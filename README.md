## SpringBoot 2.0.5 + Liquibase + security + postgres/h2 + actuator example
Пример простого SpringBoot сервиса включающего в себя Liquibase, postgreSQL, Actuator

### How to run?

    - Устанавливаем Docker Desktop
    - Загружаем образ postgres: docker pull postgres
    - Запускаем контейнер: docker run --rm   --name pg-docker -e POSTGRES_PASSWORD=docker -d -p 5432:5432 -v $HOME/docker/volumes/postgres:/var/lib/postgresql/data  postgres
    - Запускаем приложение в Intellij SpringBootLiquibaseApplication метод main

Наполнение пользователями по умолчанию
```sql
INSERT INTO roles (id, name)
VALUES (1, 'ROLE_ADMIN'),
       (2, 'ROLE_ACTUATOR'),
       (3, 'ROLE_USER')
;

INSERT INTO users (id, email, password, name)
VALUES (1, 'admin@gmail.com', '$2a$10$hKDVYxLefVHV/vtuPhWD3OigtRyOykRLDdUAp80Z1crSoS1lFqaFS', 'Admin'),
       (3, 'user@gmail.com', '$2a$10$ByIUiNaRfBKSV6urZoBBxe4UbJ/sS6u1ZaPORHF9AtNWAuVPVz1by', 'User');

insert into user_role(user_id, role_id)
values (1, 1),
       (1, 2),
       (1, 3),
       (3, 2)
;
```
### Проверяем работоспособность
    - Логин/пароль: admin@gmail.com/admin ; user@gmail.com/user
    - Ссылка на актуатор  http://localhost:8080/actuator
    - Добавленная информация о приложении http://localhost:8080/actuator/info
    - GET запрос возращающий все книги http://localhost:8080/api/books
    
    

