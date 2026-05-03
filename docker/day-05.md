# 📅 Day 05 - Docker (Volumes + Environment Variables + Persistence)

## ✅ What I Did

* Learned how to persist data using Docker volumes
* Understood environment variables in containers
* Ran containers that keep data even after restart
* Prepared basics for multi-container systems

---

## ⚙️ Commands Used

```bash
docker run -d -p 3306:3306 \
  -e MYSQL_ROOT_PASSWORD=root \
  -e MYSQL_DATABASE=testdb \
  --name mysql-db \
  mysql

docker volume ls

docker volume create my-volume

docker run -d \
  -v my-volume:/var/lib/mysql \
  --name mysql-persistent \
  mysql
```

---

## 🧠 What I Learned

### 📦 1. Volumes (MOST IMPORTANT)

* Containers are temporary
* Without volumes → data is LOST when container is removed
* Volumes = permanent storage outside container lifecycle

👉 Example:

* MySQL data stored in `/var/lib/mysql`
* If mapped with volume → data survives restart/delete

---

### 🔐 2. Environment Variables

* Used to configure containers without changing code
* Passed using `-e`

Example:

```bash
-e MYSQL_ROOT_PASSWORD=root
-e MYSQL_DATABASE=testdb
```

👉 This is how real systems configure DBs, APIs, and services dynamically.

---

### 🔁 3. Persistence Concept

* Container = runtime
* Volume = memory disk
* Without volume → stateless system
* With volume → real backend system behavior

---

## 🚧 Problems Faced

* Data disappeared after container restart (initial confusion)
* Didn’t understand where MySQL stores data internally
* Mixed up container removal vs volume removal

---

## ✅ Solution

* Learned difference:

  * `docker rm` → removes container only
  * volume stays unless explicitly deleted

* Fixed persistence using:

```bash
-v volume_name:/path/in/container
```

---

## 📌 Key Insight

> Real backend systems are useless without persistence volumes are what turn Docker from “toy containers” into real infrastructure.

---

## 📌 Next (Day 06 Preview)

Now things get serious:

### 🔥 Docker Compose

* Run multiple containers together (like backend + DB)
* One command to start full system
* Real-world app architecture
