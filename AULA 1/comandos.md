# Fullstack FullCycle - Aula 1

### Descrição

Todos os comandos utilizados na aula 1 do curso.

#

### Tecnologias

- Nest (Typescript e Node)
- Docker
- MySQL
- Prisma

<details>
  <summary>Observação</summary>
  <br>
  
  **É recomendado utilizar as seguintes extensões do VSCode:**
  
  - ESLint
  - Prettier
  - Prisma
  - REST Client
</details>

#

### Índice da aula:

<details>

  <br>

  <summary>Comandos Nest</summary>

- Instalar globalmente o Nest:

  ```bash
  npm install -g @nestjs/cli
  ```

- Cria um projeto:

  ```bash
  nest new NOME_DO_PROJETO
  ```

- Cria um modelo de controller:

  ```bash
  nest generate controller NOME_DA_CONTROLLER
  ```

- Cria um CRUD:

  ```bash
  # Será perguntado o nome do CRUD e tipo de transporte durante a execução do comando
  nest g resource
  ```

</details>

<details>

  <br>

  <summary>Comandos Docker</summary>

- Criar arquivo docker-compose.yaml

  ```yaml
  version: '3.8'

  services:
    db:
      image: mysql:8.0.30-debian
      environment:
        MYSQL_ROOT_PASSWORD: root
        MYSQL_DATABASE: nest
      ports:
        - '3306:3306'
  ```

- Inicializar o Docker após configurar o arquivo YAML:

  ```bash
  docker-compose up
  ```

- Manipulação do bash Docker:

  ```bash
  docker compose exec db bash
  ```

- Acessar o MySQL dentro do bash:

  ```bash
  # Acesse o MySQL utilizando o usuário 'root' e a senha configurada no YAML como MYSQL_ROOT_PASSWORD
  mysql -uroot -proot
  ```

- Visualizar os bancos de dados no MySQL:

  ```mysql
  # Visualiza todos os bancos de dados existentes, incluindo o definido no YAML como MYSQL_DATABASE
  show databases;
  ```

</details>

<details>

  <br>

  <summary>Comandos Prisma</summary>

- Cria um prisma schema e .env:

  ```bash
  npx prisma init
  ```

- Configurar o .env :

  ```ts
  //Configure o URL do banco de dados com as variáveis definidas no YAML, como MYSQL_ROOT_PASSWORD, ports e MYSQL_DATABASE
  DATABASE_URL = 'mysql://root:SENHA@localhost:PORTA/NOME_DO_BANCO';
  ```

- Migra o schema para o banco:

  ```bash
  npx prisma migrate dev
  ```

</details>

#

### Documentações:

- [NestJS](https://docs.nestjs.com/)
- [Docker](https://docs.docker.com/)
- [Prisma](https://www.prisma.io/docs)
