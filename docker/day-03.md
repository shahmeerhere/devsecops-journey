# 🐳 Day 03 - Docker (Ports & Networking)

## ✅ What I Did

* Learned how to expose containers using ports
* Understood how container networking works
* Created and used custom Docker networks
* Connected multiple containers together

---

## ⚙️ Commands Used

```bash id="d3cmds"
docker run -d -p 8080:80 nginx
docker ps

docker network ls
docker network create my-network

docker run -d --name nginx-container --network my-network nginx
docker run -d --name mysql-container --network my-network mysql
```

---

## 🧠 What I Learned

* Containers are isolated by default
* Port mapping (`-p host:container`) exposes services to the host machine
* Example: `8080:80` allows access via `localhost:8080`
* Docker networks allow containers to communicate internally
* Containers can talk using names instead of IPs inside a network

---

## 🚧 Problems Faced

* Unable to access container in browser initially
* Confusion between internal container ports and host ports
* Uncertainty about how containers communicate with each other

---

## ✅ Solution

* Verified running containers using `docker ps`
* Fixed port mapping format (`host:container`)
* Used Docker networks to connect containers properly
* Accessed services via correct `localhost:<port>`

---

## 📌 Next

* Learn Dockerfile and build custom images 🧱
