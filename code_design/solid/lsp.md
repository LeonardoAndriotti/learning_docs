# Liskov Substitution Principle

O Princípio da Substituição de Liskov (Liskov Substitution Principle - LSP) afirma que, em uma hierarquia de classes, as subclasses devem ser substituíveis por suas superclasses sem alterar o comportamento correto do programa. Se a substituição de uma classe base por uma classe derivada causar comportamentos inesperados, isso indica uma violação do LSP.

## Alguns exemplos de violação do LSP:

* Métodos que lançam exceções inesperadas:

Se uma subclasse lança uma exceção que a classe base não lança, ao substituir a classe base pela subclasse, o código cliente pode falhar ao não esperar essa exceção.

* Mudança de contrato (pré-condições ou pós-condições):

Se uma subclasse impõe pré-condições mais restritivas ou pós-condições diferentes das da classe base, ela viola o contrato esperado, resultando em uma violação do LSP. Por exemplo, se a subclasse espera um intervalo de valores diferente daquele esperado pela classe base.

* Modificação de comportamento observável:

Se a subclasse modifica o comportamento de um método de forma que altera significativamente o resultado esperado, quebrando a lógica do programa. Por exemplo, uma subclasse que ignora parte da funcionalidade ou altera os efeitos colaterais esperados.

* Retorno de tipos diferentes ou inválidos:

Se uma subclasse retorna tipos diferentes dos especificados pela classe base ou um valor que não faz sentido dentro do contexto da classe base, isso constitui uma violação. Por exemplo, uma subclasse que retorna null onde a classe base sempre retorna um valor válido.

* Quebra de invariante:

Invariantes são condições que devem ser mantidas como verdadeiras para garantir o estado correto de um objeto. Se uma subclasse quebra essas invariantes ao ser usada no lugar da classe base, ela viola o LSP.

Esses exemplos mostram situações em que as subclasses não se comportam como suas superclasses de forma intercambiável, levando a problemas de manutenção e confiabilidade no código.

