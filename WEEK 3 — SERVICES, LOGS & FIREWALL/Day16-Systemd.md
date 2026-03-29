## 🐧 Day 16 – systemd Services

### 🎯 Goal

Learn how to manage system services using `systemctl` and recover failed services.

---

## 📚 Concepts Covered

* What is a service
* What is **systemd**
* Service states (active, inactive, failed)
* Starting, stopping, restarting services
* Basic service troubleshooting

---

## ⚙️ Commands Used

```bash id="d16n1"
systemctl status ssh     # Check service status
systemctl restart ssh    # Restart service
```

---

## 🧠 What is systemd?

* `systemd` is the **service manager** in modern Linux
* It controls background services (daemons)

Examples:

* ssh → remote login
* nginx → web server
* docker → container service

---

## 🧪 LAB PRACTICE

### 🔹 Step 1: Check Service Status

```bash id="d16n2"
systemctl status ssh
```

### 📌 Output (sample):

```bash id="d16o1"
● ssh.service - OpenSSH Server
   Active: active (running)
```

### ✅ Explanation:

* `active (running)` → service is working
* Shows service details

---

### 🔹 Step 2: Restart Service

```bash id="d16n3"
sudo systemctl restart ssh
```

---

### 🔹 Step 3: Verify Again

```bash id="d16n4"
systemctl status ssh
```

### 📌 Output:

```bash id="d16o2"
Active: active (running)
```

### ✅ Explanation:

Service restarted successfully

---

### 🔹 Step 4: Stop Service (Test Failure)

```bash id="d16n5"
sudo systemctl stop ssh
```

---

### 🔹 Step 5: Check Status

```bash id="d16n6"
systemctl status ssh
```

### 📌 Output:

```bash id="d16o3"
Active: inactive (dead)
```

---

### 🔹 Step 6: Recover Service

```bash id="d16n7"
sudo systemctl start ssh
```

---

## ⚠️ Common Issues + Fix

### ❌ Permission Denied

```bash id="d16e1"
systemctl restart ssh
```

### ✔ Fix:

```bash id="d16f1"
sudo systemctl restart ssh
```

---

### ❌ Service Not Found

```bash id="d16e2"
systemctl status ssh
```

👉 Service name may differ:

* `ssh`
* `sshd`

---

### ✔ Fix:

```bash id="d16f2"
systemctl list-units --type=service
```

---

### ❌ Service Failed

```bash id="d16e3"
Active: failed
```

---

### ✔ Fix:

```bash id="d16f3"
sudo systemctl restart ssh
```

👉 Check logs if needed:

```bash id="d16f4"
journalctl -u ssh
```

---

## 🔥 Real-World Scenario (VERY IMPORTANT)

👉 Issue: “SSH not working”

Steps:

1. Check service:

```bash id="d16r1"
systemctl status ssh
```

2. If stopped:

```bash id="d16r2"
sudo systemctl start ssh
```

3. If failed:

```bash id="d16r3"
sudo systemctl restart ssh
```

---

👉 Issue: “Web server down”

```bash id="d16r4"
systemctl status nginx
```

---

## 🔥 Proof of Learning

✔ Checked service status
✔ Restarted service
✔ Stopped and started service
✔ Recovered failed service

👉 **Conclusion:**
I can manage and recover system services using systemctl.

---

## 🧠 My Understanding

* Services run in background
* `systemctl` controls services
* Services can be active/inactive/failed
* Restarting often fixes issues
* Logs help in deeper troubleshooting