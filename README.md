## SpringBoot 2.0.5 + Liquibase + postgres/h2 + actuator example
Пример простого SpringBoot сервиса включающего в себя Liquibase, postgreSQL, Actuator

### How to run?

    - Устанавливаем Docker Desktop
    - Загружаем образ postgres: docker pull postgres
    - Запускаем контейнер: docker run --rm   --name pg-docker -e POSTGRES_PASSWORD=docker -d -p 5432:5432 -v $HOME/docker/volumes/postgres:/var/lib/postgresql/data  postgres
    - Запускаем приложение в Intellij SpringBootLiquibaseApplication метод main

### Проверяем работоспрособность
    - Ссылка на актуатор  http://localhost:8080/actuator
    - Добавленная информация о приложении http://localhost:8080/actuator/info
    - GET запрос возращающий все книги http://localhost:8080/api/books

