# **Carteira de Investimentos**

Primeiramente, obrigado por topar este desafio. Desejamos que seja um processo de aprendizado para você!

### **Contexto**

Ativos financeiros representam a posse de um direito econômico que pode gerar lucro ao longo do tempo. Os ativos possuem preço, identificação, titular, tipo (ações, títulos do tesouro direto, títulos de CDB, etc...) e podem ser negociados no mercado financeiro dependendo da política de cada tipo. Também são conhecidos como &quot;papéis&quot; embora sejam títulos digitais intangíveis. Um ativo financeiro pode aumentar de rentabilidade ao longo do tempo, por exemplo, quem comprou uma ação da Stone (STNE) na bolsa da Nasdaq no dia 2 de novembro de 2020, pagou $52,95. Hoje esse mesmo ativo está valendo $69,33 representando uma rentabilidade de %30,93 para o titular.

Aplicativos de carteira de investimentos são muito comuns no mercado financeiro quando estamos falando do gerenciamento de ativos financeiros. A ideia é ajudar investidores a manterem sua lista de ativos comprados, rendimento, valor total por ativo, tipo de operação, etc…

### **Desafio**

Com o intuito de operar uma carteira de investimentos, onde deve-se receber entradas e responder operações, você deverá criar uma aplicação que exponha suas funcionalidades através de uma API:

1. Endpoint de persistência de recursos (ativos, operações de compra e venda)

2. Endpoint de listagem e busca de recursos (ativos na carteira, valor consolidado, histórico de operações de compra e venda)

A API pode ter os dados persistidos e mantidos em memória durante a execução. Persistir os dados num banco de dados seria um plus/bônus.

Essa aplicação deverá suportar as operações descritas abaixo:

1. **Adicionar um novo ativo na carteira:**

    O usuário informa os dados de entrada contendo o código do ativo que foi comprado (ex.: STNE, GOOG, PGRM), quantidade de ativos e o valor pago por cada unidade do ativo

2. **Visualizar a lista de ativos investidos**

    Semelhante a um extrato bancário, esse comando deverá exibir uma lista de ativos investidos, informando código, preço de cada unidade do ativo, valor total alocado no ativo e data de compra.

3. **Informar a venda de um ativo**

    Esse comando servirá para informar a venda de um ativo. O usuário irá informar o código do ativo e quantas unidades ele vendeu. O usuário não deve conseguir vender ativos que não existem na carteira.

4. **Visualizar um resumo do valor total investido em todos os ativos e também o valor investido em cada ativo**

    Comando que deve exibir um resumo da carteira de investimentos do usuário. O objetivo é mostrar o valor total da carteira e o valor total alocado por ativos.

### **Requisitos**

- Use Programação Orientada a Objetos com sua linguagem de preferência (C# ou Java facilitariam nossa revisão)
- Versionamento no Github
- Disponibilizar um endpoint para cada operação possível. Respeitando as especificações de cada verbo HTTP. Sugerimos a utilização da arquitetura REST.

### **O que iremos avaliar**:

- A aplicação tem que estar funcional e cumprir os requisitos que foram apresentados no desafio
- Implementação e utilização de testes na aplicação
- Documentação em geral (README, comandos de inicialização, endpoints da aplicação)
- Utilização correta do controle de versionamento (Git, commits)
- **Não é necessária qualquer implementação de interface front-end (página web), apenas a aplicação rodando numa aplicação console. Implementação de interface front-end não será avaliada! Coloque seus esforços na aplicação console e na API**

## **Bonus**

- Entrada e saída de dados da API serialiados no formato JSON
- Uso de algum Framework para documentação da API
- Persistência dos dados em um banco de dados

## **Entrega do desafio**

A entrega deverá ser feita através de um repositório público criado no Github contendo todo o seu código final na branch **main**. O link pode ser enviado para a pessoa que está tocando o seu processo seletivo. O time técnico irá fazer a avaliação e em seguida, iremos entrar em contato para dar um feedback em cima do seu desafio.

Te desejamos boa sorte :)