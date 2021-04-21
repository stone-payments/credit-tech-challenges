# **Aplicação de Console de Carteira de Investimentos**

Primeiramente, obrigado por topar este desafio. Desejamos que seja um processo de aprendizado para você.

### **Contexto**

Ativos financeiros representam a posse de um direito econômico que pode gerar lucro ao longo do tempo. Os ativos possuem preço, identificação, titular, tipo (ações, títulos do tesouro direto, títulos de CDB, etc...) e podem ser negociados no mercado financeiro dependendo da política de cada tipo. Também são conhecidos como &quot;papéis&quot; embora sejam títulos digitais intangíveis. Um ativo financeiro pode aumentar de rentabilidade ao longo do tempo, por exemplo, quem comprou uma ação da Stone (STNE) na bolsa da Nasdaq no dia 2 de novembro de 2020, pagou $52,95. Hoje esse mesmo ativo está valendo $69,33 representando uma rentabilidade de %30,93 para o titular.

Aplicativos de carteira de investimentos são muito comuns no mercado financeiro quando estamos falando do gerenciamento de ativos financeiros. A ideia é ajudar investidores a manterem sua lista de ativos comprados, rendimento, valor total por ativo, tipo de operação, etc…

### **Desafio**

Criar uma aplicação de carteira de investimentos que receba entradas e responda operações, funcionando pelo terminal de execução da aplicação (uma aplicação de console).

Você não precisa se preocupar em fazer uma API _web service_ ou persistir os dados de entrada informados pelo usuário num banco de dados, os dados podem ser mantidos em memória durante a execução do programa. É preciso informar um conjunto de dados que pode ser usado para testes.

Essa aplicação deverá suportar as operações descritas abaixo:

1. **Adicionar um novo ativo na carteira:**

    O usuário informa os dados de entrada contendo o código do ativo que foi comprado (ex.: STNE, GOOG, PGRM), quantidade de ativos e o valor pago por cada unidade do ativo

1. **Visualizar a lista de ativos investidos**

    Semelhante a um extrato bancário, esse comando deverá exibir uma lista de ativos investidos, informando código, preço de cada unidade do ativo, valor total alocado no ativo e data de compra.

1. **Informar a venda de um ativo**

    Esse comando servirá para informar a venda de um ativo. O usuário irá informar o código do ativo e quantas unidades ele vendeu. O usuário não deve conseguir vender ativos que não existem na carteira.

1. **Visualizar um resumo do valor total investido em todos os ativos e também o valor investido em cada ativo**

    Comando que deve exibir um resumo da carteira de investimentos do usuário. O objetivo é mostrar o valor total da carteira e o valor total alocado por ativos.

###


### **Requisitos**

- Utilização da linguagem de programação C# e o framework .NET Core 3.x
- Versionamento no Github
- Implementação de um menu numérico que apresenta todas as operações possíveis e também a opção de saída da aplicação. Esse menu será exibido na inicialização da aplicação
- Opção de retornar ao menu em todos os comandos

### **O que iremos avaliar**:

- Funcionalidade da aplicação
- Teste unitários
- Documentação dos comandos
- Validação de comandos

## **Entrega do desafio**

A entrega deverá ser feita através de um repositório público criado no Github contendo todo o seu código final na branch **main**. O link pode ser enviado para a pessoa que está tocando o seu processo seletivo. O time técnico irá fazer a avaliação e em seguida, iremos entrar em contato para dar um feedback em cima do seu desafio.

Te desejamos boa sorte :)