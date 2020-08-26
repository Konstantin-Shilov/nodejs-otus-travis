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
