## 🐧 Day 15 – Week 2 Review

### 🎯 Goal

Reinforce networking concepts learned in Week 2 and perform end-to-end troubleshooting using Linux tools.

---

## 📚 Topics Covered (Week 2)

* Network Interfaces
* IP Addressing
* Routing
* DNS Troubleshooting
* Connectivity Testing
* Ports & Services
* Packet Capture

---

## ⚙️ Tasks

* Check interface and IP
* Verify routing and connectivity
* Troubleshoot DNS
* Identify running services and ports
* Capture and analyze traffic

---

## 🧪 LAB PRACTICE (FULL FLOW 🔥)

👉 Perform this as a **real-world troubleshooting scenario**

---

### 🔹 Step 1: Check Network Interface

```bash id="w2s1"
ip addr
```

### ✅ Objective:

* Identify interface name
* Check if interface is UP
* Verify IP address

---

### 🔹 Step 2: Verify IP Address

```bash id="w2s2"
ip addr | grep inet
```

### ✅ Objective:

* Confirm correct IP assigned

---

### 🔹 Step 3: Check Routing Table

```bash id="w2s3"
ip route
```

### ✅ Objective:

* Verify default route
* Identify gateway

---

### 🔹 Step 4: Test Connectivity

```bash id="w2s4"
ping -c 3 192.168.1.1
ping -c 3 8.8.8.8
```

### ✅ Objective:

* Check LAN connectivity
* Check internet reachability

---

### 🔹 Step 5: Test DNS Resolution

```bash id="w2s5"
nslookup google.com
```

### ✅ Objective:

* Verify domain name resolution

---

### 🔹 Step 6: Trace Packet Path

```bash id="w2s6"
traceroute google.com
```

### ✅ Objective:

* Identify where traffic stops

---

### 🔹 Step 7: Check Listening Ports

```bash id="w2s7"
ss -tuln
```

### ✅ Objective:

* Identify active services

---

### 🔹 Step 8: Identify Service Owner

```bash id="w2s8"
lsof -i :22
```

### ✅ Objective:

* Map port to process

---

### 🔹 Step 9: Capture Traffic

```bash id="w2s9"
sudo tcpdump -i eth0 icmp
```

👉 In another terminal:

```bash id="w2s10"
ping -c 3 8.8.8.8
```

### ✅ Objective:

* Verify packet flow

---

## ⚠️ Common Issues + Fix

### ❌ No Internet

```bash id="w2e1"
ping 8.8.8.8
```

### ✔ Fix:

```bash id="w2f1"
ip route
sudo ip route add default via 192.168.1.1
```

---

### ❌ DNS Not Working

```bash id="w2e2"
nslookup google.com
```

### ✔ Fix:

```bash id="w2f2"
cat /etc/resolv.conf
```

---

### ❌ No Traffic Seen

```bash id="w2e3"
tcpdump -i eth0 icmp
```

### ✔ Fix:

* Check interface name
* Generate traffic (ping)

---

## 🔥 Real-World Scenario (VERY IMPORTANT)

👉 Issue: “Server not reachable”

### Troubleshooting Flow:

1. Check interface → `ip addr`
2. Check IP → verify correct
3. Check route → `ip route`
4. Ping gateway → LAN check
5. Ping public IP → internet check
6. Check DNS → `nslookup`
7. Trace route → identify failure
8. Check ports/services
9. Capture packets

👉 This is **actual NOC workflow**

---

## 🔥 Proof of Learning

✔ Verified interface and IP
✔ Checked routing and connectivity
✔ Diagnosed DNS issues
✔ Identified ports and services
✔ Captured and analyzed traffic

👉 **Conclusion:**
I can perform end-to-end network troubleshooting using Linux tools.

---

## 🧠 My Understanding

* Networking issues follow a step-by-step pattern
* Always troubleshoot layer by layer
* IP → Route → DNS → Service → Packet
* Packet capture confirms real traffic