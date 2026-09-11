#  Kittygram (контейнеры и CI/CD с помощью GitHub Actions)

[![Build Status](https://github.com/russinArtem/kittygram_final/actions/workflows/main.yml/badge.svg)](https://github.com/russinArtem/kittygram_final/actions/workflows/main.yml)
[![Python version](https://img.shields.io/badge/python-3.12-blue)](https://www.python.org/downloads/release/python-312/)

## Описание проекта

**Kittygram** — это социальная сеть для обмена фотографиями любимых питомцев. Проект позволяет пользователям:
- регистрироваться и авторизовываться в системе;
- загружать фотографии своих питомцев;
- указывать информацию о них: кличка, год рождения, окраска, достижения;
- просматривать ленту с фотографиями питомцев всех пользователей.

## Стек технологий

- **Backend:** Python, Django, PostgreSQL;
- **Frontend:** HTML, CSS, JavaScript (React);
- **Контейнеризация:** Docker, Docker Compose;
- **CI/CD:** GitHub Actions;
- **Деплой:** Nginx (в качестве шлюза/прокси).

## Как развернуть проект

1. Клонируйте репозиторий на локальный компьютер;
2. Создайте файл .env в корне проекта и заполните его (см. раздел ниже);
3. Запустите контейнеры с помощью команды <docker-compose -f docker-compose.production.yml up -d>;
4. Откройте проект в браузере по адресу, указанному в файле tests.yml.

## Как заполнить файл .env

1. В корне проекта создайте файл .env;
2. Укажите в файле переменные из файла .env.example;
3. В .env присвойте переменным свои актуальные значения.

## Как проверить работу с помощью автотестов

В корне репозитория создайте файл tests.yml со следующим содержимым:
```yaml
repo_owner: ваш_логин_на_гитхабе
kittygram_domain: полная ссылка (https://доменное_имя) на ваш проект Kittygram
taski_domain: полная ссылка (https://доменное_имя) на ваш проект Taski
dockerhub_username: ваш_логин_на_докерхабе
```

Скопируйте содержимое файла `.github/workflows/main.yml` в файл `kittygram_workflow.yml` в корневой директории проекта.

Для локального запуска тестов создайте виртуальное окружение, установите в него зависимости из backend/requirements.txt и запустите в корневой директории проекта `pytest`.

## Чек-лист для проверки перед отправкой задания

- Проект Taski доступен по доменному имени, указанному в `tests.yml`.
- Проект Kittygram доступен по доменному имени, указанному в `tests.yml`.
- Пуш в ветку main запускает тестирование и деплой Kittygram, а после успешного деплоя вам приходит сообщение в телеграм.
- В корне проекта есть файл `kittygram_workflow.yml`.

## Автор

russinArtem, yandex-praktikum
