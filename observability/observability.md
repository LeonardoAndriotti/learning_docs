# Observabilidade

## Pilares da observabilidade

A observabilidade é um conceito fundamental na engenharia de software e operações, que se refere à capacidade de entender o comportamento interno de um sistema com base em suas saídas externas. Existem três pilares principais da observabilidade:

### 1- Logs
**Descrição**: Logs são registros detalhados de eventos que ocorreram no sistema. Eles fornecem uma visão sequencial de eventos e são úteis para rastrear atividades específicas, identificar erros e entender o comportamento do sistema ao longo do tempo.

**Uso**: Ajuda na detecção de falhas, análise de problemas, e compreensão do fluxo de execução.

### 2- Métricas:

**Descrição**: Métricas são dados numéricos sobre o desempenho e a saúde do sistema. Elas geralmente são coletadas em intervalos regulares e podem incluir informações como uso de CPU, memória, tempo de resposta, número de solicitações, etc.

**Uso**: Fornece uma visão quantitativa do desempenho e da saúde do sistema, ajudando a identificar tendências, monitorar o desempenho em tempo real, e definir alertas para condições anômalas.

### 3- Traces (Rastreamento de Transações):
**Descrição**: Traces capturam o caminho completo de uma solicitação através de vários serviços ou componentes dentro de um sistema distribuído. Eles mostram como diferentes partes do sistema interagem e onde ocorrem atrasos ou falhas.

**Uso**: Útil para a análise de desempenho, identificação de gargalos, e compreensão das dependências entre serviços.

### Resumo dos Pilares da Observabilidade

* Logs: Detalhes de eventos e erros.
* Métricas: Dados quantitativos de desempenho e saúde.
* Traces: Caminho e performance de transações através do sistema.

Esses três pilares trabalham juntos para fornecer uma visão abrangente e detalhada do sistema, permitindo que os engenheiros identifiquem, diagnosticem e resolvam problemas de maneira eficiente. A integração desses pilares com ferramentas de monitoramento e análise é essencial para alcançar uma observabilidade eficaz.
