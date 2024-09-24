# Clean Architecture

Clean Architecture, proposta por Robert C. Martin (conhecido como Uncle Bob), organiza o software em camadas concêntricas, onde cada camada tem uma responsabilidade específica e interage com as outras camadas de maneira controlada. As principais camadas de Clean Architecture são:

1. Entidades (Entities):
Localizadas no centro da arquitetura, as Entidades representam as regras de negócio mais gerais e de mais alto nível. Elas são independentes de qualquer aplicação específica e podem ser usadas em diferentes contextos do sistema.
Contêm os objetos de negócio e suas regras, como entidades e agregados no Domain-Driven Design (DDD).

2. Casos de Uso (Use Cases):
Essa camada contém a lógica de aplicação específica do sistema. Define o que deve ser feito em resposta a uma ação do usuário, mantendo o foco no comportamento do sistema.
Os Casos de Uso orquestram a interação entre as Entidades e os dados, garantindo que as regras de negócio sejam aplicadas corretamente.

3. Adaptadores de Interface (Interface Adapters):
Também conhecidos como adaptadores de entrada e saída, esses componentes convertem dados do formato mais conveniente para o uso nos Casos de Uso e Entidades para um formato adequado para a interface de usuário, bancos de dados, ou outras interfaces externas.
Incluem controladores, gateways, presenters e qualquer outro componente que faz a ponte entre a lógica de negócios e a infraestrutura ou a interface do usuário.

4. Frameworks e Drivers (Frameworks & Drivers):
Esta é a camada mais externa, onde residem os detalhes de implementação, como frameworks, bibliotecas, interfaces de usuário, bancos de dados, sistemas de arquivos, e outros componentes de infraestrutura.

É dependente de todas as outras camadas, mas não influencia as camadas internas. Essa camada pode ser facilmente substituída sem impactar as camadas internas.

Dependências
Uma regra fundamental da Clean Architecture é que as dependências devem sempre apontar para o centro, ou seja, camadas externas podem depender de camadas internas, mas nunca o contrário.
As camadas internas não devem ter dependências diretas com as camadas externas, o que garante a separação de preocupações e facilita a testabilidade e a manutenção do sistema.
Essa organização permite criar sistemas mais modulares, testáveis e adaptáveis, promovendo a independência da infraestrutura e a centralização das regras de negócio.


