# Domain-Driven Design (DDD) 

No Domain-Driven Design (DDD), o conceito de Design Estratégico refere-se ao conjunto de práticas e padrões que ajudam a alinhar a arquitetura do software com o negócio, garantindo que as decisões técnicas sejam tomadas de acordo com a visão e os objetivos da organização.

O Design Estratégico foca em como dividir e organizar o domínio em várias partes, chamadas de Bounded Contexts (Contextos Delimitados), e como essas partes interagem entre si. Ele envolve:

Identificação de Bounded Contexts: Delimitar partes do domínio onde um modelo específico se aplica. Cada Bounded Context tem uma linguagem ubíqua e regras próprias.

Relacionamento entre Bounded Contexts: Definir como os Bounded Contexts se comunicam e colaboram. Isso pode incluir a utilização de padrões como Context Mapping para visualizar e planejar essas interações.

Context Mapping: Descreve as relações entre diferentes Bounded Contexts e define contratos claros entre eles, como Shared Kernel, Customer-Supplier, Conformist, entre outros.

Subdomínios: Identificação de subdomínios estratégicos (Core, Supporting, Generic) dentro do domínio de negócio para priorizar esforços de desenvolvimento e design.

Em resumo, o Design Estratégico ajuda a estruturar o sistema de forma que ele reflete a complexidade e os limites do domínio de negócio, facilitando a escalabilidade, manutenção e alinhamento com os objetivos organizacionais.

## Quando usar

* DDD é indicado para projetos complexos: Em projetos onde o domínio do negócio é complexo, com muitas regras, interações e casos de uso, o DDD proporciona uma estrutura metodológica que ajuda a gerenciar essa complexidade, organizando o projeto em Bounded Contexts e usando uma linguagem ubíqua.

*Não é necessário para todos os projetos: Em projetos mais simples, onde o domínio é bem compreendido e não possui muitas regras ou casos de uso complicados, a adoção de DDD pode ser excessiva e trazer uma sobrecarga desnecessária.

* Ajuda a alinhar software e negócios: DDD facilita a comunicação entre desenvolvedores e especialistas de domínio, garantindo que o software atenda com precisão às necessidades de negócio, especialmente em cenários onde essas necessidades são complexas e em constante evolução.

Em resumo, DDD é mais apropriado e traz mais valor quando o projeto envolve alta complexidade de domínio, onde as regras de negócio são críticas e onde há uma necessidade de um alinhamento forte entre o software e as expectativas do negócio.


## Design Tático

No Domain-Driven Design (DDD), o Design Tático se concentra em como implementar as soluções dentro de um Bounded Context. Ele abrange técnicas e padrões que ajudam a modelar o domínio e implementar a lógica de negócio de forma detalhada. Os principais elementos que fazem parte do Design Tático no DDD incluem:

* Entidades (Entities):

Objetos que possuem identidade e ciclo de vida próprios. São usados para modelar conceitos do domínio que precisam ser rastreados ao longo do tempo, como um cliente, um produto, ou um pedido.

* Objetos de Valor (Value Objects):

Objetos que não têm identidade própria e são imutáveis. Eles representam conceitos que são definidos apenas por seus atributos, como uma data, uma quantia em dinheiro ou uma coordenada geográfica.

* Agregados (Aggregates):

Conjunto de Entidades e Objetos de Valor que são tratados como uma única unidade de modificação. Cada Agregado tem uma raiz (Aggregate Root) que controla o acesso a suas partes internas e garante a consistência do conjunto.

* Repositórios (Repositories):

Interfaces para acessar e persistir Agregados. Repositórios encapsulam a lógica de persistência e fornecem métodos para buscar, salvar e remover Agregados do armazenamento.

* Serviços de Domínio (Domain Services):

Operações que não pertencem a uma única Entidade ou Objeto de Valor, mas que são essenciais para o domínio. Um Serviço de Domínio encapsula lógica de negócios que envolve múltiplas Entidades ou que não se encaixa bem em uma única Entidade.

* Fábricas (Factories):

Padrões para a criação de Entidades e Agregados complexos. Fábricas encapsulam a lógica de construção de objetos, especialmente quando a criação envolve múltiplos passos ou dependências.

* Módulos (Modules):

Agrupamentos lógicos de classes e componentes do domínio que compartilham uma função ou responsabilidade. Os Módulos ajudam a organizar o código e a manter a coesão dentro do Bounded Context.
Esses elementos compõem o Design Tático e são usados para criar um modelo de domínio detalhado que reflete as regras e os processos do negócio de maneira precisa e eficiente.


## Conceito de Agregados:
Agregado é um cluster de entidades e objetos de valor que são tratados como uma unidade única para operações de leitura e escrita.
Raiz do Agregado (Aggregate Root): A entidade principal dentro do agregado que controla o acesso e a integridade das outras entidades e objetos de valor dentro do agregado.
As operações de modificação de dados são realizadas através da raiz do agregado, garantindo consistência e encapsulamento das regras de negócios dentro do agregado.

## Qual é o proposito de eventos de domínio no DDD?

"São eventos que ocorrem no domínio do negócio e podem desencadear ações em outros contextos."

Justificativa:
Eventos de Domínio são usados para representar ocorrências significativas dentro do domínio de negócios. Eles refletem mudanças de estado ou ações que têm impacto sobre o modelo de domínio e podem ter consequências para outros contextos ou sistemas.

Propósitos dos Eventos de Domínio:

Comunicação: Eles permitem que diferentes partes do sistema ou diferentes sistemas se comuniquem sobre o que está acontecendo dentro do domínio.
Integração: Eles podem ser usados para integrar diferentes contextos delimitados, permitindo que ações em um contexto influenciem ou acionem mudanças em outros contextos.
Processamento Assíncrono: Permitem o processamento assíncrono ou eventual de tarefas relacionadas a eventos específicos do domínio.
As outras opções não são precisas no contexto dos eventos de domínio em DDD:

Eventos exclusivamente utilizados na camada de apresentação: Falso. Eventos de domínio são mais relacionados ao modelo de negócios e à lógica de domínio, não apenas à camada de apresentação.

Eventos específicos do sistema, como erros ou exceções: Falso. Eventos de domínio são sobre mudanças e ocorrências significativas no modelo de negócios, não sobre erros ou exceções técnicas.

Eventos de Domínio não têm um papel significativo no DDD: Falso. Eventos de domínio são um componente importante no DDD, ajudando a descrever e reagir a mudanças significativas no domínio de negócios.


