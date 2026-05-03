# 🐳 Day 04 - Docker (Dockerfile & Custom Images)

## ✅ What I Did

* Created my first Dockerfile
* Built a custom Docker image for a Node.js app
* Ran my own application inside a container
* Understood how Docker builds images step by step

---

## ⚙️ Commands Used

```bash id="d4cmds"
mkdir my-app
cd my-app

docker build -t my-custom-app .

docker images

docker run -d -p 5000:5000 my-custom-app

docker ps
docker logs <container_id>
```

---

## 🧾 Dockerfile Used

```dockerfile id="d4file"
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

* Dockerfile defines how an image is created step by step
* Each instruction creates a layer in the final image
* `FROM` sets the base environment
* `COPY` moves project files into the container
* `RUN` executes build-time commands
* `CMD` runs the application when container starts
* Custom images allow packaging real applications

---

## 🚧 Problems Faced

* Build failed due to missing files in context
* Confusion between `RUN` (build time) and `CMD` (run time)
* Container started but application didn’t respond

---

## ✅ Solution

* Ensured all project files were inside Docker build context
* Understood:

  * `RUN` → executes during image build
  * `CMD` → executes when container runs
* Used `docker logs` to debug container output

---

## 📌 Next

* Learn volumes and environment variables 💾
