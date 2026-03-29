## 🐧 Day 14 – Packet Capture

### 🎯 Goal

Learn how to capture and analyze real network traffic using packet capture tools.

---

## 📚 Concepts Covered

* What is packet capture
* ICMP traffic (ping)
* DNS traffic (port 53)
* Real-time traffic monitoring
* Basic packet analysis

---

## 🌐 What is Packet Capture?

Packet capture allows you to **see actual network packets flowing through your system**.

👉 Used for:

* Troubleshooting
* Debugging network issues
* Security analysis

---

## ⚙️ Commands Used

```bash id="d14n1"
tcpdump -i eth0 icmp     # Capture ICMP traffic
tcpdump -nn port 53      # Capture DNS traffic
```

---

## 🧪 LAB PRACTICE

### 🔹 Step 1: Capture ICMP Traffic

```bash id="d14n2"
sudo tcpdump -i eth0 icmp
```

👉 In another terminal, run:

```bash id="d14n3"
ping -c 3 8.8.8.8
```

### 📌 Output (sample):

```bash id="d14o1"
IP 192.168.1.5 > 8.8.8.8: ICMP echo request
IP 8.8.8.8 > 192.168.1.5: ICMP echo reply
```

### ✅ Explanation:

* Shows request & reply packets
* Confirms ICMP traffic is flowing

---

### 🔹 Step 2: Capture DNS Traffic

```bash id="d14n4"
sudo tcpdump -nn port 53
```

👉 In another terminal:

```bash id="d14n5"
nslookup google.com
```

### 📌 Output (sample):

```bash id="d14o2"
IP 192.168.1.5.12345 > 8.8.8.8.53: DNS query
IP 8.8.8.8.53 > 192.168.1.5.12345: DNS response
```

### ✅ Explanation:

* Port 53 → DNS
* Shows query and response

---

## ⚠️ Common Issues + Fix

### ❌ tcpdump command not found

```bash id="d14e1"
tcpdump
```

### ✔ Fix:

```bash id="d14f1"
sudo apt install tcpdump
```

---

### ❌ Permission Denied

```bash id="d14e2"
tcpdump -i eth0 icmp
```

### ✔ Fix:

```bash id="d14f2"
sudo tcpdump -i eth0 icmp
```

---

### ❌ No Output Seen

👉 Possible reasons:

* Wrong interface
* No traffic generated

---

### ✔ Fix:

```bash id="d14f3"
ip addr
```

👉 Use correct interface name (e.g., `ens33`)

---

## 🔥 Real-World Scenario (VERY IMPORTANT)

👉 Issue: “Ping not working”

1. Capture ICMP:

```bash id="d14r1"
sudo tcpdump -i eth0 icmp
```

2. Send ping

👉 If no packets seen → traffic not leaving system

---

👉 Issue: “DNS not resolving”

```bash id="d14r2"
sudo tcpdump -nn port 53
```

👉 Check:

* DNS query sent?
* DNS response received?

---

## 🔥 Proof of Learning

✔ Captured ICMP traffic
✔ Captured DNS traffic
✔ Verified packet flow
✔ Identified request and response

👉 **Conclusion:**
I can capture and verify real network traffic using packet analysis.

---

## 🧠 My Understanding

* `tcpdump` shows real packets
* ICMP = connectivity
* DNS = name resolution
* Packet capture proves whether traffic exists
* Helps isolate network issues