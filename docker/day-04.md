# 📅 Day 04 - Docker (Dockerfile & Custom Images)

## ✅ What I Did

* Learned how to create a `Dockerfile`
* Built my own custom Docker image
* Understood image layers and build process
* Ran a container from my own image instead of pulling from Docker Hub

---

## ⚙️ Commands Used

```bash
mkdir my-app
cd my-app

# create Dockerfile
notepad Dockerfile

docker build -t my-custom-app .

docker images

docker run -d -p 5000:5000 my-custom-app
docker ps
```

---

## 🧾 Sample Dockerfile Used

```dockerfile
FROM node:18

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 5000

CMD ["npm", "start"]
```

---

## 🧠 What I Learned

* A Docker image is built step-by-step using layers
* Each instruction in Dockerfile creates a cached layer
* `FROM` defines base system (like OS + runtime)
* `COPY` moves files into container
* `RUN` executes commands during build time
* `CMD` runs when container starts
* Custom images let me package my own apps instead of relying on prebuilt ones

---

## 🚧 Problems Faced

* Build failed due to missing files in context
* Confusion between `RUN` vs `CMD`
* Container started but app didn’t respond

---

## ✅ Solution

* Made sure Dockerfile and project files were in same directory
* Learned:

  * `RUN` = build-time commands
  * `CMD` = runtime command
* Checked logs using:

```bash
docker logs <container_id>
```

---

## 📌 Next

* Docker volumes (data persistence)
* Environment variables in containers
* Multi-container setup (Docker Compose)
