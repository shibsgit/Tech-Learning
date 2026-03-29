## 🐧 Day 21 – Network Services (DHCP & DNS Basics)

### 🎯 Goal

Understand how network services like DHCP and DNS work and configure a basic DHCP service.

---

## 📚 Concepts Covered

* What is DHCP (Dynamic Host Configuration Protocol)
* What is DNS (Domain Name System)
* Automatic IP assignment
* Service-based networking
* Basic `dnsmasq` usage

---

## 🌐 What is DHCP?

DHCP automatically assigns:

* IP address
* Subnet mask
* Gateway
* DNS

👉 Removes need for manual IP configuration

---

## 🌐 What is DNS?

DNS converts:
👉 **Domain name → IP address**

Example:

* `google.com` → `142.x.x.x`

---

## ⚙️ Commands Used

```bash id="d21n1"
sudo apt install dnsmasq     # Install dnsmasq
sudo systemctl status dnsmasq
```

---

## 🧪 LAB PRACTICE

👉 `dnsmasq` acts as:

* DHCP server
* DNS forwarder

---

### 🔹 Step 1: Install dnsmasq

```bash id="d21n2"
sudo apt update
sudo apt install dnsmasq -y
```

---

### 🔹 Step 2: Check Service Status

```bash id="d21n3"
systemctl status dnsmasq
```

### 📌 Output:

```bash id="d21o1"
Active: active (running)
```

### ✅ Explanation:

Service is running

---

### 🔹 Step 3: Configure DHCP

Edit config file:

```bash id="d21n4"
sudo nano /etc/dnsmasq.conf
```

Add:

```bash id="d21n5"
interface=eth0
dhcp-range=192.168.1.50,192.168.1.100,12h
```

### ✅ Explanation:

* `interface` → network interface
* `dhcp-range` → IP range for clients

---

### 🔹 Step 4: Restart Service

```bash id="d21n6"
sudo systemctl restart dnsmasq
```

---

### 🔹 Step 5: Verify DHCP (Client Side)

👉 On another system:

```bash id="d21n7"
ip addr
```

### 📌 Output:

```bash id="d21o2"
inet 192.168.1.55/24
```

### ✅ Explanation:

IP assigned automatically via DHCP

---

## ⚠️ Common Issues + Fix

### ❌ dnsmasq not starting

```bash id="d21e1"
systemctl status dnsmasq
```

---

### ✔ Fix:

```bash id="d21f1"
journalctl -u dnsmasq
```

👉 Check config errors

---

### ❌ Port conflict (53)

👉 Another DNS service running

---

### ✔ Fix:

```bash id="d21f2"
ss -tuln | grep 53
```

---

### ❌ Clients not getting IP

👉 Possible reasons:

* Wrong interface
* DHCP range incorrect

---

### ✔ Fix:

```bash id="d21f3"
ip addr
```

---

## 🔥 Real-World Scenario (VERY IMPORTANT)

👉 Office network setup:

* Router assigns IP using DHCP
* DNS resolves domain names

---

👉 Issue: “Client not getting IP”

Steps:

1. Check service:

```bash id="d21r1"
systemctl status dnsmasq
```

2. Check config
3. Restart service

---

👉 Issue: “DNS not resolving”

Check:

```bash id="d21r2"
cat /etc/resolv.conf
```

---

## 🔥 Proof of Learning

✔ Installed dnsmasq
✔ Configured DHCP range
✔ Restarted service
✔ Verified IP assignment

👉 **Conclusion:**
I understand how network services provide IP and name resolution.

---

## 🧠 My Understanding

* DHCP automates IP assignment
* DNS resolves names to IP
* Services run in background
* Misconfiguration can break network
* Logs help identify issues