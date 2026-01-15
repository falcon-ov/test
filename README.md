# Go to Codespaces

1. Create an empty repository on GitHub
2. Go to Codespaces
   ![img](/image1.png)

# Run the ready-made image

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

# How to use

Just open port 3000 in Codespaces → a full Chromium browser will appear in your browser. You can browse as usual. All data (cookies, history) is stored inside the container as long as you don’t delete it.
![img](/image2.png)

# Useful commands for management

```bash
# View running containers
docker ps

# Stop the browser
docker stop browser

# Start again
docker start browser

# Remove the container completely
docker rm -f browser

# View logs (if something doesn’t work)
docker logs browser
```

# What if I closed the browser?

Method 1: Start the browser via the terminal inside the container (the simplest)

```bash
# Enter the container
docker exec -it browser bash

# Start Chromium and exit the container
chromium --no-sandbox & exit
```

Method 2: Restart the container

# Restart the container — Chromium will start automatically

```bash
docker restart browser
```

# Advantages of this option (browser in Codespaces):

✅ Nothing is installed on the work computer — no traces
✅ All traffic looks like work with Codespaces — normal development
✅ No proxy settings in the system — IT won’t see any changes
✅ Full isolation — everything happens remotely
✅ Easy to explain — “tested a web application in a container”
