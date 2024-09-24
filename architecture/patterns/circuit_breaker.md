**Circuit Breaker** é um padrão de design utilizado em sistemas distribuídos, especialmente em arquiteturas baseadas em microserviços, para aumentar a resiliência e confiabilidade. Ele é inspirado em disjuntores elétricos, que interrompem o fluxo de eletricidade quando há sobrecarga, prevenindo danos maiores.

Em sistemas de software, o Circuit Breaker é usado para **proteger a aplicação contra falhas repetidas ou demoradas** ao tentar acessar serviços externos ou dependências instáveis. Ele age como uma proteção, evitando que múltiplas chamadas falhem de maneira contínua, o que pode sobrecarregar os recursos e prejudicar o desempenho geral.

### Como o Circuit Breaker funciona:

O Circuit Breaker tem três estados principais:

1. **Fechado (Closed)**:
   - O estado normal, em que as chamadas para o serviço ou recurso externo são permitidas.
   - Se as respostas são bem-sucedidas, o circuito permanece fechado.
   - Quando as chamadas começam a falhar repetidamente, um contador é incrementado até que um limite seja atingido.

2. **Aberto (Open)**:
   - Quando o número de falhas atinge um limite configurado, o Circuit Breaker entra no estado "Aberto".
   - Nesse estado, novas tentativas de acessar o serviço são **imediatamente rejeitadas**, evitando novas chamadas ao serviço problemático.
   - As chamadas falham rapidamente, poupando tempo e recursos, sem esperar por timeouts.

3. **Meio-Aberto (Half-Open)**:
   - Após um período de tempo (timeout), o Circuit Breaker permite uma pequena quantidade de chamadas de teste para verificar se o serviço externo se recuperou.
   - Se as chamadas de teste forem bem-sucedidas, o circuito volta para o estado "Fechado".
   - Se falharem novamente, o circuito retorna ao estado "Aberto".

### Benefícios do Circuit Breaker:
- **Prevenção de sobrecarga**: Impede que um serviço sobrecarregado ou com falhas cause uma cascata de falhas em outros serviços que dependem dele.
- **Recuperação rápida**: Em vez de tentar incessantemente acessar um serviço falho, ele rapidamente retorna um erro, permitindo que a aplicação lide com o problema de maneira eficiente.
- **Isolamento de falhas**: Protege o sistema geral ao isolar problemas de um serviço específico.

### Exemplo de uso:

Imagine que sua aplicação web depende de um serviço externo de pagamento. Se o serviço de pagamento começar a ter problemas, cada tentativa de chamada pode falhar e demorar muito, afetando o desempenho da sua aplicação.

Usando o padrão Circuit Breaker, você pode:
- Definir um limite de 5 falhas consecutivas.
- Se o serviço de pagamento falhar 5 vezes, o Circuit Breaker abre e impede novas tentativas de serem feitas por, digamos, 30 segundos.
- Após esse período, ele entra no estado "Meio-Aberto" e testa o serviço novamente. Se estiver funcional, o circuito volta ao estado "Fechado"; caso contrário, retorna ao estado "Aberto".

### Ferramentas populares que implementam Circuit Breaker:
- **Netflix Hystrix** (agora descontinuado, mas ainda amplamente usado).
- **Resilience4j** (substituto mais moderno do Hystrix).
- **Polly** (biblioteca .NET para resiliência de falhas). 

Em suma, o Circuit Breaker é um componente essencial para garantir a resiliência e evitar falhas em cascata em sistemas complexos e distribuídos.