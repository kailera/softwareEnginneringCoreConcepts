# 🪨Princípio SOLID

## 1 - Princípio da Responsabilidade Única (SRP)

***Uma classe deve ter apenas um motivo para mudar***
Princípio da coesão (afinidade duncional dos elementos do módulo). A entidade conhece as regras 
de negócio, services e repositories estabelecem as conexões com banco e interfaces intermedeiam o 
fluxo de informações entre as entidades e o usuário final. Também podem ser definidas interfaces para 
regras de negócios específicas.


## 2 - Princípio do Aberto/Fechado (OCP)
***As entidades de software (classes, módulos, funções etc.) devem ser abertas para ampliação, mas 
fechadas para modificação***
De forma mais detalhada, diz que podemos estender o comportamento de uma classe, 
quando for necessário, por meio de herança, interface e composição,
mas não podemos permitir a abertura dessa classe para fazer pequenas modificações. A ideia é enxugar
as classes e interfaces de modo que elas implementem módulos, mas não modificações.

## 3 - Princípio da Substituição de Liskov (LSP)
***Os subtipos devem ser substituíveis pelos seus tipos base***
Mesmo a herança sendo um mecanismo poderoso, ela deve ser utilizada de forma 
contextualizada e moderada, evitando os casos de classes serem estendidas apenas por
possuírem algo em comum. Esse princípio foi descrito pela pesquisadora Barbara Liskov, 
em seu artigo de 1988, em que ela explica que, antes de optar pela herança, 
precisamos pensar nas pré-condições e pós-condições da sua classe.
Atendendo o princípio OCP, o ideal é encapsular tarefas compartilhadas por 2 entidades e deixar que 
elas cuidem apenas das regras de negócio.


## 4 - Princípio da Segregação de Interfaces (ISP)
***Muitas interfaces específicas são melhores que uma interface geral***
Trata da coesão de interfaces, com poucos comportamentos, que são mais fáceis de manter e evoluir.

## 5 - Princípio da Inversão de Dependências (DIP)
***Depender de abstrações e não de classes concretas*** 
Há ainda dois sub-itens:
- Módulos de alto nível não devem depender de módulos de baixo nível
- As abstrações não devem depender de detalhes, os detalhes devem depender de abstrações
A ideia é evoluir classes concretas (os detalhes).



Artigo de apoio: https://mari-azevedo.medium.com/princ%C3%ADpios-s-o-l-i-d-o-que-s%C3%A3o-e-porque-projetos-devem-utiliz%C3%A1-los-bf496b82b299

