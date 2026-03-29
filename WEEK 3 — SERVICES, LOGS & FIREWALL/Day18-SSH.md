## 🐧 Day 18 – SSH Mastery

### 🎯 Goal

Learn how to securely access remote systems using SSH and transfer files safely.

---

## 📚 Concepts Covered

* What is SSH (Secure Shell)
* Remote login
* Password vs key-based authentication
* Secure file transfer (SCP)
* Basic SSH troubleshooting

---

## 🌐 What is SSH?

SSH is a **secure protocol used to connect to remote systems over a network**.

👉 Uses encryption to protect:

* Credentials
* Data
* Commands

---

## ⚙️ Commands Used

```bash id="d18n1"
ssh user@server                # Remote login
scp file user@server:/tmp      # Copy file to remote server
```

---

## 🧪 LAB PRACTICE

### 🔹 Step 1: SSH Login

```bash id="d18n2"
ssh user@server-ip
```

### 📌 Output:

```bash id="d18o1"
user@server:~$
```

### ✅ Explanation:

* Connected to remote server
* Now working on remote machine

---

### 🔹 Step 2: Copy File to Remote Server

```bash id="d18n3"
scp test.txt user@server-ip:/tmp
```

### 📌 Output:

```bash id="d18o2"
test.txt 100%
```

### ✅ Explanation:

File successfully transferred

---

### 🔹 Step 3: Verify on Remote Server

```bash id="d18n4"
ssh user@server-ip
ls /tmp
```

### ✅ Explanation:

Confirms file exists on remote system

---

## 🔐 Key-Based Authentication (IMPORTANT 🔥)

### 🔹 Step 4: Generate SSH Key

```bash id="d18n5"
ssh-keygen
```

---

### 🔹 Step 5: Copy Key to Server

```bash id="d18n6"
ssh-copy-id user@server-ip
```

---

### 🔹 Step 6: Login Without Password

```bash id="d18n7"
ssh user@server-ip
```

### ✅ Explanation:

* No password required
* More secure and faster

---

## ⚠️ Common Issues + Fix

### ❌ Connection Refused

```bash id="d18e1"
ssh user@server-ip
```

### ✔ Fix:

```bash id="d18f1"
systemctl status ssh
sudo systemctl start ssh
```

---

### ❌ Permission Denied

```bash id="d18e2"
ssh user@server-ip
```

👉 Possible reasons:

* Wrong password
* Key not configured

---

### ✔ Fix:

```bash id="d18f2"
ssh-copy-id user@server-ip
```

---

### ❌ Port Blocked

👉 SSH uses port 22

---

### ✔ Check:

```bash id="d18f3"
ss -tuln | grep 22
```

---

## 🔥 Real-World Scenario (VERY IMPORTANT)

👉 Issue: “Cannot access server remotely”

Steps:

1. Check SSH service:

```bash id="d18r1"
systemctl status ssh
```

2. Check port:

```bash id="d18r2"
ss -tuln | grep 22
```

3. Try connection:

```bash id="d18r3"
ssh user@server-ip
```

---

👉 File transfer required:

```bash id="d18r4"
scp config.conf user@server-ip:/etc/
```

---

## 🔥 Proof of Learning

✔ Logged into remote system using SSH
✔ Transferred files using SCP
✔ Configured key-based authentication
✔ Verified secure access

👉 **Conclusion:**
I can securely access and manage remote Linux systems.

---

## 🧠 My Understanding

* SSH enables secure remote access
* SCP transfers files securely
* Key-based auth is more secure than passwords
* SSH issues can be due to service, port, or auth