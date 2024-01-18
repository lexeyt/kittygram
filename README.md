# Kittygram

![example workflow](https://github.com/github/docs/actions/workflows/main.yml/badge.svg)

Учебный проект для ведения базы котов, котиков и кошек:

## Возможности
- Регистрация на сайте
- Добавление новых котов
- Указание года рождения и цвета
- Загрузка фотографий
- Просмотр всех котов

## Технологии
- Django 3.2.3
- djangorestframework 3.12.4
- djoser 2.1.0
- webcolors 1.11.1
- psycopg2-binary 2.9.3
- Pillow 9.0.0
- pytest 6.2.4
- pytest-django 4.4.0
- pytest-pythonpath 0.7.3
- PyYAML 6.0
- gunicorn 20.1.0
- Docker
- PostgreSQL

## Особенности
Проект выполнен с применением технологии контейнеризации: каждая функциональная часть преокта упакована в отдельный контейнер и разворачивается автоматически с помощью docker-compose.
Это позволяет запускать проет независимо от внешнего окружения операционной системы. Для работы приложения требуется только ядро операционной системы хоста, а необходимый набор системных библиотек содержится непосредственно в файловой системе контейнера.

Кроме этого, такой подход позволяет реалализовать концепцию CI/CD:
- каждый коммит в мастер ветку автоматически проверяется тестами
- в случае успешного прохождения тестов новый код автоматиески деплоится на сервер.

## Развернутый проект
https://kittygram.redirectme.net/

## Запуск проекта на Linux
### Установка Docker
Выполните команды:
```sh
sudo apt update
sudo apt install curl
url -fSL https://get.docker.com -o get-docker.sh 
sudo sh ./get-docker.sh
```
Для сборки так же требуется утилита Docker Compose:
```sh
sudo apt install docker-compose-plugin 
```
Официальная документация по установке: https://docs.docker.com/engine/install/ubuntu/

### Сборка проекта
- Клонируйте репозиторий и настройте параметры окружения
- Соберите образы и отправьте их в Docker Hub
- Скопируйте файл docker-compose.production.yml в корневую папку проекта
- Запустите оркестр с помощью docker compose

#### Полезные команды Docker
Аутентификация в Docker Hub:
```sh
docker login -u username 
```
Сборка образа:
```sh
docker build -t image_name . 
```
Отправка образов в Docker Hub:
```sh
docker push username/image_name:latest
```
Запуск всех описанных в docker-compose.yml контейнеров:
```sh
docker compose up
```
Запуск всех описанных в docker-compose.yml контейнеров в фоновом режиме:
```sh
docker compose up -d
```
Остановка всех контейнеров:
```sh
docker compose stop
```
Остановка и удаление всех контейнеров:
```sh
docker compose down
```
Остановка и удаление всех контейнеров и volume:
```sh
docker compose down -v
```
Если файл называется не docker-compose.yml, то в каждой команде после compose нужно
указывать параметр -f имя_файла.


## Автор

Тачеев Алексей
