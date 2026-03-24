### Hexlet tests and linter status:
[![Actions Status](https://github.com/sigilisd/devops-for-developers-project-74/actions/workflows/hexlet-check.yml/badge.svg)](https://github.com/sigilisd/devops-for-developers-project-74/actions) [![Push to Docker Hub](https://github.com/sigilisd/devops-for-developers-project-74/actions/workflows/push.yml/badge.svg)](https://github.com/sigilisd/devops-for-developers-project-74/actions/workflows/push.yml)

## Devops for Developers Project

Учебное веб-приложение на Node.js с запуском в Docker Compose.
В проекте используются сервисы `app`, `db` (PostgreSQL) и `caddy` для локальной разработки.

Docker Hub образ:
- https://hub.docker.com/repository/docker/sigilisd/devops-for-developers-project-74

## System Requirements

- Linux/macOS/WSL2
- Docker Engine + Docker Compose v2
- GNU Make

## Environment Variables

Проект конфигурируется через переменные окружения:

- `DATABASE_HOST`
- `DATABASE_NAME`
- `DATABASE_USERNAME`
- `DATABASE_PASSWORD`
- `DATABASE_PORT`

Локальная подготовка:

```bash
cp .env.example .env
```

## Make Commands

- `make setup` - подготовка приложения (установка зависимостей и инициализация)
- `make dev` - локальный запуск сервиса приложения через Docker Compose
- `make test` - запуск тестов в Docker Compose (production compose)
- `make ci` - CI-режим запуска тестов в Docker Compose

## Run Application

```bash
cp .env.example .env
make dev
```

После запуска:
- приложение доступно через `caddy` на `http://localhost`
- HTTPS доступно на `https://localhost`

## Run Tests

```bash
cp .env.example .env
make test
```

В CI тесты запускаются внутри Docker через команду `make ci` (workflow `.github/workflows/push.yml`).