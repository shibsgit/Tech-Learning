## 🐧 Day 19 – Firewall (iptables)

### 🎯 Goal

Learn how to control network traffic using firewall rules and understand packet filtering.

---

## 📚 Concepts Covered

* What is a firewall
* What is `iptables`
* Packet filtering (allow/deny traffic)
* INPUT chain basics
* Protocol & port-based rules

---

## 🔐 What is a Firewall?

A firewall controls **incoming and outgoing network traffic** based on rules.

👉 Used for:

* Security
* Access control
* Blocking unwanted traffic

---

## 🧠 What is iptables?

* `iptables` is a Linux firewall tool
* Works with rules and chains

### 🔹 Important Chain:

* **INPUT** → incoming traffic

---

## ⚙️ Commands Used

```bash id="d19n1"
iptables -L                                   # List rules
iptables -A INPUT -p tcp --dport 22 -j ACCEPT  # Allow SSH
```

---

## 🧪 LAB PRACTICE

### 🔹 Step 1: View Current Rules

```bash id="d19n2"
sudo iptables -L
```

### 📌 Output (sample):

```bash id="d19o1"
Chain INPUT (policy ACCEPT)
target     prot opt source   destination
```

### ✅ Explanation:

* Shows current firewall rules
* Default policy = ACCEPT

---

### 🔹 Step 2: Allow SSH (Port 22)

```bash id="d19n3"
sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT
```

### ✅ Explanation:

* `-A INPUT` → append rule
* `tcp` → protocol
* `--dport 22` → SSH port
* `ACCEPT` → allow traffic

---

### 🔹 Step 3: Block ICMP (Ping)

```bash id="d19n4"
sudo iptables -A INPUT -p icmp -j DROP
```

### ✅ Explanation:

* Blocks ping requests
* Useful for security

---

### 🔹 Step 4: Verify Rules

```bash id="d19n5"
sudo iptables -L
```

### 📌 Output:

```bash id="d19o2"
ACCEPT tcp -- anywhere anywhere tcp dpt:22
DROP   icmp -- anywhere anywhere
```

---

### 🔹 Step 5: Test Firewall

👉 From another system:

```bash id="d19n6"
ping server-ip
```

❌ Ping fails (blocked)

---

👉 Test SSH:

```bash id="d19n7"
ssh user@server-ip
```

✔ Works (allowed)

---

## ⚠️ Common Issues + Fix

### ❌ Permission Denied

```bash id="d19e1"
iptables -L
```

### ✔ Fix:

```bash id="d19f1"
sudo iptables -L
```

---

### ❌ Locked Out from SSH

👉 Wrong rule order

---

### ✔ Fix:

```bash id="d19f2"
sudo iptables -F
```

👉 Flush all rules (use carefully)

---

### ❌ Rules Not Persistent

👉 Rules reset after reboot

---

### ✔ Fix:

```bash id="d19f3"
sudo apt install iptables-persistent
```

---

## 🔥 Real-World Scenario (VERY IMPORTANT)

👉 Issue: “Server not reachable via ping”

Check firewall:

```bash id="d19r1"
iptables -L
```

👉 If ICMP blocked → expected behavior

---

👉 Issue: “SSH access blocked”

```bash id="d19r2"
iptables -L | grep 22
```

👉 Add rule:

```bash id="d19r3"
sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT
```

---

## 🔥 Proof of Learning

✔ Viewed firewall rules
✔ Allowed SSH traffic
✔ Blocked ICMP traffic
✔ Verified rule behavior

👉 **Conclusion:**
I can control network traffic and apply packet filtering using iptables.

---

## 🧠 My Understanding

* Firewall controls traffic using rules
* `iptables` filters packets
* Rules are applied in chains
* Order of rules matters
* Misconfiguration can block access