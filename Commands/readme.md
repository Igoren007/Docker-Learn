Команды в контейнере
```bash
docker exec [params] [name] [command]
```
* **i** - интерасктивно
* **t** - псевдо tty
* **d** - запуск в фоне
* **e** - переменные окружения
* **u** - пользователь
* **w** - рабочая директория

Примеры:

Путь к текущей директории в контейнере:
```bash
sudo docker exec -w /root my_app_3 pwd
```
Передать переменную окружения и увидеть  ее в списке:
```bash
sudo docker exec -e MYVAR=123 my_app_3 printenv
```
Bash внутри контейнера:
```bash
sudo docker exec -it my_app_3 bash
```
Команда внутри контейнера:
```bash
sudo docker exec my_app_3 bash -с "ls"
```
Удалить запущенный контейнер my_container:
```bash
docker rm my_container -f
```

Записать вывод команды в файл:
```bash
sudo docker exec my_app_3 uptime > text.txt
```




Список volums:
```bash
docker volume ls
```

Создать volume:
```bash
docker volume create v1
```
Volums хранятся по пути:
```bash
/var/lib/docker/volumes/
```

Потребление ресурсов контейнером:
```bash
docker stats
```

Информация о контейнере:
```bash
docker inspect <name>
```

Просмотр конкретного параметра контейнера:
```bash
docker inspect -f "{{.State.Status}}" <name>
```

Просмотр логов:
```bash
docker logs <name>
