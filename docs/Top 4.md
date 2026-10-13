# Top 4 Características Arquiteturais

## Segurança

### Contexto

O único atributo de qualidade mencionado no documento de requisitos se refere à segurança: "o sistema deve permitir o acesso ao sistema apenas por usuários
cadastrados". Além disso, o sistema trabalha com dados sensíveis, como CPF, endereço, dados do cartão de crédito, entre outros.

### Decisão

Considerar tal característica uma das 4 mais relevantes.

### Alternativas consideradas

Nenhuma, devido à suma importância desta característica (conforme a justificativa a seguir).

### Justificativa

Esta é a característica mais importante, pois conforme o contexto apresentado, o sistema lida com dados sensíveis. Além disso, o próprio documento de requisitos ressalta a relevância dessa característica.

### Consequências

- Sistema mais confiável e menos propenso a causar prejuízos financeiros aos usuários.
- Aumento da complexidade do código e do workflow do projeto.

---
## Auditabilidade
### Contexto

O Veridt lida com operações de pagamento, armazenamento de dados de usuários, registros de conteúdos e geração de relatórios.

### Decisão

Considerar tal característica uma das 4 mais relevantes.

### Alternativas consideradas

Nenhuma, porque também se trata de uma característica central.

### Justificativa

Via de regra, é exigido que serviços que lidam com operações financeiras sejam transparentes. Logo, é importante garantir que os dados envolvidos com os pagamentos sejam adequadamente verificáveis pelos usuários, para que eles fiquem a par de como seu dinheiro está sendo utilizado. Ao mesmo tempo, é importante que os administradores tenham a capacidade de verificar tais informações para lidar com eventuais problemas no banco de dados, bugs ou mesmo complicações jurídicas. 

Além disso, a proposta central do Veridt é permitir que os usuários verifiquem que determinados acontecimentos sejam provados reais a partir de registros. Logo, é preciso que as fontes de informação sobre eles (os conteúdos da aplicação) sejam devidamente auditáveis para comprovar a veracidade dos acontecimentos.

Tais características também se relacionam com a transparência que o documento de requisitos pretende aplicar por meio dos relatórios e detalhes, que buscam permitir a verificação dos dados e de seus históricos.

### Consequências

- Adequação do Veridt ao seu propósito de livre acesso aos conteúdos registrados, bem como à garantia de sua veracidade.
- Aumento da segurança e confiabilidade no uso da aplicação.
- Custo adicional devido ao armazenamento de um grande volume de informações.

---
## Confiabilidade e Tolerância a Falhas
### Contexto


### Decisão


### Alternativas consideradas


### Justificativa


### Consequências

---
## Disponibilidade
### Contexto


### Decisão


### Alternativas consideradas


### Justificativa


### Consequências