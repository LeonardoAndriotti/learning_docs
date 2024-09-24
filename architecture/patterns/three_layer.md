# 3 Layers Architecture

## Regra de Ouro



Na Arquitetura de Três Camadas (Three-Layer Architecture), a “Regra de Ouro” refere-se ao princípio que afirma:

*“A camada de apresentação não deve depender diretamente da camada de acesso a dados.”*

### **Explicação:**
Camada de Apresentação (Presentation Layer):

Esta camada lida com a interação com o usuário e é responsável pela exibição dos dados e pela captura das entradas.

### **Camada de Lógica de Negócio (Business Logic Layer):**

Contém a lógica de aplicação e as regras de negócio. Atua como intermediária entre a camada de apresentação e a camada de acesso a dados.

### **Camada de Acesso a Dados (Data Access Layer):**

Responsável pela persistência dos dados e pela comunicação com o banco de dados ou outros sistemas de armazenamento.

### **Regra de Ouro:**
A camada de apresentação deve interagir apenas com a camada de lógica de negócios.
A camada de lógica de negócios deve ser responsável por interagir com a camada de acesso a dados.

Isso promove uma separação clara de responsabilidades e ajuda a garantir que a camada de apresentação permaneça desacoplada dos detalhes de implementação de persistência, facilitando a manutenção e a escalabilidade do sistema. Além disso, torna mais fácil realizar alterações na forma como os dados são armazenados ou recuperados sem impactar diretamente a camada de apresentação.


