## 🚪Ports & Adapters 🔌

## O que é?
Padrão arquitetônico usado em design de software, que busca separar o domínio da aplicação da tecnologia a ser aplicada, fraco acoplamento entre os componentes e separação 
de responsabilidades. 

## Explicação 
Alistar Cockburn buscava um design que ajudasse a evitar problemas com a modelagem de sistemas orientados a objetos, como a alta dependência entre as entidades e a exibição
de regras de negócio na interface de usuário. Assim ele definiu uma arquitetura hexagonal, onde as faces do hexagono representam as portas e adaptadores. 

## O que são as portas e adaptadores?
Portas são as conexões pelas quais cada componente da aplicação se comunica entre si, principalmente via mensageria. 
Adapters é como as informações transitam de dentro para fora e vice-versa pela aplicação. Há o hexagono interno, que representa o núcleo, ou domínio da aplicação
e o hexagono externo, que possui os módulos (com suas portas) e as faces para o mundo exterior, representando os adapters, com interfaces de usuário e de dados.

<img width="1024" height="1024" alt="image" src="https://github.com/user-attachments/assets/2a9bd4bc-03da-4a6e-b677-0fd54fd6821c" />

