## 🐧 Day 30 – FINAL CHALLENGE

### 🎯 Goal

Build a complete Linux-based system that acts as a **Router, Firewall, SSH Server, and Log Analyzer**.

---

## 📚 Concepts Covered

* Network routing (IP forwarding + NAT)
* Firewall configuration (`iptables`)
* Remote access (SSH)
* Log monitoring (`journalctl`)
* End-to-end system design

---

## 🏗️ System Design

👉 Your Linux machine will act as:

* 🌐 **Router** → Forward traffic
* 🔐 **Firewall** → Control access
* 🔑 **SSH Server** → Remote management
* 📊 **Log Analyzer** → Troubleshooting

---

## ⚙️ Tasks

* Enable routing
* Configure NAT
* Apply firewall rules
* Setup SSH access
* Analyze logs

---

## 🧪 LAB PRACTICE (FULL BUILD 🔥)

---

## 🔹 Step 1: Enable Routing (Router Setup)

```bash id="d30n1"
sudo sysctl -w net.ipv4.ip_forward=1
```

### ✅ Verify:

```bash id="d30n2"
sysctl net.ipv4.ip_forward
```

---

## 🔹 Step 2: Configure NAT

```bash id="d30n3"
sudo iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE
```

### ✅ Explanation:

* Enables internet sharing
* Linux acts as gateway

---

## 🔹 Step 3: Configure Firewall

```bash id="d30n4"
sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT
sudo iptables -A INPUT -p icmp -j DROP
```

### ✅ Explanation:

* Allow SSH
* Block ping

---

## 🔹 Step 4: Setup SSH Server

```bash id="d30n5"
sudo systemctl start ssh
systemctl status ssh
```

### ✅ Test:

```bash id="d30n6"
ssh user@server-ip
```

---

## 🔹 Step 5: Log Analysis

```bash id="d30n7"
journalctl -xe
journalctl -u ssh
```

### ✅ Explanation:

* Monitor system logs
* Debug issues

---

## 🔹 Step 6: Test Full Setup

👉 From client system:

```bash id="d30n8"
ping gateway-ip
ssh user@server-ip
```

---

## ⚠️ Common Issues + Fix

### ❌ No Internet

```bash id="d30e1"
ip route
```

✔ Fix:

```bash id="d30f1"
sudo ip route add default via gateway-ip
```

---

### ❌ SSH Not Working

✔ Fix:

```bash id="d30f2"
systemctl status ssh
sudo systemctl restart ssh
```

---

### ❌ Firewall Blocking

✔ Fix:

```bash id="d30f3"
sudo iptables -L
```

---

## 🔥 REAL-WORLD SCENARIO

👉 You built a Linux server that:

* Routes traffic for internal users
* Secures access using firewall
* Allows remote management via SSH
* Provides logs for debugging

👉 This is **actual production-level setup**

---

## 🔥 FINAL PROOF OF LEARNING

✔ Configured Linux as router
✔ Applied firewall rules
✔ Enabled SSH access
✔ Performed log analysis
✔ Tested full system

👉 **Conclusion:**
I can design, configure, and troubleshoot a Linux-based network system.

---

## 🧠 My Understanding

* Linux can act as full network device
* Routing + firewall + services work together
* Security is essential
* Logs help in debugging
* End-to-end thinking is required