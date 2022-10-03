---
layout: post
title: "Як встановити PostgreSQL на MacOS за допомогою Homebrew"
categories: misc
---

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

Виправлення помилки: "FATAL: role "postgres" does not exist"

```shell
CREATE ROLE postgres WITH LOGIN PASSWORD 'postgres';
ALTER ROLE postgres CREATEDB;
```
