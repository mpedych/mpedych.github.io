---
layout: post
title: "Як встановити PostgreSQL на MacOS"
categories: misc
---

# За допомогою Homebrew
Встановлення:

```shell
brew install postgresql
```

Запуск:

```shell
brew services start postgresql
```

Зупинка:

```shell
brew services stop postgresql
```

Підключення до сервера БД:

```shell
psql postgres
```

Виправлення помилки: 
>"FATAL: role "postgres" does not exist"

```shell
CREATE ROLE postgres WITH LOGIN PASSWORD 'postgres';
ALTER ROLE postgres CREATEDB;
```

# За допомогою Docker

Встановлення:
```shell
docker run --name pg-16.1 -p 5432:5432 -e POSTGRES_PASSWORD=12345 -d postgres:16.1
```
