## Indice
### Módulo 1: Introdução ao Elasticsearch e Kibana

**Objetivos:**
- Compreender os conceitos básicos de Elasticsearch e Kibana.
- Instalar e configurar o Elasticsearch e o Kibana.
- Familiarizar-se com a interface do Kibana.

**Conteúdo:**

1. **Introdução ao Elasticsearch:**
    - O que é Elasticsearch?
    - Conceitos principais: Índices, Documentos, Shards, Réplicas.
    - Casos de uso comuns.

2. **Introdução ao Kibana:**
    - O que é Kibana?
    - Como o Kibana se integra com o Elasticsearch?
    - Funcionalidades principais do Kibana.

3. **Instalação e Configuração:**
    - Pré-requisitos de instalação.
    - Instalando Elasticsearch.
    - Configurando Elasticsearch (elasticsearch.yml).
    - Instalando Kibana.
    - Configurando Kibana (kibana.yml).

4. **Primeiros Passos no Kibana:**
    - Navegando na interface do Kibana.
    - Criando o primeiro índice no Elasticsearch.
    - Conectando Kibana ao índice do Elasticsearch.

### Módulo 2: Indexação e Pesquisa no Elasticsearch

**Objetivos:**
- Aprender a indexar dados no Elasticsearch.
- Realizar pesquisas básicas e avançadas.

**Conteúdo:**

1. **Indexação de Dados:**
    - Adicionando documentos a um índice.
    - Atualizando e deletando documentos.
    - Bulk API para indexação em massa.

2. **Consultas no Elasticsearch:**
    - Estrutura básica de uma consulta.
    - Consulta Match, Term, Range, etc.
    - Filtragem de dados.

3. **Análise de Texto:**
    - Analisadores e Tokenizers.
    - Campos de texto vs. campos de palavra-chave.
    - Mapeamento de campos personalizados.

4. **Agregações:**
    - O que são agregações?
    - Agregações básicas: Sum, Avg, Min, Max.
    - Agregações compostas.

### Módulo 3: Visualização de Dados no Kibana

**Objetivos:**
- Criar visualizações e dashboards no Kibana.
- Utilizar diferentes tipos de visualizações para analisar dados.

**Conteúdo:**

1. **Descoberta de Dados:**
    - Usando o Discover para explorar dados.
    - Salvando consultas.

2. **Visualizações:**
    - Criando visualizações básicas (Barras, Linhas, Tabelas).
    - Visualizações avançadas (Heatmaps, Mapas, Timelion).
    - Customização de visualizações.

3. **Dashboards:**
    - Criando e configurando dashboards.
    - Interatividade em dashboards.
    - Compartilhamento e exportação de dashboards.

4. **Canvas e Lens:**
    - Introdução ao Canvas para visualizações personalizadas.
    - Usando Lens para análises intuitivas.

### Módulo 4: Monitoramento e Gerenciamento

**Objetivos:**
- Configurar monitoramento e alertas no Kibana e Elasticsearch.
- Gerenciar clusters do Elasticsearch.

**Conteúdo:**

1. **Monitoramento:**
    - Introdução ao X-Pack Monitoring.
    - Configurando o monitoramento de clusters.
    - Análise de métricas de desempenho.

2. **Alertas:**
    - Introdução ao Watcher.
    - Criando alertas básicos.
    - Alertas avançados e ações.

3. **Gerenciamento de Clusters:**
    - Configurações de nós e clusters.
    - Adição e remoção de nós.
    - Backup e restauração de índices.

4. **Segurança:**
    - Configuração de usuários e permissões.
    - Segurança de comunicação (TLS/SSL).
    - Proteção de dados sensíveis.

### Módulo 5: Práticas Avançadas e Boas Práticas

**Objetivos:**
- Aplicar técnicas avançadas e seguir boas práticas para otimização e manutenção.

**Conteúdo:**

1. **Tuning de Desempenho:**
    - Otimização de consultas.
    - Configuração de caches.
    - Balanceamento de carga.

2. **Escalabilidade:**
    - Planejamento de escalabilidade.
    - Sharding e réplicas avançadas.

3. **Análise e Machine Learning:**
    - Introdução ao Elastic Machine Learning.
    - Criação de jobs de machine learning.
    - Análise preditiva e anomalias.

4. **Boas Práticas:**
    - Estruturação e nomenclatura de índices.
    - Manutenção de índices (curation).
    - Monitoramento contínuo e auditoria.

### Módulo 6: Projeto Prático

**Objetivos:**
- Aplicar os conhecimentos adquiridos em um projeto prático.

**Conteúdo:**

1. **Definição do Projeto:**
    - Escolha de um conjunto de dados realista.
    - Definição de requisitos e objetivos.

2. **Implementação:**
    - Indexação dos dados no Elasticsearch.
    - Criação de visualizações e dashboards no Kibana.
    - Configuração de monitoramento e alertas.

3. **Apresentação:**
    - Preparação de um relatório ou apresentação.
    - Compartilhamento das lições aprendidas e resultados.

### Recursos Adicionais

- Documentação oficial do Elasticsearch e Kibana.
- Cursos online e tutoriais.
- Comunidades e fóruns de suporte.
- Exemplos de projetos e casos de uso.

Com essa estrutura, você terá uma base sólida para aprender e se especializar em Elasticsearch e Kibana, desde os fundamentos até as práticas avançadas.

### Módulo 1: Introdução ao Elasticsearch e Kibana

#### 1. Introdução ao Elasticsearch

##### O que é Elasticsearch?

Elasticsearch é um mecanismo de busca e análise distribuído e de código aberto, construído no topo do Apache Lucene. Ele é usado para buscas de texto completo, análise de logs, inteligência operacional e outras tarefas que requerem armazenamento e análise de grandes volumes de dados.

##### Conceitos Principais

- **Índices:**
    - Um índice é uma coleção de documentos que compartilham características semelhantes. Ele é identificado por um nome que é usado para referenciá-lo nas operações de indexação, pesquisa, atualização e exclusão.

- **Documentos:**
    - A menor unidade de dados indexável no Elasticsearch, representado em formato JSON. Um documento é armazenado em um índice e possui um tipo, um ID e um conjunto de campos.

- **Shards:**
    - Os índices podem ser divididos em múltiplos shards (fragmentos) para distribuição e paralelização das operações. Cada shard é uma instância do Lucene e é gerenciado por um nó do cluster.

- **Réplicas:**
    - Réplicas são cópias dos shards, usadas para aumentar a disponibilidade e a tolerância a falhas. Elas permitem que o cluster continue a operar mesmo que um ou mais nós falhem.

##### Casos de Uso Comuns

- **Pesquisa de Texto Completo:**
    - Elasticsearch é frequentemente usado para implementar funcionalidades de busca em sites e aplicativos, como a busca de produtos em e-commerces e a busca de conteúdo em sites de notícias.

- **Análise de Logs:**
    - Elasticsearch é utilizado em conjunto com o Logstash e o Kibana (formando a stack ELK) para coletar, processar e visualizar logs de sistemas, servidores e aplicações.

- **Analytics em Tempo Real:**
    - Empresas usam Elasticsearch para criar dashboards interativos que mostram métricas de desempenho, vendas, monitoramento de rede e muito mais em tempo real.

#### 2. Introdução ao Kibana

##### O que é Kibana?

Kibana é uma ferramenta de visualização e análise de dados que funciona diretamente com o Elasticsearch. Ele permite que os usuários explorem, visualizem e compartilhem dados de maneira fácil e intuitiva.

##### Funcionalidades Principais

- **Visualização:**
    - Criação de gráficos, tabelas, mapas e outros tipos de visualizações para representar dados de forma visual.

- **Exploração de Dados:**
    - Uso de ferramentas de descoberta para explorar dados indexados, aplicar filtros e criar consultas.

- **Monitoramento:**
    - Análise de métricas e logs, criação de alertas e monitoramento de desempenho.

#### 3. Instalação e Configuração

##### Pré-requisitos de Instalação

- **Java:**
    - Elasticsearch requer o Java Development Kit (JDK). A versão recomendada é a JDK 11 ou superior.

- **Requisitos de Hardware:**
    - CPU e memória adequadas para o volume de dados esperado.
    - Armazenamento rápido (SSD recomendado) para índices.

##### Instalando Elasticsearch

1. **Download:**
    - Baixe a versão mais recente do Elasticsearch do [site oficial](https://www.elastic.co/downloads/elasticsearch).

2. **Instalação:**
    - Extraia o arquivo baixado e mova para o diretório desejado.

3. **Configuração:**
    - Edite o arquivo `config/elasticsearch.yml` para definir configurações básicas, como nome do cluster, nome do nó e diretórios de dados e logs.

4. **Inicialização:**
    - Execute `bin/elasticsearch` para iniciar o Elasticsearch. Verifique os logs para garantir que o serviço iniciou corretamente.

##### Instalando Kibana

1. **Download:**
    - Baixe a versão correspondente do Kibana do [site oficial](https://www.elastic.co/downloads/kibana).

2. **Instalação:**
    - Extraia o arquivo baixado e mova para o diretório desejado.

3. **Configuração:**
    - Edite o arquivo `config/kibana.yml` para definir configurações básicas, como a URL do Elasticsearch que o Kibana deve usar.

4. **Inicialização:**
    - Execute `bin/kibana` para iniciar o Kibana. A interface estará acessível através do navegador no endereço `http://localhost:5601`.

#### 4. Primeiros Passos no Kibana

##### Navegando na Interface

1. **Página Inicial:**
    - Após iniciar o Kibana, acesse `http://localhost:5601` no navegador. A página inicial fornece uma visão geral das funcionalidades disponíveis.

2. **Conectando ao Elasticsearch:**
    - Kibana automaticamente se conecta ao Elasticsearch usando a URL definida no `kibana.yml`. Certifique-se de que o Elasticsearch esteja em execução.

3. **Explorando os Dados:**
    - Use o menu lateral para acessar funcionalidades como Discover, Visualize, Dashboard, Canvas e Management.

4. **Criando o Primeiro Índice:**
    - No Elasticsearch, indexe alguns documentos simples. Por exemplo, use a API REST do Elasticsearch:
      ```bash
      curl -X POST "localhost:9200/my_first_index/_doc/1" -H 'Content-Type: application/json' -d'
      {
        "name": "John Doe",
        "age": 30,
        "occupation": "Software Engineer"
      }'
      ```

5. **Configurando o Padrão de Índices no Kibana:**
    - No Kibana, vá para Management > Index Patterns e crie um novo padrão de índice que corresponda ao índice recém-criado (`my_first_index`).

6. **Explorando Dados no Discover:**
    - Acesse Discover, selecione o padrão de índice e explore os dados indexados, aplicando filtros e consultas conforme necessário.

Com esses passos, os participantes terão uma base sólida para começar a trabalhar com Elasticsearch e Kibana. Eles poderão explorar, indexar e visualizar dados de forma eficiente, preparando-se para os módulos mais avançados.


### Módulo 2: Indexação e Pesquisa no Elasticsearch

#### 1. Indexação de Dados

##### Adicionando Documentos

- **Estrutura de um Documento:**
    - Um documento é uma unidade de informação no Elasticsearch, representado em formato JSON. Cada documento reside em um índice e possui um tipo, um ID e um conjunto de campos.

- **Operações CRUD:**
    - **Create (Criação):** Adiciona um novo documento a um índice.
      ```bash
      curl -X POST "localhost:9200/my_index/_doc/1" -H 'Content-Type: application/json' -d'
      {
        "name": "Jane Doe",
        "age": 25,
        "occupation": "Data Scientist"
      }'
      ```

    - **Read (Leitura):** Obtém um documento a partir de seu ID.
      ```bash
      curl -X GET "localhost:9200/my_index/_doc/1"
      ```

    - **Update (Atualização):** Atualiza campos de um documento existente.
      ```bash
      curl -X POST "localhost:9200/my_index/_update/1" -H 'Content-Type: application/json' -d'
      {
        "doc": {
          "age": 26
        }
      }'
      ```

    - **Delete (Exclusão):** Remove um documento a partir de seu ID.
      ```bash
      curl -X DELETE "localhost:9200/my_index/_doc/1"
      ```

##### Bulk API para Indexação em Massa

- A Bulk API permite realizar múltiplas operações em um único pedido, o que é útil para melhorar a eficiência ao lidar com grandes volumes de dados.
  ```bash
  curl -X POST "localhost:9200/_bulk" -H 'Content-Type: application/json' -d'
  { "index" : { "_index" : "my_index", "_id" : "1" } }
  { "name" : "Alice", "age" : 28, "occupation" : "Engineer" }
  { "index" : { "_index" : "my_index", "_id" : "2" } }
  { "name" : "Bob", "age" : 32, "occupation" : "Manager" }
  '
  ```

#### 2. Consultas no Elasticsearch

##### Estrutura Básica de uma Consulta

- As consultas no Elasticsearch são expressas em JSON e podem ser bastante complexas. A estrutura básica envolve a definição de um tipo de consulta (query type) e seus parâmetros.
  ```bash
  curl -X GET "localhost:9200/my_index/_search" -H 'Content-Type: application/json' -d'
  {
    "query": {
      "match": {
        "occupation": "Engineer"
      }
    }
  }'
  ```

##### Tipos de Consulta

- **Match Query:**
    - Realiza uma busca de texto completo em um ou mais campos.
  ```bash
  curl -X GET "localhost:9200/my_index/_search" -H 'Content-Type: application/json' -d'
  {
    "query": {
      "match": {
        "name": "Alice"
      }
    }
  }'
  ```

- **Term Query:**
    - Busca por um termo exato em um campo.
  ```bash
  curl -X GET "localhost:9200/my_index/_search" -H 'Content-Type: application/json' -d'
  {
    "query": {
      "term": {
        "age": 28
      }
    }
  }'
  ```

- **Range Query:**
    - Busca por valores dentro de um intervalo.
  ```bash
  curl -X GET "localhost:9200/my_index/_search" -H 'Content-Type: application/json' -d'
  {
    "query": {
      "range": {
        "age": {
          "gte": 30,
          "lte": 40
        }
      }
    }
  }'
  ```

##### Filtragem de Dados

- Os filtros são usados para restringir os resultados da busca sem afetar a pontuação das consultas.
  ```bash
  curl -X GET "localhost:9200/my_index/_search" -H 'Content-Type: application/json' -d'
  {
    "query": {
      "bool": {
        "must": [
          { "match": { "occupation": "Engineer" } }
        ],
        "filter": [
          { "term": { "age": 28 } }
        ]
      }
    }
  }'
  ```

#### 3. Análise de Texto

##### Analisadores e Tokenizers

- **Analisadores:**
    - Analisadores transformam texto de entrada em tokens ou termos que podem ser indexados. O Elasticsearch vem com vários analisadores integrados, como `standard`, `simple`, `whitespace`, `stop`, `keyword`, `pattern`, etc.

- **Tokenizers:**
    - Tokenizers dividem o texto em termos menores (tokens). Exemplos incluem `standard`, `letter`, `lowercase`, `whitespace`, `uax_url_email`, `keyword`, etc.

- **Exemplo de Analisador Personalizado:**
  ```bash
  curl -X PUT "localhost:9200/my_index" -H 'Content-Type: application/json' -d'
  {
    "settings": {
      "analysis": {
        "analyzer": {
          "custom_analyzer": {
            "type": "custom",
            "tokenizer": "standard",
            "filter": ["lowercase", "stop"]
          }
        }
      }
    },
    "mappings": {
      "properties": {
        "content": {
          "type": "text",
          "analyzer": "custom_analyzer"
        }
      }
    }
  }'
  ```

##### Campos de Texto vs. Campos de Palavra-chave

- **Texto (`text`):**
    - Usado para campos que devem ser analisados, como descrições ou comentários. É apropriado para busca de texto completo.

- **Palavra-chave (`keyword`):**
    - Usado para campos que não devem ser analisados, como IDs, códigos de produto, ou campos onde você precisa de buscas exatas ou agregações.

#### 4. Agregações

##### O que são Agregações?

- Agregações são usadas para sumarizar dados, calcular estatísticas e criar visualizações complexas. Elas permitem transformar grandes volumes de dados em informações significativas.

##### Agregações Básicas

- **Sum:**
    - Calcula a soma de valores numéricos.
  ```bash
  curl -X GET "localhost:9200/my_index/_search" -H 'Content-Type: application/json' -d'
  {
    "size": 0,
    "aggs": {
      "total_age": {
        "sum": {
          "field": "age"
        }
      }
    }
  }'
  ```

- **Avg:**
    - Calcula a média de valores numéricos.
  ```bash
  curl -X GET "localhost:9200/my_index/_search" -H 'Content-Type: application/json' -d'
  {
    "size": 0,
    "aggs": {
      "average_age": {
        "avg": {
          "field": "age"
        }
      }
    }
  }'
  ```

- **Min:**
    - Encontra o valor mínimo.
  ```bash
  curl -X GET "localhost:9200/my_index/_search" -H 'Content-Type: application/json' -d'
  {
    "size": 0,
    "aggs": {
      "min_age": {
        "min": {
          "field": "age"
        }
      }
    }
  }'
  ```

- **Max:**
    - Encontra o valor máximo.
  ```bash
  curl -X GET "localhost:9200/my_index/_search" -H 'Content-Type: application/json' -d'
  {
    "size": 0,
    "aggs": {
      "max_age": {
        "max": {
          "field": "age"
        }
      }
    }
  }'
  ```

##### Agregações Compostas

- Agregações podem ser combinadas para criar estruturas mais complexas. Por exemplo, você pode calcular a média de idade por ocupação.
  ```bash
  curl -X GET "localhost:9200/my_index/_search" -H 'Content-Type: application/json' -d'
  {
    "size": 0,
    "aggs": {
      "by_occupation": {
        "terms": {
          "field": "occupation.keyword"
        },
        "aggs": {
          "average_age": {
            "avg": {
              "field": "age"
            }
          }
        }
      }
    }
  }'
  ```

Esse módulo fornece uma base sólida para trabalhar com indexação e consultas no Elasticsearch. Ao entender como adicionar, atualizar e excluir documentos, realizar buscas complexas e agregações, você estará preparado para explorar e analisar grandes volumes de dados de maneira eficiente.


### Módulo 3: Visualização de Dados no Kibana

#### 1. Descoberta de Dados

##### Usando o Discover

O Discover é a ferramenta do Kibana para explorar dados brutos. É a primeira parada para quem quer entender os dados que foram indexados no Elasticsearch.

- **Navegando no Discover:**
    - Acesse a aba Discover no menu lateral do Kibana.
    - Selecione o padrão de índice que deseja explorar.
    - Você verá uma lista de documentos com uma linha do tempo que mostra a distribuição dos documentos ao longo do tempo.

- **Aplicação de Filtros e Consultas:**
    - Use a barra de pesquisa para inserir consultas Lucene ou KQL (Kibana Query Language).
    - Adicione filtros clicando nos campos e selecionando valores específicos.

- **Visualização de Campos:**
    - No painel esquerdo, expanda e contraia campos para ver seus valores únicos.
    - Use o botão "Add" para adicionar campos à visualização principal dos documentos.

#### 2. Visualizações

##### Criando Visualizações Básicas

As visualizações são componentes fundamentais para a criação de dashboards no Kibana.

- **Tipos de Visualização:**
    - **Gráfico de Barras:** Útil para comparar valores categóricos.
    - **Gráfico de Linhas:** Ideal para visualizar séries temporais.
    - **Gráfico de Tabelas:** Mostra dados tabulares de maneira detalhada.

- **Criação de Visualizações:**
    - Acesse a aba Visualize no menu lateral.
    - Clique em "Create visualization" e selecione o tipo de visualização desejado.
    - Escolha o padrão de índice e configure as opções de visualização.

- **Configuração de Visualizações:**
    - Defina eixos (X e Y) para gráficos.
    - Adicione métricas e agregações, como soma, média, contagem, etc.
    - Customize a aparência com opções de estilo, cores, e rótulos.

##### Visualizações Avançadas

Kibana oferece opções avançadas para criar visualizações mais complexas.

- **Heatmaps:** Representam dados em uma matriz de cores, ideal para mostrar densidades de pontos de dados.
    - Configure as células do heatmap para representar diferentes métricas e intervalos de dados.

- **Mapas:** Use coordenadas geográficas para visualizar dados em um contexto espacial.
    - Configure mapas de coordenadas para representar pontos de dados geolocalizados.
    - Utilize layers e filtros para refinar a visualização.

- **Timelion:** Uma ferramenta poderosa para análise de séries temporais com sintaxe personalizada.
    - Crie visualizações de séries temporais complexas com operações matemáticas e funções.

#### 3. Dashboards

##### Criando Dashboards

Dashboards são uma coleção de visualizações que fornecem uma visão geral e interativa dos dados.

- **Adição de Visualizações:**
    - Acesse a aba Dashboard no menu lateral.
    - Clique em "Create new dashboard".
    - Use o botão "Add" para adicionar visualizações já criadas.

- **Configuração de Layout:**
    - Arraste e redimensione as visualizações para organizar o layout do dashboard.
    - Adicione e configure filtros globais que afetem todas as visualizações no dashboard.

##### Interatividade

- **Filtragem e Drill-Down:**
    - Clique em elementos das visualizações para aplicar filtros automaticamente.
    - Use painéis interativos para permitir navegação aprofundada nos dados.

- **Painéis de Controle:**
    - Adicione controles como dropdowns e sliders para permitir filtragem dinâmica.
    - Configure as ações dos controles para afetar visualizações específicas ou todo o dashboard.

#### 4. Canvas e Lens

##### Canvas

Canvas é uma ferramenta de apresentação e design que permite criar apresentações dinâmicas e interativas.

- **Criação de Apresentações:**
    - Acesse a aba Canvas no menu lateral.
    - Clique em "Create new workpad" para iniciar uma nova apresentação.
    - Adicione elementos como texto, imagens, gráficos e visualizações.

- **Personalização:**
    - Customize o layout, fundo, e elementos gráficos.
    - Adicione interatividade com controles e animações.

##### Lens

Lens é uma ferramenta intuitiva de análise de dados que facilita a criação de visualizações arrastando e soltando campos.

- **Interface Intuitiva:**
    - Acesse a aba Lens no menu Visualize.
    - Arraste campos do padrão de índice para criar visualizações instantaneamente.
    - Configure e customize as visualizações com uma interface amigável.

- **Exploração de Dados:**
    - Use a funcionalidade de arrastar e soltar para adicionar métricas, eixos, e filtros.
    - Compare diferentes visualizações facilmente para encontrar insights.

### Exemplos Práticos

#### Exemplo 1: Criando um Gráfico de Barras

1. **Acesse Visualize:**
    - Vá para Visualize e clique em "Create visualization".
    - Selecione "Bar chart" e escolha o padrão de índice.

2. **Configure a Visualização:**
    - Adicione uma agregação no eixo X (por exemplo, "Terms" para categorizar por um campo específico).
    - Adicione uma métrica no eixo Y (por exemplo, "Count" para contar documentos).

3. **Customize:**
    - Defina rótulos, cores e estilos.
    - Salve a visualização e adicione ao dashboard.

#### Exemplo 2: Criando um Dashboard Interativo

1. **Acesse Dashboard:**
    - Vá para Dashboard e clique em "Create new dashboard".

2. **Adicione Visualizações:**
    - Use o botão "Add" para adicionar visualizações previamente criadas.

3. **Configure Interatividade:**
    - Adicione filtros globais e controles interativos.
    - Organize o layout e salve o dashboard.

#### Exemplo 3: Usando Lens para Análise Rápida

1. **Acesse Lens:**
    - Vá para Visualize e selecione Lens.

2. **Arraste e Solte Campos:**
    - Arraste um campo para o eixo X (por exemplo, "date").
    - Arraste uma métrica para o eixo Y (por exemplo, "count").

3. **Explore e Customize:**
    - Compare diferentes visualizações e encontre insights.
    - Salve a visualização e adicione ao dashboard.

Com este módulo, os participantes aprenderão a utilizar as poderosas ferramentas de visualização e análise do Kibana, criando visualizações detalhadas e interativas que permitem uma exploração profunda dos dados.

### Módulo 4: Administração e Manutenção do Elasticsearch e Kibana

#### 1. Gerenciamento de Clusters

##### Estrutura de Cluster

- **Nó (Node):**
    - Cada instância do Elasticsearch é chamada de nó. Um cluster pode ter vários nós que colaboram para armazenar e pesquisar dados.

- **Cluster:**
    - Um cluster é um conjunto de um ou mais nós que juntos armazenam dados e fornecem recursos de busca indexada.

- **Tipos de Nós:**
    - **Nó Mestre (Master Node):** Gerencia o cluster, mantendo o estado e as configurações do cluster.
    - **Nó de Dados (Data Node):** Armazena dados e realiza operações relacionadas a eles, como busca e agregações.
    - **Nó de Cliente (Client Node):** Encaminha solicitações de clientes para os nós de dados apropriados.

##### Configuração de Cluster

- **Configuração Básica:**
    - No arquivo `elasticsearch.yml`, configure o nome do cluster, nome do nó, e endereços de outros nós no cluster.
  ```yaml
  cluster.name: my_cluster
  node.name: node-1
  network.host: 0.0.0.0
  discovery.seed_hosts: ["node-1", "node-2"]
  cluster.initial_master_nodes: ["node-1", "node-2"]
  ```

- **Adicionando Nós ao Cluster:**
    - Configure cada nó com informações do cluster e nós mestres.
  ```yaml
  cluster.name: my_cluster
  node.name: node-2
  network.host: 0.0.0.0
  discovery.seed_hosts: ["node-1", "node-2"]
  cluster.initial_master_nodes: ["node-1", "node-2"]
  ```

##### Monitoramento do Cluster

- **API de Cluster Health:**
    - Verifique a saúde do cluster para monitorar o estado geral e detectar problemas.
  ```bash
  curl -X GET "localhost:9200/_cluster/health?pretty"
  ```

- **API de Estado do Cluster:**
    - Obtenha detalhes sobre a configuração do cluster, incluindo nós e shards.
  ```bash
  curl -X GET "localhost:9200/_cluster/state?pretty"
  ```

#### 2. Segurança

##### Autenticação e Autorização

- **Configuração de Segurança:**
    - Habilite a segurança no Elasticsearch editando o arquivo `elasticsearch.yml`.
  ```yaml
  xpack.security.enabled: true
  xpack.security.transport.ssl.enabled: true
  ```

- **Criação de Usuários:**
    - Use a API de segurança para criar e gerenciar usuários.
  ```bash
  curl -X POST "localhost:9200/_security/user/new_user" -H 'Content-Type: application/json' -d'
  {
    "password" : "new_password",
    "roles" : [ "admin" ],
    "full_name" : "New User",
    "email" : "new_user@example.com"
  }'
  ```

- **Papéis e Permissões:**
    - Defina papéis para controlar o acesso a índices e ações específicas.
  ```bash
  curl -X POST "localhost:9200/_security/role/my_role" -H 'Content-Type: application/json' -d'
  {
    "cluster": ["all"],
    "indices": [
      {
        "names": [ "my_index" ],
        "privileges": ["read", "write"]
      }
    ]
  }'
  ```

##### Configuração de TLS/SSL

- **Geração de Certificados:**
    - Gere certificados SSL para criptografar a comunicação entre nós.
  ```bash
  ./bin/elasticsearch-certutil ca
  ./bin/elasticsearch-certutil cert --ca elastic-stack-ca.p12
  ```

- **Configuração de Certificados:**
    - Configure os certificados gerados no arquivo `elasticsearch.yml`.
  ```yaml
  xpack.security.transport.ssl.enabled: true
  xpack.security.transport.ssl.verification_mode: certificate
  xpack.security.transport.ssl.keystore.path: "path/to/your/keystore.p12"
  xpack.security.transport.ssl.truststore.path: "path/to/your/truststore.p12"
  ```

#### 3. Backup e Restauração

##### Snapshots

- **Criação de Repositório de Snapshots:**
    - Defina um repositório para armazenar snapshots, como um sistema de arquivos ou um bucket S3.
  ```bash
  curl -X PUT "localhost:9200/_snapshot/my_backup" -H 'Content-Type: application/json' -d'
  {
    "type": "fs",
    "settings": {
      "location": "/mount/backups/my_backup"
    }
  }'
  ```

- **Criação de Snapshot:**
    - Capture um snapshot dos índices desejados.
  ```bash
  curl -X PUT "localhost:9200/_snapshot/my_backup/snapshot_1?wait_for_completion=true" -H 'Content-Type: application/json'
  ```

##### Restauração de Snapshots

- **Restauração de Índices:**
    - Restaure os índices de um snapshot.
  ```bash
  curl -X POST "localhost:9200/_snapshot/my_backup/snapshot_1/_restore" -H 'Content-Type: application/json' -d'
  {
    "indices": "my_index",
    "ignore_unavailable": true,
    "include_global_state": false
  }'
  ```

#### 4. Monitoramento e Logging

##### Monitoramento com Kibana

- **Stack Monitoring:**
    - Habilite o monitoramento da stack ELK no Kibana para visualizar métricas de desempenho do Elasticsearch.
    - Acesse a aba Stack Monitoring no menu lateral do Kibana.

##### Logging

- **Configuração de Logs:**
    - Configure a saída de logs no arquivo `log4j2.properties` do Elasticsearch.
  ```properties
  appender.rolling.type = RollingFile
  appender.rolling.name = rolling
  appender.rolling.fileName = ${sys:es.logs.base_path}${sys:file.separator}${sys:es.logs.cluster_name}.log
  appender.rolling.filePattern = ${sys:es.logs.base_path}${sys:file.separator}${sys:es.logs.cluster_name}-%d{yyyy-MM-dd}-%i.log.gz
  appender.rolling.layout.type = PatternLayout
  appender.rolling.layout.pattern = [%d{ISO8601}] [%p] [%c{1.}] [%t] [%marker] [%C{1.}] [%L] - %m%n
  appender.rolling.policies.type = Policies
  appender.rolling.policies.time.type = TimeBasedTriggeringPolicy
  appender.rolling.policies.time.interval = 1
  appender.rolling.policies.time.modulate = true
  appender.rolling.policies.size.type = SizeBasedTriggeringPolicy
  appender.rolling.policies.size.size = 128MB
  rootLogger.level = info
  rootLogger.appenderRef.rolling.ref = rolling
  ```

- **Análise de Logs:**
    - Use ferramentas como Filebeat para enviar logs para o Elasticsearch e analisá-los no Kibana.
    - Configure Filebeat para monitorar os logs do Elasticsearch e enviá-los para um índice.
  ```yaml
  filebeat.inputs:
  - type: log
    paths:
      - /path/to/elasticsearch/logs/*.log

  output.elasticsearch:
    hosts: ["localhost:9200"]
  ```

#### 5. Performance e Tuning

##### Ajustes de Performance

- **Configuração de JVM:**
    - Aumente a memória heap da JVM para melhorar a performance.
  ```bash
  export ES_HEAP_SIZE=4g
  ```

- **Configuração de Shards e Réplicas:**
    - Ajuste o número de shards e réplicas para otimizar a distribuição de dados e a redundância.
  ```bash
  curl -X PUT "localhost:9200/my_index/_settings" -H 'Content-Type: application/json' -d'
  {
    "index": {
      "number_of_replicas": 1
    }
  }'
  ```

##### Diagnóstico de Problemas

- **Uso da API Cat:**
    - Use a API Cat para obter informações detalhadas sobre o estado do cluster, índices, shards, e nós.
  ```bash
  curl -X GET "localhost:9200/_cat/indices?v"
  curl -X GET "localhost:9200/_cat/nodes?v"
  ```

- **Análise de Gargalos:**
    - Monitore métricas de performance, como latência de busca e tempos de resposta, usando ferramentas de monitoramento como Kibana e Grafana.

Com este módulo, os participantes aprenderão a gerenciar, proteger e otimizar clusters Elasticsearch e Kibana, garantindo a integridade dos dados e a eficiência das operações. Eles também aprenderão a configurar backups e restaurações, monitorar logs e ajustar a performance do sistema para atender às necessidades empresariais.


### Módulo 5: Análise Avançada e Machine Learning no Elasticsearch e Kibana

#### 1. Introdução ao Machine Learning no Elasticsearch

##### Configuração do Machine Learning

- **Habilitando Machine Learning:**
    - Certifique-se de que o recurso de Machine Learning está habilitado no Elasticsearch.
    - No arquivo `elasticsearch.yml`, verifique se a linha abaixo está presente e não comentada:
  ```yaml
  xpack.ml.enabled: true
  ```

- **Instalação dos Plugins Necessários:**
    - O recurso de Machine Learning está incluído no pacote X-Pack do Elasticsearch. Certifique-se de que você está usando uma versão do Elasticsearch que inclui o X-Pack.

#### 2. Anomalias e Detecção de Anomalias

##### Criação de Jobs de Detecção de Anomalias

- **Definição de Jobs:**
    - Um job de detecção de anomalias analisa os dados em busca de padrões incomuns ou anômalos.
    - No Kibana, vá para a seção "Machine Learning" e clique em "Create Job".

- **Tipos de Jobs:**
    - **Single Metric:** Detecta anomalias em uma única métrica.
    - **Multi Metric:** Detecta anomalias em várias métricas ao mesmo tempo.
    - **Advanced:** Oferece configurações avançadas para detecção de anomalias.

- **Configuração de Jobs:**
    - Selecione o índice e o campo de tempo.
    - Defina a métrica a ser monitorada, como média, soma, contagem, etc.
    - Configure a frequência e o intervalo de análise.

##### Interpretação dos Resultados

- **Visualização de Anomalias:**
    - Após a criação e execução do job, vá para a seção "Anomaly Explorer" no Kibana.
    - Visualize as anomalias detectadas em gráficos de séries temporais.

- **Pontuação de Anomalia:**
    - Cada anomalia detectada recebe uma pontuação que indica o grau de anomalia. Pontuações mais altas indicam eventos mais raros.

#### 3. Forecasting

##### Previsão de Dados

- **Criação de Previsões:**
    - Previsões permitem antecipar tendências futuras com base em dados históricos.
    - No Kibana, vá para a seção "Machine Learning" e selecione um job de detecção de anomalias.
    - Clique em "Forecast" para criar uma previsão.

- **Configuração de Previsões:**
    - Defina o intervalo de tempo para a previsão.
    - Revise e ajuste as configurações conforme necessário.

- **Interpretação dos Resultados:**
    - Visualize os resultados da previsão na seção "Anomaly Explorer".
    - Compare as previsões com os dados reais à medida que novos dados são adicionados.

#### 4. Data Frames e Transforms

##### Criação e Gerenciamento de Transforms

- **Definição de Transforms:**
    - Transforms permitem transformar e agregar dados em tempo real.
    - No Kibana, vá para a seção "Machine Learning" e clique em "Transforms".

- **Configuração de Transforms:**
    - Selecione o índice de origem e defina as transformações desejadas, como agrupamento por campo e aplicação de funções de agregação.
  ```bash
  PUT _transform/my-transform
  {
    "source": {
      "index": "source-index"
    },
    "dest": {
      "index": "dest-index"
    },
    "pivot": {
      "group_by": {
        "field_name": {
          "terms": {
            "field": "field_name"
          }
        }
      },
      "aggregations": {
        "avg_value": {
          "avg": {
            "field": "value"
          }
        }
      }
    }
  }
  ```

- **Execução de Transforms:**
    - Inicie e monitore o status dos transforms no Kibana.

#### 5. Modelos de Regressão e Classificação

##### Treinamento de Modelos

- **Definição de Dados de Treinamento:**
    - Para treinar modelos de regressão e classificação, defina um conjunto de dados de treinamento com as características e o alvo.

- **Treinamento com Elastic Machine Learning:**
    - Utilize APIs de Machine Learning do Elasticsearch para treinar modelos.
  ```bash
  POST _ml/data_frame/analytics/my-analysis/_start
  ```

##### Avaliação e Implementação de Modelos

- **Avaliação de Modelos:**
    - Avalie a performance dos modelos treinados usando métricas como precisão, recall, e F1-score.

- **Implementação de Modelos:**
    - Após a avaliação, implemente os modelos para realizar previsões em novos dados.

#### 6. Visualização de Resultados no Kibana

##### Dashboards de Machine Learning

- **Criação de Dashboards:**
    - Crie dashboards no Kibana para visualizar os resultados de jobs de detecção de anomalias, previsões, e transforms.
    - Combine diferentes visualizações para obter uma visão abrangente dos dados.

- **Interatividade e Filtros:**
    - Adicione filtros e controles interativos para permitir uma análise mais detalhada e personalizada dos dados.

#### 7. Exemplos Práticos

##### Exemplo 1: Detecção de Anomalias em Dados de Log

1. **Criação de Job de Detecção de Anomalias:**
    - No Kibana, vá para Machine Learning > Create Job > Single Metric.
    - Selecione o índice de logs e configure a métrica para monitorar.

2. **Execução e Visualização:**
    - Execute o job e visualize as anomalias na seção Anomaly Explorer.

##### Exemplo 2: Previsão de Demanda de Produto

1. **Criação de Previsão:**
    - Selecione um job de detecção de anomalias existente relacionado a vendas de produtos.
    - Crie uma previsão para o próximo mês.

2. **Análise dos Resultados:**
    - Compare os resultados da previsão com as vendas reais conforme novos dados são adicionados.

##### Exemplo 3: Transformação de Dados para Relatórios Mensais

1. **Configuração de Transform:**
    - No Kibana, vá para Machine Learning > Transforms > Create Transform.
    - Selecione o índice de vendas e configure uma transformação para agrupar por mês e calcular a média de vendas.

2. **Visualização:**
    - Execute o transform e visualize os resultados em um dashboard no Kibana.

Com este módulo, os participantes aprenderão a utilizar os recursos avançados de Machine Learning e análise de dados do Elasticsearch e Kibana. Eles serão capazes de detectar anomalias, fazer previsões, transformar dados e visualizar resultados de forma eficaz para obter insights valiosos.


### Módulo 6: Integrando e Automatizando com Elasticsearch e Kibana

#### 1. Integração com Outros Sistemas

##### Integração com Logstash

- **O que é o Logstash:**
    - Logstash é uma ferramenta de coleta, transformação e envio de dados que faz parte do stack ELK.

- **Configuração Básica do Logstash:**
    - Instale o Logstash e configure um pipeline de entrada, filtro e saída.
  ```plaintext
  input {
    file {
      path => "/var/log/myapp/*.log"
      start_position => "beginning"
    }
  }
  
  filter {
    grok {
      match => { "message" => "%{COMBINEDAPACHELOG}" }
    }
    date {
      match => [ "timestamp" , "dd/MMM/yyyy:HH:mm:ss Z" ]
    }
  }
  
  output {
    elasticsearch {
      hosts => ["localhost:9200"]
      index => "myapp-logs-%{+YYYY.MM.dd}"
    }
  }
  ```

- **Iniciando o Logstash:**
  ```bash
  bin/logstash -f /path/to/logstash.conf
  ```

##### Integração com Beats

- **O que é o Beats:**
    - Beats são agentes de dados leves que enviam dados de centenas de máquinas e sistemas para Logstash ou Elasticsearch.

- **Instalação e Configuração do Filebeat:**
    - Instale o Filebeat em uma máquina que deseja monitorar.
    - Configure o Filebeat para enviar logs para o Elasticsearch.
  ```yaml
  filebeat.inputs:
  - type: log
    paths:
      - /var/log/*.log

  output.elasticsearch:
    hosts: ["localhost:9200"]
  ```

- **Iniciando o Filebeat:**
  ```bash
  sudo service filebeat start
  ```

##### Integração com Kafka

- **Uso do Kafka como Pipeline de Dados:**
    - Apache Kafka pode ser usado para coletar e distribuir logs e eventos entre diferentes sistemas.

- **Configuração do Logstash para Kafka:**
  ```plaintext
  input {
    kafka {
      bootstrap_servers => "localhost:9092"
      topics => ["my_topic"]
    }
  }
  
  output {
    elasticsearch {
      hosts => ["localhost:9200"]
      index => "my_topic_logs"
    }
  }
  ```

#### 2. Automatizando Tarefas com Scripts e APIs

##### Uso de APIs REST do Elasticsearch

- **Introdução às APIs:**
    - O Elasticsearch oferece uma ampla gama de APIs REST para gerenciar e interagir com o cluster.

- **Exemplos de Uso:**
    - **Busca:**
      ```bash
      curl -X GET "localhost:9200/my_index/_search?q=user:kimchy&pretty"
      ```
    - **Indexação:**
      ```bash
      curl -X POST "localhost:9200/my_index/_doc/1" -H 'Content-Type: application/json' -d'
      {
        "user": "kimchy",
        "message": "trying out Elasticsearch"
      }'
      ```

##### Agendamento de Tarefas com Curator

- **O que é o Curator:**
    - Curator é uma ferramenta para gerenciar índices do Elasticsearch.

- **Instalação e Configuração do Curator:**
  ```bash
  pip install elasticsearch-curator
  ```

    - Crie um arquivo de configuração para definir as conexões do Elasticsearch.
  ```yaml
  client:
    hosts:
      - 127.0.0.1
    port: 9200
  ```

- **Uso do Curator para Gerenciar Índices:**
    - Crie um arquivo de ação para definir as tarefas, como excluir índices antigos.
  ```yaml
  actions:
    1:
      action: delete_indices
      description: "Delete indices older than 30 days"
      options:
        ignore_empty_list: True
      filters:
      - filtertype: age
        source: creation_date
        direction: older
        unit: days
        unit_count: 30
  ```

    - Execute o Curator com a configuração e o arquivo de ação.
  ```bash
  curator --config curator.yml action_file.yml
  ```

##### Automatização com Scripts

- **Uso de Scripts Painless:**
    - Painless é a linguagem de script embutida no Elasticsearch.

- **Exemplos de Scripts:**
    - **Atualização de Documentos:**
      ```bash
      curl -X POST "localhost:9200/my_index/_update/1" -H 'Content-Type: application/json' -d'
      {
        "script" : {
          "source": "ctx._source.counter += params.count",
          "lang": "painless",
          "params" : {
            "count" : 4
          }
        }
      }'
      ```

- **Uso de Ingest Pipelines:**
    - Ingest Pipelines permitem processar documentos durante a indexação.
  ```bash
  PUT _ingest/pipeline/my-pipeline
  {
    "processors": [
      {
        "set": {
          "field": "field1",
          "value": "value1"
        }
      }
    ]
  }

  POST my_index/_doc/1?pipeline=my-pipeline
  {
    "field2": "value2"
  }
  ```

#### 3. Orquestração com Kubernetes e Docker

##### Uso de Docker

- **Instalação do Elasticsearch com Docker:**
  ```bash
  docker run -d --name elasticsearch -p 9200:9200 -e "discovery.type=single-node" elasticsearch:7.10.0
  ```

- **Uso de Docker Compose:**
    - Configure um arquivo `docker-compose.yml` para iniciar o Elasticsearch e Kibana.
  ```yaml
  version: '3'
  services:
    elasticsearch:
      image: elasticsearch:7.10.0
      environment:
        - discovery.type=single-node
      ports:
        - "9200:9200"
    kibana:
      image: kibana:7.10.0
      ports:
        - "5601:5601"
      depends_on:
        - elasticsearch
  ```

    - Inicie os serviços.
  ```bash
  docker-compose up
  ```

##### Uso de Kubernetes

- **Configuração de um Cluster Kubernetes:**
    - Defina arquivos de configuração YAML para Elasticsearch e Kibana.

- **Exemplo de Configuração de Elasticsearch:**
  ```yaml
  apiVersion: apps/v1
  kind: StatefulSet
  metadata:
    name: elasticsearch
  spec:
    serviceName: "elasticsearch"
    replicas: 3
    selector:
      matchLabels:
        app: elasticsearch
    template:
      metadata:
        labels:
          app: elasticsearch
      spec:
        containers:
        - name: elasticsearch
          image: elasticsearch:7.10.0
          ports:
          - containerPort: 9200
            name: es
  ```

- **Exemplo de Configuração de Kibana:**
  ```yaml
  apiVersion: apps/v1
  kind: Deployment
  metadata:
    name: kibana
  spec:
    replicas: 1
    selector:
      matchLabels:
        app: kibana
    template:
      metadata:
        labels:
          app: kibana
      spec:
        containers:
        - name: kibana
          image: kibana:7.10.0
          ports:
          - containerPort: 5601
            name: kb
  ```

- **Iniciando os Serviços:**
  ```bash
  kubectl apply -f elasticsearch.yaml
  kubectl apply -f kibana.yaml
  ```

#### 4. Exemplos Práticos

##### Exemplo 1: Pipeline de Ingestão com Logstash e Elasticsearch

1. **Configuração do Logstash:**
    - Crie um pipeline para coletar logs, processá-los e enviá-los para o Elasticsearch.

2. **Monitoramento no Kibana:**
    - Configure dashboards no Kibana para visualizar e analisar os logs coletados.

##### Exemplo 2: Automatização de Backup com Curator

1. **Configuração do Curator:**
    - Defina um arquivo de ação para fazer backup de índices antigos.

2. **Agendamento com Cron:**
    - Agende o Curator para rodar periodicamente usando cron.
   ```bash
   0 2 * * * /usr/local/bin/curator --config /path/to/curator.yml /path/to/action_file.yml
   ```

##### Exemplo 3: Deploy do Stack ELK com Docker Compose

1. **Configuração do Docker Compose:**
    - Defina os serviços de Elasticsearch e Kibana em um arquivo `docker-compose.yml`.

2. **Início dos Serviços:**
    - Inicie os serviços e acesse o Kibana para configurar índices e visualizações.

Com este módulo, os participantes aprenderão a integrar o Elasticsearch e o Kibana com outros sistemas e ferramentas, automatizar tarefas comuns e orquestrar implantações usando Docker e Kubernetes. Eles ganharão habilidades práticas para configurar pipelines de dados, agendar tarefas de manutenção e implementar soluções escaláveis para análise de dados.

Para garantir eficiência e escalabilidade no uso do Elasticsearch, é importante seguir algumas boas práticas ao criar índices e gerenciar IDs de documentos. Aqui estão algumas recomendações:

### Boas Práticas para Criação de Índices

1. **Nomeação de Índices**
    - Use nomes de índice descritivos e significativos.
    - Evite caracteres especiais e espaços. Use apenas letras minúsculas, números, sublinhados (_), traços (-) e pontos (.).
    - Utilize prefixos ou sufixos para diferenciar ambientes (por exemplo, `prod_`, `dev_`).

2. **Gestão de Mapeamentos**
    - Defina mapeamentos explícitos sempre que possível para controlar a estrutura dos dados e evitar mapeamentos dinâmicos indesejados.
    - Utilize tipos de dados apropriados para os campos (por exemplo, `keyword` para termos que não devem ser analisados, `text` para textos analisados).
    - Use `dynamic: false` ou defina mapeamentos específicos para evitar a criação automática de campos indesejados.

3. **Ajuste de Configurações de Índices**
    - Defina configurações adequadas para o número de shards e réplicas com base no tamanho dos dados e nas necessidades de desempenho.
    - Configure `index.lifecycle` para gerenciar automaticamente a criação, rotação e exclusão de índices antigos.

4. **Aliases de Índices**
    - Utilize aliases para facilitar a gestão de índices, especialmente para operações de reindexação e rotação de índices.
    - Crie aliases com nomes lógicos que não mudem, permitindo que o backend do Elasticsearch altere os índices físicos subjacentes sem impactar as consultas.

### Boas Práticas para IDs de Documentos

1. **IDs Automáticos vs IDs Personalizados**
    - Deixe o Elasticsearch gerar IDs automaticamente, a menos que tenha uma necessidade específica para IDs personalizados. IDs automáticos são gerados de forma eficiente e única.
    - Se usar IDs personalizados, certifique-se de que sejam únicos e de comprimento adequado para evitar colisões e garantir desempenho.

2. **Evite Reindexação Desnecessária**
    - Evite usar IDs personalizados que possam causar atualizações frequentes dos mesmos documentos, o que pode levar a reindexações desnecessárias e degradação do desempenho.

3. **Hashing de IDs**
    - Se precisar gerar IDs personalizados, considere usar uma função de hash para garantir unicidade e distribuição uniforme dos documentos entre os shards.

### Exemplo de Boas Práticas

Aqui está um exemplo de como aplicar algumas dessas boas práticas ao criar um índice e gerenciar documentos:

```go
package main

import (
	"bytes"
	"context"
	"encoding/json"
	"fmt"
	"log"
	"net/http"
	"regexp"

	"github.com/elastic/go-elasticsearch/v8"
	"github.com/elastic/go-elasticsearch/v8/esapi"
)

func isValidIndexName(name string) bool {
	if name == "" {
		return false
	}
	var validName = regexp.MustCompile(`^[a-z0-9._-]+$`)
	return validName.MatchString(name)
}

func main() {
	cfg := elasticsearch.Config{
		Addresses: []string{
			"http://localhost:9200",
		},
	}

	es, err := elasticsearch.NewClient(cfg)
	if err != nil {
		log.Fatalf("Erro ao criar o cliente Elasticsearch: %s", err)
	}

	indexName := "prod_explicitly_created_index"

	if !isValidIndexName(indexName) {
		log.Fatalf("Nome do índice '%s' é inválido", indexName)
	}

	reqExists := esapi.IndicesExistsRequest{
		Index: []string{indexName},
	}

	res, err := reqExists.Do(context.Background(), es)
	if err != nil {
		log.Fatalf("Erro ao verificar existência do índice: %s", err)
	}
	defer res.Body.Close()

	if res.StatusCode == http.StatusOK {
		fmt.Printf("Índice %s já existe.\n", indexName)
	} else if res.StatusCode == http.StatusNotFound {
		reqCreate := esapi.IndicesCreateRequest{
			Index: indexName,
			Body: bytes.NewReader([]byte(`{
				"settings": {
					"number_of_shards": 3,
					"number_of_replicas": 1
				},
				"mappings": {
					"properties": {
						"title": {"type": "text"},
						"content": {"type": "text"}
					}
				}
			}`)),
		}

		resCreate, err := reqCreate.Do(context.Background(), es)
		if err != nil {
			log.Fatalf("Erro ao criar índice: %s", err)
		}
		defer resCreate.Body.Close()

		if resCreate.IsError() {
			log.Fatalf("Erro ao criar índice. Status: %s", resCreate.Status())
		} else {
			fmt.Printf("Índice %s criado com sucesso.\n", indexName)
		}
	} else {
		log.Fatalf("Erro ao verificar existência do índice. Status: %s", res.Status())
	}

	doc := map[string]interface{}{
		"title":   "Document with explicit index creation",
		"content": "Elasticsearch will not create the index automatically",
	}

	var docBuf bytes.Buffer
	if err := json.NewEncoder(&docBuf).Encode(doc); err != nil {
		log.Fatalf("Erro ao codificar documento JSON: %s", err)
	}

	reqIndex := esapi.IndexRequest{
		Index:   indexName,
		Body:    &docBuf,
		Refresh: "true",
	}

	res, err = reqIndex.Do(context.Background(), es)
	if err != nil {
		log.Fatalf("Erro ao indexar documento: %s", err)
	}
	defer res.Body.Close()

	if res.IsError() {
		log.Fatalf("Erro ao indexar documento. Status: %s", res.Status())
	} else {
		fmt.Println("Documento indexado com sucesso.")
	}
}
```

### Explicação

1. **Nomeação do Índice**: O índice é nomeado com um prefixo `prod_` para indicar que é para produção.
2. **Criação de Índice**: Define configurações explícitas para o número de shards e réplicas.
3. **Verificação do Índice**: Verifica se o índice já existe antes de tentar criá-lo.
4. **Codificação e Envio do Documento**: O documento é codificado em JSON e enviado ao índice criado.

Essas práticas ajudam a garantir que o Elasticsearch funcione de maneira eficiente e escalável, mantendo a integridade dos dados e o desempenho do sistema.