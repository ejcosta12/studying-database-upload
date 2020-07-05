<h3 align="center">
  Importando arquivo CSV - PostgreSQL e NodeJS
</h3>

<p align="center">
  <img alt="GitHub language count" src="https://img.shields.io/github/languages/count/ejcosta12/studying-database-upload">
  <img alt="javaScript" src="https://img.shields.io/github/languages/top/ejcosta12/studying-database-upload">
  <img alt="Size" src="https://img.shields.io/github/repo-size/ejcosta12/studying-database-upload">
</p>

## Sobre
API desenvolvida para cadastro de transações em uma conta bancária, podendo ser entrada "income" ou saída "outcome", realizando atualização dos valores disponíveis e informando a soma de entradas, saídas, bem como o total. Caso for efetuada alguma operação de saída que ultrapasse o total disponível em conta, este sistema retorna um erro informando que não é possível ter saldo negativo. Para cadastro de transações é possível importar uma planilha, seguinte o arquivo modelo.csv disponível, que será interpretada e transformada em novos dados para a conta.

### Tecnologias

- NodeJs
- Express
- TypeORM
- PostgreSQL
- CSV Parse
- Multer
- Dotenv

### Scripts CLI

#### yarn
Instalação de todas as dependências necessárias.

#### yarn typeorm migration:run
Utilizando uma base de dados do postgreSQL com o nome de studying_database_upload, porta 5432 "para o desenvolvimento foi utilizado container Docker" execute o comando acima
e aguarde para que as migrations criem tabelas e configurações no banco. As configurações de conexão, como usuário e senha, podem ser vistas no arquivo ormconfig.json.

#### yarn dev:server
Inicialização do sistema pelo node, porta 3333.

#### Testes
Foram realizados testes utilizando o software insomnia, através das seguintes rotas:

- POST http://localhost:3333/transactions

Exemplo body(JSON):
```js
{
	"title": "Desenvolvimento de Sistema",
	"value": 6000,
	"type": "income",
	"category": "Salario"
}
```

- GET http://localhost:3333/transactions

- DELETE http://localhost:3333/transactions/:id

- POST http://localhost:3333/transactions/import

Exemplo body(Multipart Form):
```js
file: caminho\arquivo.csv
```
