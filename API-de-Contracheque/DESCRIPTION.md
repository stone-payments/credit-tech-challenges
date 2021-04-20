# API de Contracheques

Primeiramente, obrigado por aceitar o desafio! Esperamos que a realização do mesmo seja proveitosa tanto para nossa avaliação como para você, aumentando sua capacidade de resolução de problemas ou até mesmo colocando mais um projeto em seu portfólio.

## Descrição do desafio

Na empresa existe um setor responsável pela contabilidade e pagamento de seus funcionários, entretanto, a parte contábil é realizada por uma consultoria externa. Gerir essas informações é algo bem importante e, dado que há uma confidencialidade no tráfego desses dados e também há uma possibilidade de economizar tirando essa consultoria do jogo, você foi escalado para criar uma aplicação responsável por criar o extrato da folha salarial dos funcionários. Esse extrato deve expôr o salário líquido do funcionário e todos os seus descontos discriminados.

## Especificação técnica do Desafio

1. A API tem como principal entidade o **Funcionário** , ele possui:

   1. Id
   2. Nome
   3. Sobrenome
   4. Documento (CPF válido)
   5. Setor
   6. Salário bruto
   7. Data de admissão
   8. Possui desconto no plano de saúde (bool)
   9. Possui desconto no plano dental (bool)
   10. Possui desconto de vale transporte (bool)

2.  Os descontos que o funcionário possui são

    1.  INSS (em cima do salário bruto):

    | Salário de Contribuição | Alíquota INSS |
    |:-----------------------|--------------:|
    |até 1.045,00|7,5%|
    |de 10.045,01 até 2.089,60|9%|
    |de 2.089,61 até 3.134,40|12%|
    |de 3.134,41 até 6.101,06|14%|

    **Obs:** Sabemos que o cálculo de INSS vigente usa um outro modelo de cálculo progressivo mas você não precisa contemplar isso. Pode se ater a esse cálculo na tabela acima com base no salário bruto para simplificar.

    2. Imposto de renda retido na fonte (em cima do salário bruto):

        |Base de cálculo (R$)|Alíquota (%) | Parcela a deduzir do IRPF (R\$)|
        |:-------------------|:-----------:|-------------------------------:|
        |Até 1.903,98|-|-|
        |De 1.903,90 até 2.826,65|7,5|142,80|
        |De 2.826,66 até 3.751,05|15|354,80|
        |De 3.751,06 até 4.664,68|22,5|636,13|
        |Acima de 4.664,68|27,5|869,36|

        i. A coluna "Parcela a deduzir do IR (R\$)" é o teto do desconto. Por exemplo, caso um funcionário tenha o salário bruto igual a R$ 5.000, a alíquota aplicada em cima do valor seria de 27.5% que resultaria em R$ 1.375 de desconto, porém, ele pagaria apenas o teto da alíquota, R$ 869,36.

    3. Plano de saúde (R$ 10 fixos em cima do salário bruto, se o funcionário optar pelo plano)
    4. Plano dental (R$ 5 fixos em cima do salário bruto, se o funcionário optar pelo plano)
    5. Vale transporte (6% em cima do salário bruto, se o funcionário optar pelo vale transporte)

        i. Caso o funcionário ganhe menos que R$ 1500, não há esse desconto

    1. FGTS (8% em cima do salário bruto)

3. Interações possíveis com um funcionário
   1. Deve ser possível fazer GET em um funcionário dado o seu Id, retornando a entidade
   2. Deve ser possível inserir um funcionário dados todos os seus dados, exceto Id, que deve ser gerado automaticamente. Esse Id deve vir na resposta da criação do funcionário

4. Extrato de contracheque
   1. Deve ser possível expor via endpoint o extrato de contracheque dado o Id de um funcionário
   2. Não há necessidade de persistir os dados do contracheque, ele pode ser construído em tempo de execução
   3. O contracheque deve ser capaz de expor
      1. Mês de referência
      2. Lista de lançamentos
      3. Salário bruto
      4. Total de descontos (Valor negativo)
      5. Salário líquido

   4. Um lançamento é composto da seguinte maneira:
      1. Tipo (Desconto, remuneração)
      2. Valor
      3. Descrição (Vale transporte, INSS, IRRF, etc)
5.  Considerações finais
    1. Faça um bom uso de recursos RESTful
    2. Persista a base de funcionários como você quiser (NoSQL, SQL).
    3. Use Programação Orientada a Objetos com sua linguagem de preferência (C# ou Java facilitariam nossa revisão)
    4.  Use frameworks com sabedoria, sem poluir seu código

## Avaliações que serão feitas

1. A aplicação tem que estar funcional e cumprir os requisitos que foram apresentados no desafio
2. Implementação e utilização de testes na aplicação
3. A forma que escreveu seu código
4. A organização do projeto
5. A utilização e a aplicação de patterns para os problemas que encontrou
6. A aplicação implementada e suas dependências têm que ser executáveis em qualquer ambiente e qualquer SO
7. Aplicação e suas dependências têm que ser inicializadas da forma mais prática possível
8. Documentação em geral (README, comandos de inicialização, endpoints da aplicação)
9. Utilização correta do controle de versionamento (Git, commits)
10. **<span style="color:red">Não é necessária qualquer implementação de interface front-end. Isso não será avaliado! Coloque seus esforços em deixar seu backend bem modelado.</span>**

## Bônus

- Hospedagem da API em algum serviço (sugerimos o [Heroku](https://www.heroku.com/))
- Hospedagem da imagem Docker da aplicação no [Dockerhub](https://hub.docker.com/)
- Criação de pipeline de CI/CD em algum serviço

Nos surpreenda.

## Entrega do desafio

A entrega deverá ser feita através de um repositório público criado no Github contendo todo o seu código final na branch **main**. O link pode ser enviado para a pessoa que está tocando o seu processo seletivo. O time técnico irá fazer a avaliação e em seguida, iremos entrar em contato para dar um feedback em cima do seu desafio.