# Node homework 16
Docker, Travis, Heroku

### Разворачивание проекта:

1) Создаем файл `.env` по типу `.env.example`
2) Запускаем `npm i` для установки зависимостей
4) Запускаем `npm start`

### Докеризация

Сборка Docker-образа: `docker build -t konstantin-shilov/node-dth .` <br>
Запуск образа: `docker run -p 8000:4000 -d <repository_name>` <br>
Запуск образа с добавлением имени контейнера, по которому можно будет к нему обращаться: `docker run -p 8000:4000 -d --name <container_name> <repository_name>` <br>
Отображение логов приложения: `docker logs <container name/id>` <br>
Вход в контейнер в интерактивном режиме: `docker exec -it <container name/id> /bin/bash` <br>
Остановка процесса: `docker stop <container name/id>` <br>

#### Вспомогательные команды

- `docker images` - все образы
- `docker ps --all` - все контейнеры
- `docker rm <container-name> --force` - остановка и удаление контейнера

### Travis

#### Инициализация
Зарегистрироваться на `https://travis-ci.com/`. Создать `.travis.yml`

#### Настройка CLI
- Команда `gem install travis`. На mac этой командой не получилось, поэтому использовал `brew install travis`
- Логин `travis login --pro`

После получения токена авторизации в Heroku командой `travis encrypt <token>` создается `api_key` для деплоя. <br>
По умолчанию travis смотрит на `api.travis-ci.org`. Для того, что бы достучаться до `api.travis-ci.com` необходимо воспользоваться `travis encrypt --pro <token>`.

### Heroku

#### Инициализация
- `npm install -g heroku`
- `heroku login -i`
- `heroku authorizations:create` - получение бессрочного токена
  - `heroku auth:token` - если нужен токен со сроком действия

#### Приложение
`https://node-16.herokuapp.com/`