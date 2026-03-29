## 🐧 Day 26 – Containers Intro

### 🎯 Goal

Understand basic container concepts and how networking works inside containers.

---

## 📚 Concepts Covered

* What is a container
* Container vs Virtual Machine
* Running a container
* Port exposure (container networking)
* Basic Docker usage

---

## 🧠 What is a Container?

A container is a **lightweight, isolated environment to run applications**.

👉 Key points:

* Uses host OS kernel
* Faster than VMs
* Portable

---

## ⚙️ Commands Used

```bash id="d26n1"
docker run -d -p 8080:80 nginx   # Run container
docker ps                        # List running containers
```

---

## 🧪 LAB PRACTICE

### 🔹 Step 1: Install Docker (if not installed)

```bash id="d26n2"
sudo apt update
sudo apt install docker.io -y
```

---

### 🔹 Step 2: Start Docker Service

```bash id="d26n3"
sudo systemctl start docker
```

---

### 🔹 Step 3: Run Container

```bash id="d26n4"
sudo docker run -d -p 8080:80 nginx
```

### 📌 Explanation:

* `-d` → run in background
* `-p 8080:80` → map port

  * Host: 8080
  * Container: 80

---

### 🔹 Step 4: Check Running Containers

```bash id="d26n5"
docker ps
```

### 📌 Output (sample):

```bash id="d26o1"
CONTAINER ID   IMAGE   PORTS
abc123         nginx   0.0.0.0:8080->80/tcp
```

### ✅ Explanation:

* Container is running
* Port mapping visible

---

### 🔹 Step 5: Test Access

```bash id="d26n6"
curl http://localhost:8080
```

### 📌 Output:

```bash id="d26o2"
Welcome to nginx!
```

### ✅ Explanation:

Container service accessible via mapped port

---

## ⚠️ Common Issues + Fix

### ❌ Docker not running

```bash id="d26e1"
docker ps
```

### ✔ Fix:

```bash id="d26f1"
sudo systemctl start docker
```

---

### ❌ Permission Denied

```bash id="d26e2"
docker run ...
```

### ✔ Fix:

```bash id="d26f2"
sudo docker run ...
```

---

### ❌ Port already in use

```bash id="d26e3"
-p 8080:80
```

### ✔ Fix:

* Change port:

```bash id="d26f3"
-p 8081:80
```

---

## 🔥 Real-World Scenario (VERY IMPORTANT)

👉 Deploy web service using container:

```bash id="d26r1"
docker run -d -p 80:80 nginx
```

---

👉 Issue: “Service not accessible”

Check:

```bash id="d26r2"
docker ps
ss -tuln | grep 8080
```

---

## 🔥 Proof of Learning

✔ Ran container using Docker
✔ Verified running containers
✔ Checked exposed ports
✔ Accessed service via browser/curl

👉 **Conclusion:**
I understand container basics and how port mapping enables networking.

---

## 🧠 My Understanding

* Containers are lightweight environments
* Docker runs containers
* Ports connect container to host
* Networking is done via port mapping
* Containers simplify deployment