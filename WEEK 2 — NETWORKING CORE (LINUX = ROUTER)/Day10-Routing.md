## 🐧 Day 10 – Routing

### 🎯 Goal

Understand how packets travel in a network and how to manage routing in Linux.

---

## 📚 Concepts Covered

* What is routing
* Routing table
* Default gateway
* Packet forwarding basics
* Fixing “no internet” issues

---

## 🌐 What is Routing?

Routing is the process of **deciding where a packet should go next**.

👉 Every system uses a **routing table** to determine:

* Local network traffic
* Remote network traffic
* Internet traffic

---

## ⚙️ Commands Used

```bash
ip route                              # View routing table
ip route add default via 192.168.1.1  # Add default gateway
```

---

## 🧪 LAB PRACTICE

### 🔹 Step 1: View Routing Table

```bash
ip route
```

### 📌 Output (sample):

```bash
default via 192.168.1.1 dev eth0
192.168.1.0/24 dev eth0 proto kernel scope link
```

### ✅ Explanation:

* `default via 192.168.1.1` → gateway for internet
* `192.168.1.0/24` → local network

---

### 🔹 Step 2: Remove Default Route (Simulation)

```bash
sudo ip route del default
```

---

### 🔹 Step 3: Check Again

```bash
ip route
```

### 📌 Output:

```bash
192.168.1.0/24 dev eth0
```

### ✅ Explanation:

👉 No default route → no internet access

---

### 🔹 Step 4: Add Default Route

```bash
sudo ip route add default via 192.168.1.1
```

---

### 🔹 Step 5: Verify Route

```bash
ip route
```

### 📌 Output:

```bash
default via 192.168.1.1 dev eth0
```

### ✅ Explanation:

Internet path restored

---

### 🔹 Step 6: Test Connectivity

```bash
ping -c 3 8.8.8.8
```

### 📌 Output:

```bash
64 bytes from 8.8.8.8: icmp_seq=1 ttl=117 time=20 ms
```

### ✅ Explanation:

Successful internet connectivity

---

## ⚠️ Common Issues + Fix

### ❌ No Internet Access

```bash
ping 8.8.8.8
```

👉 Fails

---

### ✔ Fix:

```bash
ip route
```

👉 If no default route:

```bash
sudo ip route add default via 192.168.1.1
```

---

### ❌ Wrong Gateway

👉 If gateway IP is incorrect → no connectivity

✔ Fix: Use correct router IP

---

### ❌ Interface Down

👉 Even with route, internet won’t work

✔ Fix:

```bash
sudo ip link set eth0 up
```

---

## 🔥 Real-World Scenario (VERY IMPORTANT)

👉 “Server has no internet”

Steps:

1. Check IP → `ip addr`
2. Check route → `ip route`
3. Add default route if missing
4. Test with ping

👉 This is **real NOC troubleshooting workflow**

---

## 🔥 Proof of Learning

✔ Viewed routing table
✔ Removed default route
✔ Added default route
✔ Verified connectivity

👉 **Conclusion:**
I can troubleshoot and fix routing issues, including “no internet” problems.

---

## 🧠 My Understanding

* Routing decides packet path
* Default route = path to internet
* Without default route → no internet
* `ip route` shows routing table
* Gateway must be correct