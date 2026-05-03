# 🐳 Day 02 - Docker (Images & Containers)

## ✅ What I Did

* Worked with Docker images and containers
* Learned how container lifecycle works
* Practiced starting, stopping, and removing containers
* Understood how Docker manages system resources

---

## ⚙️ Commands Used

```bash id="d2cmds"
docker images
docker ps
docker ps -a

docker run -d nginx
docker run -d mysql

docker stop <container_id>
docker start <container_id>

docker rm <container_id>
docker rmi <image_id>

docker system prune
```

---

## 🧠 What I Learned

* Images are templates used to create containers
* Containers are runtime instances of images
* `docker ps` shows running containers only
* `docker ps -a` shows all containers (running + stopped)
* Containers can be stopped and restarted anytime
* Removing containers/images helps free system resources

---

## 🚧 Problems Faced

* Confusion between stopping and removing containers
* Some containers stayed in exited state
* Error when removing images used by containers

---

## ✅ Solution

* Used `docker ps -a` to identify all containers
* Stopped running containers using `docker stop <container_id>`
* Removed containers using `docker rm <container_id>`
* Removed images only after detaching containers

---

## 📌 Next

* Learn about ports and container networking 🌐
