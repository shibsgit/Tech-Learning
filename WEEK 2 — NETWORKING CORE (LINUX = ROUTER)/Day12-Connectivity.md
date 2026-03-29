## 🐧 Day 12 – Connectivity Testing

### 🎯 Goal

Understand how to verify connectivity and trace packet flow to identify where network issues occur.

---

## 📚 Concepts Covered

* End-to-end connectivity
* ICMP (ping) basics
* Packet path tracing
* Latency and hops
* Identifying network failure points

---

## 🌐 What is Connectivity Testing?

Connectivity testing helps determine:

* Whether a system can reach another system
* Where communication is failing
* How packets travel across the network

---

## ⚙️ Commands Used

```bash id="d12n1"
ping 8.8.8.8              # Test connectivity
traceroute google.com     # Trace packet path
```

---

## 🧪 LAB PRACTICE

### 🔹 Step 1: Test Basic Connectivity

```bash id="d12n2"
ping -c 3 8.8.8.8
```

### 📌 Output (sample):

```bash id="d12o1"
64 bytes from 8.8.8.8: icmp_seq=1 ttl=117 time=20 ms
```

### ✅ Explanation:

* Confirms system can reach internet
* `time` → latency
* `ttl` → packet lifetime

---

### 🔹 Step 2: Test Gateway Connectivity

```bash id="d12n3"
ping -c 3 192.168.1.1
```

### 📌 Explanation:

* Tests local network connectivity
* If this fails → LAN issue

---

### 🔹 Step 3: Trace Packet Path

```bash id="d12n4"
traceroute google.com
```

### 📌 Output (sample):

```bash id="d12o2"
1  192.168.1.1
2  10.x.x.x
3  ISP-router
4  google.com
```

### ✅ Explanation:

* Shows each hop between source and destination
* Helps identify where traffic stops

---

## ⚠️ Common Issues + Fix

### ❌ traceroute command not found

```bash id="d12e1"
traceroute google.com
```

### ✔ Fix:

```bash id="d12f1"
sudo apt install traceroute
```

---

### ❌ Ping fails

```bash id="d12e2"
ping 8.8.8.8
```

👉 Possible reasons:

* Interface down
* No IP assigned
* Routing issue

---

### ✔ Fix:

```bash id="d12f2"
ip addr
ip route
```

---

## 🔥 Real-World Scenario (VERY IMPORTANT)

👉 Issue: “Internet not working”

### Step-by-step:

1. Ping gateway:

```bash id="d12r1"
ping 192.168.1.1
```

❌ Fails → local network issue

---

2. Ping public IP:

```bash id="d12r2"
ping 8.8.8.8
```

❌ Fails → routing/internet issue

---

3. Trace route:

```bash id="d12r3"
traceroute google.com
```

👉 Identify where traffic stops

---

## 🔥 Proof of Learning

✔ Tested connectivity using `ping`
✔ Verified gateway reachability
✔ Traced packet path using `traceroute`
✔ Identified failure points in network

👉 **Conclusion:**
I can determine where network traffic stops and troubleshoot connectivity issues.

---

## 🧠 My Understanding

* `ping` checks connectivity
* `traceroute` shows packet path
* Gateway is first hop
* Failures can occur at any hop
* Step-by-step testing helps isolate issues