Download

```
go get go.uber.org/zap
go get github.com/olivere/elastic/v7
```


Se você deseja enviar logs automaticamente para o Elasticsearch usando `zap`, pode usar uma combinação do `zap` para gerar logs e um cliente Elasticsearch para enviar os logs. Para enviar logs automaticamente, você pode criar um `zap` logger que inclui um hook ou função personalizada que envia os logs para o Elasticsearch.

Aqui está um exemplo mais detalhado de como fazer isso:

### 1. Configurar o Logger com `zap`

Crie um logger `zap` que irá gerar logs no formato JSON:

```go
package main

import (
    "context"
    "encoding/json"
    "fmt"
    "net/http"
    "bytes"

    "go.uber.org/zap"
    "github.com/olivere/elastic/v7"
)

// Define um tipo para um hook personalizado
type esHook struct {
    client *elastic.Client
}

// Implementa o método para o hook
func (h *esHook) Fire(entry zapcore.Entry) error {
    logMessage := map[string]interface{}{
        "level":   entry.Level.String(),
        "msg":     entry.Message,
        "time":    entry.Time,
        "caller":  entry.Caller.String(),
        "fields":  entry.Extra,
    }
    jsonLogMessage, _ := json.Marshal(logMessage)

    _, err := h.client.Index().
        Index("logs").
        BodyJson(bytes.NewReader(jsonLogMessage)).
        Do(context.Background())
    if err != nil {
        return fmt.Errorf("erro ao enviar log para Elasticsearch: %w", err)
    }

    return nil
}

func (h *esHook) Levels() []zapcore.Level {
    return zapcore.AllLevels
}

func main() {
    // Configura o cliente Elasticsearch
    es, err := elastic.NewClient(elastic.SetSniff(false))
    if err != nil {
        panic(fmt.Sprintf("erro ao criar cliente Elasticsearch: %v", err))
    }

    // Configura o logger zap
    core := zapcore.NewTee(
        zapcore.NewCore(
            zapcore.NewJSONEncoder(zap.NewProductionEncoderConfig()),
            zapcore.AddSync(zapcore.NewConsoleWriter()),
            zapcore.InfoLevel,
        ),
        zapcore.NewCore(
            zapcore.NewJSONEncoder(zap.NewProductionEncoderConfig()),
            zapcore.AddSync(&esHook{client: es}),
            zapcore.InfoLevel,
        ),
    )

    logger := zap.New(core)
    defer logger.Sync() // Flushes buffer, if any

    // Usa o logger
    logger.Info("Este é um log de exemplo",
        zap.String("tipo", "exemplo"),
        zap.Int("número", 123),
    )
}
```

### Explicação

1. **Configuração do Cliente Elasticsearch**: Configure o cliente Elasticsearch usando `olivere/elastic`.

2. **Hook Personalizado**: O `esHook` é um hook personalizado que implementa a interface `zapcore.Hook`. Ele é responsável por enviar logs para o Elasticsearch. O método `Fire` é chamado sempre que um log é registrado.

3. **Configuração do Logger**: Configure o logger `zap` para usar o `esHook` e envie logs para o Elasticsearch. O método `Levels` define quais níveis de logs o hook deve processar.

4. **Enviar Logs**: Use o logger normalmente em sua aplicação e os logs serão enviados automaticamente para o Elasticsearch.

### Observações

- **Desempenho**: Enviar logs para o Elasticsearch pode afetar o desempenho se não for bem gerenciado. Considere usar uma fila ou buffer para processar logs de forma assíncrona se o volume de logs for alto.
- **Segurança**: Certifique-se de que o cliente Elasticsearch está configurado de forma segura e acessível apenas a partir de fontes autorizadas.

Com essa configuração, você terá um sistema de logging automatizado que envia logs diretamente para o Elasticsearch e, por conseguinte, para o Kibana.