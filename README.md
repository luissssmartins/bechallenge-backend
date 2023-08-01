# Desafio Web (React JS + Django)

Este repositório contém os arquivos necessários e o código fonte para rodar o back-end requerido pelo desafio proposto pela beAnalytic.

# Backend

No back-end, foi utilizando Django, um framework de python extremamente robusta e escalável.

Rotas disponíveis nesta API:

`GET: http://127.0.0.1/api/tasks` (Esta rota está responsável por listar todas as tarefas cadastradas no banco de dados)

`POST: http://127.0.0.1/api/tasks` (Esta rota está responsável por cadastrar a tarefa no banco de dados)

`PUT: http://127.0.0.1/api/tasks/<id>` (Esta rota está responsável por realizar alguma alteração no estado da tarefa, seja concluir/reabrir ou até mesmo modificar o seu contéudo, bem como nome ou descrição)

`DELETE: http://127.0.0.1/api/tasks/<id>` (Esta rota está responsável por deletar por completo a tarefa com ID enviado)

#Parâmetros

Para realizar requisições, o formato de envio deve seguir o modelo abaixo:

```bash

{
    "name": "<nome_da_tarefa>",
    "description": "<descrição da tarefa>",
    "status": <true ou false>
}

```

# Compilando e executando o back-end

Para realizar a execução, é necessário tomar alguns passos, dentre eles, primeiramente vamos realizar as migrações do banco de dados utilizado:

```bash
$ python3 manage.py makemigrations
```

Depois, realize a migration por inteiro:

```bash
$ python3 manage.py migrate
```

Agora, basta executar e rodar a API:

```bash
$ python3 manage.py runserver
```

# Configuração do banco de dados (Postgre SQL)

No arquivo `settings.py`, localizado dentro de "bechallenge_backend", procure por:

```bash

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'bechallenge',
        'USER': 'app',
        'PASSWORD': 'beanalytic',
        'HOST': 'localhost',
        'PORT': '',
    }
}

```

E realize as alterações para que a API rode e se conecte com o banco de dados pré-estabelecido.

