id="q8m2zp"
# Day 03 - Docker (Ports & Networking)

## ✅ What I Did

- Learned how to expose containers to the host  
- Used port binding to access services  
- Explored basic Docker networking  

---

## ⚙️ Commands Used

```bash
docker run -d -p 8080:80 nginx
docker ps

docker network ls
docker network create my-network

docker run -d --name nginx-container --network my-network -p 8080:80 nginx
docker run -d --name mysql-container --network my-network mysql
````

---

## 🧠 What I Learned

* Containers are isolated and not accessible by default
* Port binding (`-p host:container`) exposes container to host
* Example: `8080:80` → access via localhost:8080
* Docker provides default networks
* Custom networks allow communication between containers

---

## 🚧 Problems Faced

* Could not access container in browser initially
* Confusion about port mapping

---

## ✅ Solution

* Checked running containers using `docker ps`
* Verified correct port binding using `-p`
* Accessed service using correct host port

---

## 📌 Next

* Learn Dockerfile and build custom images

```
```
