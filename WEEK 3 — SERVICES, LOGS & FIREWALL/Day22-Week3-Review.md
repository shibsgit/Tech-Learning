## 🐧 Day 21 – Week 3 Review

### 🎯 Goal

Consolidate advanced Linux skills and perform production-level troubleshooting using SSH, firewall, logs, and routing.

---

## 📚 Topics Covered (Week 3)

* SSH (Secure Remote Access)
* Firewall (`iptables`)
* Log Analysis (`journalctl`)
* Routing (`ip route`)
* Service troubleshooting

---

## ⚙️ Tasks

* Access system using SSH
* Verify and fix firewall rules
* Analyze logs for failures
* Check and correct routing issues

---

## 🧪 LAB PRACTICE (PRODUCTION SCENARIO 🔥)

👉 Simulate: **“Server is not accessible from network”**

---

### 🔹 Step 1: Test SSH Access

```bash id="w3r1"
ssh user@server-ip
```

### ✅ Objective:

* Verify remote connectivity

---

### 🔹 Step 2: Check SSH Service

```bash id="w3r2"
systemctl status ssh
```

### ✅ Objective:

* Ensure SSH service is running

---

### 🔹 Step 3: Restart Service (if needed)

```bash id="w3r3"
sudo systemctl restart ssh
```

---

### 🔹 Step 4: Check Firewall Rules

```bash id="w3r4"
sudo iptables -L
```

### ✅ Objective:

* Verify port 22 is allowed

---

### 🔹 Step 5: Fix Firewall (if blocked)

```bash id="w3r5"
sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT
```

---

### 🔹 Step 6: Check Routing

```bash id="w3r6"
ip route
```

### ✅ Objective:

* Ensure default route exists

---

### 🔹 Step 7: Fix Routing (if missing)

```bash id="w3r7"
sudo ip route add default via 192.168.1.1
```

---

### 🔹 Step 8: Analyze Logs

```bash id="w3r8"
journalctl -u ssh -n 20
```

### ✅ Objective:

* Identify root cause of failure

---

### 🔹 Step 9: Verify Connectivity

```bash id="w3r9"
ping -c 3 server-ip
```

---

## ⚠️ Common Issues + Fix

### ❌ SSH Not Working

✔ Fix:

```bash id="w3rf1"
systemctl status ssh
sudo systemctl start ssh
```

---

### ❌ Firewall Blocking SSH

✔ Fix:

```bash id="w3rf2"
sudo iptables -L
sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT
```

---

### ❌ No Internet / Routing Issue

✔ Fix:

```bash id="w3rf3"
ip route
sudo ip route add default via gateway-ip
```

---

### ❌ Service Failure

✔ Fix:

```bash id="w3rf4"
journalctl -xe
```

---

## 🔥 Real-World Troubleshooting Flow

👉 When server issue occurs:

1. Check connectivity → `ping`
2. Check service → `systemctl`
3. Check logs → `journalctl`
4. Check firewall → `iptables`
5. Check routing → `ip route`
6. Retry access → SSH

👉 This is **actual production troubleshooting workflow**

---

## 🔥 Proof of Learning

✔ Accessed system via SSH
✔ Verified and fixed firewall rules
✔ Analyzed logs for root cause
✔ Checked and corrected routing

👉 **Conclusion:**
Linux is now usable in production and I can troubleshoot real-world issues.

---

## 🧠 My Understanding

* Troubleshooting must follow structured approach
* Logs provide root cause
* Firewall controls access
* Routing ensures connectivity
* SSH is key for remote management