# API - Projeto 1 do Módulo 4 BlueEdTech

Essa é uma API criada utilizando as aulas do Módulo 4 de Back End em NodeJS da BlueEdTech.

A idéia é criar um CRUD utilizando o framework NestJS, em um banco de dados relacional postgres.

Linguagem Utilizada: JavaScript / TypeScript

Banco de dados: Postgres

## Tabelas utilizadas

      O projeto possui três tabelas: Filmes, Generos e Participantes.
      O banco foi modelado seguindo a imagem abaixo:

![image](https://user-images.githubusercontent.com/55242537/144943617-1ae0338d-6102-4124-9322-d7ade6fccee6.png)

## Iniciando o aplicativo

    Em modo de desenvolvimento:
    npm run start:dev
    Em ambiente de produção:
    npm run start

## URL Base

    https://localhost:3000

## Listando todos os registros na tabela (GET)

        {urlBase}/filmes
        {urlBase}/generos
        {urlBase}/participantes

## Os retornos da aplicação estão no formato JSON, exemplo:

### Retorno de {urlBase}/filmes

        [{"id": 3,"nome": "teste","imagem": "teste","data_lancamento": "1970-01-01T00:00:00.000Z",
        "tempo_duracao": "1970-01-01T00:00:00.000Z"},{"id": 4,"nome": "Teste","imagem": "Teste",
        "data_lancamento": "2020-07-10T18:00:00.000Z","tempo_duracao": "2020-07-10T18:00:00.000Z"}]

## Listando objeto específico (GET)

### Deverá ser passado um parametro(nome) na rota _/{urlBase}/{tabela}/{id}_, exemplo:

        {urlBase}/filmes/1
        {urlBase}/generos/2
        {urlBase}/participantes/3
        Será retornado um objeto no formato JSON com os dados do banco.

## Adicionando novos objetos (POST)

### Para adicionar um novo objeto a alguma tabela do banco, deverá ser enviado um JSON para a rota correta, tendo os dados corretos, caso contrário a API retornará um erro. Campos abaixo marcados com "?" são opcionais.

#### Para adicionar um novo objeto na tabela **FILMES**:

      Rota: /filmes/
      Fomato JSON esperado: { "nome": String, "imagem": String?, "data_lancamento": string, "tempo_duracao": String }

#### Para adicionar um novo objeto na tabela **GENEROS**:

      Rota: /generos/
      Fomato JSON esperado: { "nome": String, "filmeId": Number }

#### Para adicionar um novo objeto na tabela **PARTICIPANTES**:

      Rota: /participantes/
      Fomato JSON esperado: { "nome": String, "imagem": String,
      "data_nascimento": String, "ator": Boolean, "staff": Boolean, "filmeId": Number }

### Caso exista algum problema com os dados do JSON enviado, a aplicação retornará um erro com detalhes.

### Caso o objeto seja adicionado com sucesso, a API retornará um JSON igual ao objeto adicionado ao banco.

## Atualizando um objeto (PATCH)

### Para atualizar uma linha de alguma tabela, deverá ser informado o ID do objeto na rota, e enviado um JSON com os novos valores através do método PATCH.

#### Para atualizar um novo objeto na tabela **FILMES**:

      Rota: /filmes/{id}
      Fomato JSON esperado: { "nome": String, "imagem": String?, "data_lancamento": string, "tempo_duracao": String }

#### Para adicionar um novo objeto na tabela **GENEROS**:

      Rota: /generos/{id}
      Fomato JSON esperado: { "nome": String, "filmeId": Number }

#### Para adicionar um novo objeto na tabela **PARTICIPANTES**:

      Rota: /participantes/{id}
      Fomato JSON esperado: { "nome": String, "imagem": String,
      "data_nascimento": String, "ator": Boolean, "staff": Boolean, "filmeId": Number }

### Caso o objeto seja atualizado com sucesso, a API retornará um JSON igual ao objeto atualizado no banco.

## Excluindo um objeto (DELETE)

### Para deletar um objeto de alguma tabela, deverá ser informado o ID do objeto na rota.

#### Para deletar um objeto na tabela **FILMES**:

      Rota: /filmes/{id}

#### Para deletar um objeto na tabela **GENEROS**:

      Rota: /generos/{id}

#### Para deletar um objeto na tabela **PARTICIPANTES**:

      Rota: /participantes/{id}

### Caso o objeto seja deletado com sucesso, a API retornará um JSON igual ao objeto deletado.
