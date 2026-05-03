# 📅 Day 06 - Docker Compose (Multi-Container Setup for AppTrackr)

## ✅ What I Did

* Converted my AppTrackr backend setup into a multi-container system
* Ran **backend + MongoDB + PostgreSQL** together using Docker Compose
* Learned how services communicate inside a shared network
* Replaced manual `docker run` commands with one `docker-compose up`

---

## 🧱 System I Built

My AppTrackr stack:

* Backend (Node.js / Express)
* MongoDB (for document data)
* PostgreSQL (for relational data)

Instead of running them separately, I connected everything using **Docker Compose**

---

## ⚙️ `docker-compose.yml`

```yaml id="apptrackr_compose"
version: "3.8"

services:

  backend:
    build: .
    container_name: apptrackr-backend
    ports:
      - "5000:5000"
    depends_on:
      - mongo
      - postgres
    environment:
      MONGO_URL: mongodb://mongo:27017/apptrackr
      POSTGRES_URL: postgres://postgres:password@postgres:5432/apptrackr
    networks:
      - app-network

  mongo:
    image: mongo
    container_name: mongo-db
    ports:
      - "27017:27017"
    networks:
      - app-network

  postgres:
    image: postgres
    container_name: postgres-db
    environment:
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: password
      POSTGRES_DB: apptrackr
    ports:
      - "5432:5432"
    networks:
      - app-network

networks:
  app-network:
```

---

## 🚀 Commands Used

```bash id="compose_run"
docker-compose up -d

docker-compose ps

docker-compose logs backend

docker-compose down
```

---

## 🧠 What I Learned (REAL IMPORTANT PART)

### 🔗 1. Containers talk using service names

Instead of:

```
localhost:27017
```

Inside Docker:

```
mongo:27017
```

👉 Because Docker DNS resolves service names automatically.

---

### 🌐 2. Everything runs in one network

* `app-network` connects all containers
* No manual IP handling needed
* Containers behave like they are in same private LAN

---

### ⚡ 3. Depends_on is startup order (not wait-for-ready)

* Backend starts after DB containers
* BUT databases might still be initializing
* So real apps need retry logic in backend

---

### 📦 4. One command = full system

Instead of:

```bash
docker run backend
docker run mongo
docker run postgres
```

Now:

```bash
docker-compose up
```

👉 This is exactly how real projects are deployed locally or in CI/CD pipelines.

---

## 🚧 Problems Faced

* Backend couldn’t connect to MongoDB initially
* Used `localhost` instead of service name (`mongo`)
* Confused why Postgres connection failed even though container was running

---

## ✅ Solution

* Fixed connection strings:

  * ❌ `localhost`
  * ✅ `mongo` / `postgres`

* Understood Docker networking abstraction layer

---

## 📌 Key Insight

> Multi-container systems are not about running multiple containers — they are about **making them behave like one unified application system**

---

## 📌 What You Actually Achieved Here

With AppTrackr now:

✔ Backend isolated but connected
✔ Databases fully containerized
✔ System reproducible anywhere
✔ No manual setup required

---

## 📌 Next (Day 07 Preview)

Now you move into:

🔥 **Production thinking**

* Docker volumes in Compose (real persistence)
* Health checks
* Restart policies
* Basic CI/CD mindset
