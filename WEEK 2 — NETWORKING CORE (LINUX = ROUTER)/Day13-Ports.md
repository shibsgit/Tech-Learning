## 🐧 Day 13 – Ports & Services

### 🎯 Goal

Understand how services use ports and how to identify which service is running on which port.

---

## 📚 Concepts Covered

* What is a port
* What is a service
* Listening ports
* TCP vs UDP
* Mapping services to ports

---

## 🌐 What is a Port?

A port is a **logical endpoint for network communication**.

Examples:

* 22 → SSH
* 80 → HTTP
* 443 → HTTPS

---

## ⚙️ Commands Used

```bash id="d13n1"
ss -tuln        # Show listening ports
lsof -i :22     # Show process using port 22
```

---

## 🧪 LAB PRACTICE

### 🔹 Step 1: Check Listening Ports

```bash id="d13n2"
ss -tuln
```

### 📌 Output (sample):

```bash id="d13o1"
tcp   LISTEN  0  128  0.0.0.0:22
tcp   LISTEN  0  128  0.0.0.0:80
udp   UNCONN  0  0    0.0.0.0:68
```

### ✅ Explanation:

* `tcp` / `udp` → protocol
* `LISTEN` → service is active
* `:22` → port number

---

### 🔹 Step 2: Identify Service Using Port

```bash id="d13n3"
lsof -i :22
```

### 📌 Output (sample):

```bash id="d13o2"
sshd   1234  root  TCP *:22 (LISTEN)
```

### ✅ Explanation:

* `sshd` → service name
* `1234` → process ID (PID)
* `root` → owner

---

## ⚠️ Common Issues + Fix

### ❌ lsof command not found

```bash id="d13e1"
lsof -i :22
```

### ✔ Fix:

```bash id="d13f1"
sudo apt install lsof
```

---

### ❌ Port not listening

```bash id="d13e2"
ss -tuln | grep 22
```

👉 No output → service not running

---

### ✔ Fix:

```bash id="d13f2"
sudo systemctl start ssh
```

---

### ❌ Port already in use

👉 Service fails to start

---

### ✔ Check:

```bash id="d13f3"
lsof -i :80
```

👉 Identify conflicting service

---

## 🔥 Real-World Scenario (VERY IMPORTANT)

👉 Issue: “SSH not working”

Steps:

1. Check port:

```bash id="d13r1"
ss -tuln | grep 22
```

2. If not listening:

```bash id="d13r2"
sudo systemctl start ssh
```

3. Verify process:

```bash id="d13r3"
lsof -i :22
```

---

👉 Issue: “Web server not accessible”

Check:

```bash id="d13r4"
ss -tuln | grep 80
```

---

## 🔥 Proof of Learning

✔ Checked listening ports using `ss -tuln`
✔ Identified service using specific port
✔ Verified service owner and PID

👉 **Conclusion:**
I can identify which service is running on which port and troubleshoot service issues.

---

## 🧠 My Understanding

* Ports are endpoints for services
* Each service listens on specific port
* `ss` shows active ports
* `lsof` maps port to process
* Troubleshooting starts from checking ports