# Зайдите в codespaces
1. Создайте пустой репозиторий на github
2. Зайдите на codespaces
![img](/image.png)

# Запустите готовый образ

```bash
docker run -d \
  --name browser \
  -p 3000:3000 \
  -p 3001:3001 \
  -e PUID=1000 \
  -e PGID=1000 \
  -e TZ=Europe/Vienna \
  --shm-size="2gb" \
  lscr.io/linuxserver/chromium:latest
```

# Как пользоваться
Просто откройте порт 3000 в Codespaces → появится полноценный Chromium браузер в вашем браузере. Можете серфить как обычно. Все данные (cookies, история) сохраняются внутри контейнера, пока вы его не удалите.

# Полезные команды для управления

```bash
# Посмотреть запущенные контейнеры
docker ps

# Остановить браузер
docker stop browser

# Запустить снова
docker start browser

# Удалить контейнер полностью
docker rm -f browser

# Посмотреть логи (если что-то не работает)
docker logs browser
```