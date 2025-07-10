# DDD - Domain - Driven Design

## 🚀 Introdução 

DDD ou domain-driven development são um conjunto de príncípios  para projetos de software, elaborados por Eric Evans  em 2003 focados no desenvolvimento de sistemas 
com design focado e alinhado ao domínio de negócio. 

O objetivo é garantir que desenvolvedores busquem informações junto aos especialistas no domínio (ou negócio) para o desenvolvimento de sistemas sem amarras técnicas
mas sim focados em atender às demandas que o negócio pede. DDD defende a separação entre domínio e tecnologia. Assim as arquiteturas em camadas, limpa e hexagonal podem
ser usadas para tal objetivo.

## 📓 Conceitos 
### Linguagem Ubiqua
Linguagem ubíqua são termos comuns tanto a desenvolvedores como aos especialista no domínio, possibilitando uma comunicação clara durante o ciclo de vida do sistema.
![linguagem-onipresente](https://github.com/user-attachments/assets/d32e526c-0565-43fe-8739-e07f3ba72f42)
Cópia da imagem de https://engsoftmoderna.info/artigos/ddd.html

Diagramas de classe de UML também fazem parte dessa linguagem, pois permitem entender as interações e relações entre os componentes do sistema.

### Objetos de domínio
Objetos de domínio foram projetados pensando em implementações baseadas em linguagens orientadas a objetos.
São eles: 
 - Entidades
 - Objetos de Valor
 - Serviços
 - Agregados
 - Repositorios

**Entidades e Objetos de Valor**
Entidade é um objeto que possui identidade única (Classe Livro). Possui ciclo de vida e persistência adequada,
já que uma entidade pode ter relações que existam apenas pela existência da entidade.
Objetos de valor não possuem identificador único (título do Livro), sendo caracterizados por seu estado(valores) 
Objetos de valor são imutáveis, ou seja, não são alterados, apenas excluídos e criados


**Serviços**
São operações importantes do domínio que não são entidades nem objetos de valor. Assim são stateless, não possuem estado, apenas métodos. São implementados como
**Singletons**; possuem apenas uma unica instâncio no sistema; para evitar inconsistências. 
Ex.: Serviços que envolvem 2 ou mais entidades. Não pertencem a nenhuma específica, assim se cria uma classe de serviços para acomodá-las.


**Agregados**
São coleções de entidade de objeto e valor, que não podem ser relacionadas de forma individual. 
Um agregado possui um objeto raiz  que deve ser uma entidade. Externamente, o agregado é acessado a partir da raiz. Apenas a raiz pode referenciá-los.
Por formar uma unidade coerente, o agregado é persistido no banco de dados. A deleção de um banco de dados implica na deleção de sua raiz e seus objetos internos
Por serem objetos complexos, devem ser criados a partir de uma factory, que são metodos específicos para a criação de entidades.
Exemplo do Site engsoftmoderna: 
Exemplo: No sistema de bibliotecas, um Empréstimo possui um Usuário (que é uma entidade) e uma lista de ItemEmpréstimo. Cada ItemEmpréstimo contém informações sobre um certo Livro que foi emprestado.
Logo, Empréstimo e ItemEmpréstimo formam um agregado, como mostrado na figura. Isto é, uma entidade única do ponto de vista conceitual. 
Empréstimo é a raiz do agregado e ItemEmpréstimo é a classe dos objetos internos, os quais não podem ser manipulados sem passar antes pela raiz.

**Repositório** 
Para implementar certos serviços do domínio é preciso antes obter referencias de determinados objetos. O repósitório é o objeto encarregado de buscar essas referencias
ou dados de forma segura. Em termos mais concretos, um repositório permite manipular objetos de domínio como se eles fossem listas (ou coleções) armazenadas na memória principal. 
A implementação interna do repositório cuida de ler e salvar essas listas no banco de dados. Aplica-se a entidades e agregados.

**Contextos Delimitados**
Para impedir que um sistema cresça indefinidamente, contextos são aplicados para se definir até onde o sistema atua, quais problemas resolve, mantendo o domínio
principal, onde também a linguagem ubíqua continua coerente. 

**Camada Anticorrupção**
Às vezes, temos que integrar sistemas que estão em contextos delimitados diferentes. Por exemplo, um sistema A precisa usar serviços de um sistema B, que pode inclusive ser um sistema externo, isto é, de uma outra organização. Para evitar que A tenha que se adaptar e usar, mesmo que parcialmente, a linguagem ubíqua de B, pode-se usar uma Camada Anticorrupção para mediar essa comunicação.

Essa camada é formada por três tipos principais de classes:

Classes de Serviço, cujos métodos serão chamados por A e que, portanto, seguem a linguagem ubíqua desse sistema.

Classes Adaptadoras, que convertem o modelo e os tipos de dados de B para o modelo e tipos de dados de A. Ou seja, essas classes vão isolar elementos próprios de B e evitar que eles cheguem até o sistema A.

Uma Classe de Fachada, usada para acessar o sistema B. O papel dessa classe é facilitar o uso de B, principalmente quando ele é um sistema legado com uma interface complexa e antiga.




