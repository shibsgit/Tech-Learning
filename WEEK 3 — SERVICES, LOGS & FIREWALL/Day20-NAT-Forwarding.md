## 🐧 Day 20 – NAT & Forwarding

### 🎯 Goal

Understand how Linux can act as a router by enabling IP forwarding and configuring NAT (Network Address Translation).

---

## 📚 Concepts Covered

* What is NAT (Network Address Translation)
* What is IP forwarding
* Linux as a gateway/router
* Packet forwarding between interfaces
* NAT using `iptables`

---

## 🌐 What is NAT?

NAT allows **multiple private IPs to access the internet using one public IP**.

👉 Used in:

* Routers
* Firewalls
* Gateways

---

## 🔄 What is IP Forwarding?

IP forwarding allows Linux to:
👉 **Forward packets between interfaces (like a router)**

---

## ⚙️ Commands Used

```bash id="d20n1"
sysctl net.ipv4.ip_forward     # Check forwarding status
iptables -t nat -L             # View NAT rules
```

---

## 🧪 LAB PRACTICE

👉 Assume:

* `eth0` → internet interface
* `eth1` → internal network

---

### 🔹 Step 1: Check IP Forwarding

```bash id="d20n2"
sysctl net.ipv4.ip_forward
```

### 📌 Output:

```bash id="d20o1"
net.ipv4.ip_forward = 0
```

### ✅ Explanation:

* `0` → forwarding disabled
* `1` → forwarding enabled

---

### 🔹 Step 2: Enable IP Forwarding

```bash id="d20n3"
sudo sysctl -w net.ipv4.ip_forward=1
```

---

### 🔹 Step 3: Verify Again

```bash id="d20n4"
sysctl net.ipv4.ip_forward
```

### 📌 Output:

```bash id="d20o2"
net.ipv4.ip_forward = 1
```

### ✅ Explanation:

System can now forward packets

---

### 🔹 Step 4: Configure NAT (Masquerading)

```bash id="d20n5"
sudo iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE
```

### ✅ Explanation:

* `POSTROUTING` → outgoing packets
* `-o eth0` → internet interface
* `MASQUERADE` → hide internal IPs

---

### 🔹 Step 5: Verify NAT Rules

```bash id="d20n6"
sudo iptables -t nat -L
```

### 📌 Output:

```bash id="d20o3"
MASQUERADE  all  --  anywhere  anywhere
```

---

## ⚠️ Common Issues + Fix

### ❌ No Internet for Clients

👉 Possible reasons:

* Forwarding disabled
* NAT not configured

---

### ✔ Fix:

```bash id="d20f1"
sysctl net.ipv4.ip_forward
sudo iptables -t nat -L
```

---

### ❌ Wrong Interface

👉 Using incorrect interface name

---

### ✔ Fix:

```bash id="d20f2"
ip addr
```

---

### ❌ Rules Lost After Reboot

---

### ✔ Fix:

```bash id="d20f3"
sudo apt install iptables-persistent
```

---

## 🔥 Real-World Scenario (VERY IMPORTANT)

👉 Setup Linux as gateway for internal network:

1. Enable forwarding
2. Configure NAT
3. Connect clients through this system

---

👉 Issue: “Clients cannot access internet”

Steps:

```bash id="d20r1"
sysctl net.ipv4.ip_forward
```

```bash id="d20r2"
iptables -t nat -L
```

👉 Fix forwarding + NAT

---

## 🔥 Proof of Learning

✔ Enabled IP forwarding
✔ Configured NAT using iptables
✔ Verified NAT rules
✔ Understood packet forwarding

👉 **Conclusion:**
Linux can act as a router and forward traffic between networks.

---

## 🧠 My Understanding

* NAT translates private IP to public IP
* IP forwarding enables routing
* Linux can act as gateway
* `iptables` handles NAT rules
* Required for network design