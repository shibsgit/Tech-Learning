## 🐧 Day 28 – Security Basics

### 🎯 Goal

Learn how to harden a Linux system by securing SSH access and protecting against brute-force attacks.

---

## 📚 Concepts Covered

* What is system hardening
* SSH security best practices
* Root login risks
* Brute-force attack prevention
* Introduction to Fail2Ban

---

## 🔐 What is System Hardening?

System hardening means:
👉 **Reducing vulnerabilities and securing the system against attacks**

---

## ⚙️ Tasks

* Disable root SSH login
* Install and configure Fail2Ban

---

## ⚙️ Commands Used

```bash id="d27n1"
sudo nano /etc/ssh/sshd_config
sudo systemctl restart ssh
sudo apt install fail2ban
systemctl status fail2ban
```

---

## 🧪 LAB PRACTICE

---

### 🔹 Step 1: Disable Root SSH Login

Open SSH config:

```bash id="d27n2"
sudo nano /etc/ssh/sshd_config
```

---

### 🔹 Step 2: Modify Configuration

Find:

```bash id="d27n3"
PermitRootLogin yes
```

Change to:

```bash id="d27n4"
PermitRootLogin no
```

---

### 🔹 Step 3: Restart SSH Service

```bash id="d27n5"
sudo systemctl restart ssh
```

### ✅ Explanation:

Root login via SSH is now disabled

---

## 🔐 Why Disable Root Login?

* Root has full access
* Attackers target root account
* Safer to use normal user + sudo

---

### 🔹 Step 4: Install Fail2Ban

```bash id="d27n6"
sudo apt update
sudo apt install fail2ban -y
```

---

### 🔹 Step 5: Check Fail2Ban Status

```bash id="d27n7"
systemctl status fail2ban
```

### 📌 Output:

```bash id="d27o1"
Active: active (running)
```

### ✅ Explanation:

Fail2Ban is protecting the system

---

## 🛡️ What is Fail2Ban?

Fail2Ban:
👉 Monitors logs and **blocks suspicious IPs**

Example:

* Multiple failed SSH attempts → IP banned

---

### 🔹 Step 6: Verify Jail (SSH Protection)

```bash id="d27n8"
sudo fail2ban-client status sshd
```

### 📌 Output:

```bash id="d27o2"
Status for the jail: sshd
```

---

## ⚠️ Common Issues + Fix

### ❌ Locked Out from SSH

👉 Disabled root login without user access

---

### ✔ Fix:

* Ensure normal user has sudo
* Test before logout

---

### ❌ Fail2Ban not running

```bash id="d27e1"
systemctl status fail2ban
```

---

### ✔ Fix:

```bash id="d27f1"
sudo systemctl start fail2ban
```

---

### ❌ No protection working

👉 Logs not monitored

---

### ✔ Fix:

```bash id="d27f2"
journalctl -u fail2ban
```

---

## 🔥 Real-World Scenario (VERY IMPORTANT)

👉 Issue: “Server under brute-force attack”

Steps:

1. Check logs:

```bash id="d27r1"
journalctl -u ssh
```

2. Fail2Ban blocks attacker automatically

---

👉 Issue: “Unauthorized access risk”

✔ Disable root login
✔ Use secure authentication

---

## 🔥 Proof of Learning

✔ Disabled root SSH login
✔ Installed Fail2Ban
✔ Verified protection status
✔ Understood brute-force prevention

👉 **Conclusion:**
I can secure Linux servers against common attacks.

---

## 🧠 My Understanding

* Security is critical for production systems
* Root login should be disabled
* Fail2Ban protects against attacks
* Logs help detect threats
* Hardening reduces risk