
# Day 02 - Docker (Images & Containers)

## ✅ What I Did

- Worked with Docker images and containers  
- Learned how to manage container lifecycle  
- Practiced starting, stopping, and removing containers  

---

## ⚙️ Commands Used

```bash
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
````

---

## 🧠 What I Learned

* Images are templates used to create containers
* Containers can be started, stopped, and removed anytime
* `docker ps` shows running containers
* `docker ps -a` shows all containers
* Removing containers and images helps free system space

---

## 🚧 Problems Faced

* Confusion between stopping and removing containers
* Some containers stayed in exited state
* Error while removing an image that was being used by a container

---

## ✅ Solution

* Used `docker ps -a` to find all containers
* Stopped the running container using `docker stop <container_id>`
* Removed the container using `docker rm <container_id>`
* Then successfully removed the image using `docker rmi <image_id>`

---

## 📌 Next

* Learn about ports and container networking

```
```
