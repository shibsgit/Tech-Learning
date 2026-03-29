## 🐧 Day 7 – Week 1 Review

### 🎯 Goal

Reinforce all Linux basics learned in Week 1 and ensure they feel natural and practical.

---

## 📚 Topics Covered (Week 1)

* Terminal & Navigation
* Directory Structure
* File Handling
* Viewing Files & Logs
* Permissions & Ownership
* Users & sudo

---

## ⚙️ Tasks

* Navigate filesystem
* Create and manage users
* Modify file permissions
* Read and monitor logs

---

## 🧪 LAB PRACTICE (COMBINED 🔥)

👉 Perform all tasks in one flow (real-world simulation)

---

### 🔹 Step 1: Navigate Filesystem

```bash id="s7n1"
pwd
cd /
ls
cd ~
```

### ✅ Objective:

* Move between root and home directory
* Understand structure

---

### 🔹 Step 2: Create and Switch User

```bash id="s7n2"
sudo useradd testuser
sudo passwd testuser
su - testuser
```

### ✅ Objective:

* Create new user
* Verify login

---

### 🔹 Step 3: File Handling

```bash id="s7n3"
touch test.txt
cp test.txt copy.txt
mv copy.txt prod.txt
ls
```

### ✅ Objective:

* Create, copy, rename files

---

### 🔹 Step 4: Modify Permissions

```bash id="s7n4"
chmod 644 test.txt
chmod 755 prod.txt
ls -l
```

### ✅ Objective:

* Understand permission structure

---

### 🔹 Step 5: Read Logs

```bash id="s7n5"
cat /etc/hosts
less /etc/passwd
```

### Optional (if permitted):

```bash id="s7n6"
sudo tail -f /var/log/syslog
```

### ✅ Objective:

* Read config files
* Monitor logs

---

## ⚠️ Common Issues + Fix

### ❌ Permission Denied

```bash id="s7e1"
ls /root
```

### ✔ Fix:

```bash id="s7f1"
sudo ls /root
```

---

### ❌ Command not found

```bash id="s7e2"
tree /
```

### ✔ Fix:

```bash id="s7f2"
sudo apt install tree
```

---

## 🔥 Real-World Scenario

👉 During troubleshooting:

1. Navigate to log directory
2. Check logs
3. Verify permissions
4. Switch user if needed

👉 This is exactly what NOC engineers do daily

---

## 🔥 Proof of Learning

✔ Navigated Linux filesystem confidently
✔ Created and switched users
✔ Managed files and permissions
✔ Read configuration files and logs

👉 **Conclusion:**
Linux basics now feel natural and I can perform daily tasks using CLI without hesitation.

---

## 🧠 My Understanding

* CLI is powerful and faster than GUI
* Linux is structured and predictable
* Permissions and users control security
* Logs are key for troubleshooting