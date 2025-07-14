# Clean Architeture

## Introdução
Clean Architecture tem como objetivo padronizar e harmonizar o código desenvolvido priozando a qualidade e manutenção do código, independente da tecnologia. Dá destaque ao domínio e ao uso do sistema, a preservação das regras internas e comunicação dessas com as tecnologias de desenvolvimento e interação com o usuário.

<img width="772" height="567" alt="image" src="https://github.com/user-attachments/assets/1f9abecf-7b98-4000-adc7-fdcd44ff2291" />

## Camadas

### Entidades ou Enterprise Business Rules
É a camada mais interna e fundamental da Clean Architecture, abrigando as regras de negócio e as entidades centrais principais da aplicação, junto com as principais regras de negócios. Entidades e regras são independentes de tecnologia. 

### Application Business Rules
Acima da camada de entidade, define todos os casos de uso e gerencia o fluxo da aplicação. Os casos de uso implementados são responsáveis por orquestrar a interação entre as entidades do domínio. Essa camada atua como um intermediário entre a interface de usuário e o domínio.

### Interface Adapters
Para o transito seguro das informações persistidas pelas entidades para a visualização e uso pelo usuário é necessário a implementação de interfaces, que mantêm as camadas mais internas protegidas de tecnologias externas. Essa camada fica entre a camada de negócios e as camadas mais externas como a interface de usuário.

### Frameworks e drivers
Detalhes técnicos da implementação (stack, front/backend, etc)

