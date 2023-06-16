<p align="center">
    <h1><strong>Desafios Técnico do crédito</strong></h1>
</p>
<p align="center">
    <img width=20% src="StoneLogo.png">
</p>

![StoneSDK](https://cloud.githubusercontent.com/assets/2567823/11539067/6300c838-990c-11e5-9831-4f8ce691859e.png)

# Desafio Backend

O desafio consiste em criar uma API REST que permite salvar e ler comentários (similar a posts em um blog).

Tecnologias que devem ser utilizadas:
- .Net Core (C#) para Web API
- OpenAPI para documentação da API
- SQL Server ou MongoDB para persistecia
- RabbitMQ para mensageria
- Docker para ambiente de execução (componentes de infra estrutura e API)

# Funcionalidades

A API deve expor dois endpoints:

1 - Recebe  um comentário e salva no banco de dados de maneira assícrona
2 - Permite a consulta dos comentários salvos de maneira paginada, permitindo filtro pelo autor do comentário. 


### POST `/comment

Ao receber um comentário, o endpoint deve validar se os campos foram devidamente preenchidos. 
Caso algum campo esteja vazio o endpoint retorna status 400 (BadRequest) informando quais campos estão inválidos.
Caso todos os campos sejam válidos, o endpoint retorna status 202 (Accepted) e envia para uma fila do RabbitMQ uma mensagem com os dados que devem ser adicionados ao banco de dados.

Deve existir um processo em background que processa as mensagens eviadas para o RabbitMQ e salva no banco de dados os comentários.
Esse processo pode ser executado pela própria WebAPI ou em um outro projeto de aplicação separado.

####Request Body:

```json
{
   "content":"Meu comentário",
   "author": "Pedro" 
}
```
| Campo       | Tipo   |
|-------------|--------|
| content     | string |
| author      | string |



### GET `/comments?page_size=10&author=Pedro&page_number=1
Esse método da API deve retornar o seguinte JSON
```json
{
	"items": [
		{
			"content": "Meu comentário",
			"author": "Pedro"     
		}
	],
    page_number: 1,
	page_size: 10,
	page_count: 1
}
```

Caso dados de páginação sejam inválidos o endpoint deve retornar status 400 (BadRequest)
Filtro de autor deve ser opcional. E caso não seja econtrado nenhum item para o autor informado, deve ser retornado um array vazio.

| Campo       | Tipo      |
|-------------|-----------|
| items       | comment[] |
| page_number | int       |
| page_size   | int       |
| page_count  | int       |

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
