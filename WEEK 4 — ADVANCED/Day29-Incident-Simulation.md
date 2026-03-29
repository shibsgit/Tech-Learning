## 🐧 Day 29 – Incident Simulation

### 🎯 Goal

Simulate real-world incidents and troubleshoot them step-by-step under pressure.

---

## 📚 Concepts Covered

* End-to-end troubleshooting
* Multi-layer issue detection
* Network + system debugging
* Incident handling mindset
* Root cause analysis

---

## ⚙️ Simulated Issues

* Interface down
* DNS broken
* Firewall blocking traffic

---

## 🧪 LAB PRACTICE (FULL INCIDENT 🔥)

👉 Scenario:
**“Server is not reachable and internet is not working”**

---

## 🔻 Issue 1: Interface Down

### 🔹 Step 1: Break It

```bash id="d29n1"
sudo ip link set eth0 down
```

---

### 🔹 Step 2: Detect Issue

```bash id="d29n2"
ip addr
```

### 📌 Output:

```bash id="d29o1"
eth0: <DOWN>
```

### ✅ Root Cause:

Interface is down

---

### 🔹 Step 3: Fix It

```bash id="d29n3"
sudo ip link set eth0 up
```

---

## 🔻 Issue 2: DNS Broken

### 🔹 Step 4: Break DNS

```bash id="d29n4"
sudo nano /etc/resolv.conf
```

👉 Change to:

```bash id="d29n5"
nameserver 1.1.1.1.1
```

---

### 🔹 Step 5: Detect Issue

```bash id="d29n6"
nslookup google.com
```

### 📌 Output:

```bash id="d29o2"
Temporary failure in name resolution
```

### ✅ Root Cause:

Invalid DNS configuration

---

### 🔹 Step 6: Fix DNS

```bash id="d29n7"
sudo nano /etc/resolv.conf
```

👉 Set:

```bash id="d29n8"
nameserver 8.8.8.8
```

---

## 🔻 Issue 3: Firewall Blocking Traffic

### 🔹 Step 7: Break Firewall

```bash id="d29n9"
sudo iptables -A INPUT -p icmp -j DROP
```

---

### 🔹 Step 8: Detect Issue

```bash id="d29n10"
ping 8.8.8.8
```

### 📌 Output:

```bash id="d29o3"
Request timeout
```

### ✅ Root Cause:

Firewall blocking ICMP

---

### 🔹 Step 9: Fix Firewall

```bash id="d29n11"
sudo iptables -D INPUT -p icmp -j DROP
```

---

## 🔥 FINAL TROUBLESHOOTING FLOW

👉 Always follow this order:

1. Check interface → `ip addr`
2. Check IP → correct or not
3. Check routing → `ip route`
4. Check DNS → `nslookup`
5. Check firewall → `iptables -L`
6. Test connectivity → `ping`

👉 This is **real incident workflow**

---

## ⚠️ Common Mistakes

❌ Random troubleshooting
❌ Skipping steps
❌ Not checking logs

---

### ✔ Correct Approach

✔ Follow structured steps
✔ Verify after each fix
✔ Identify root cause

---

## 🔥 Real-World Scenario (VERY IMPORTANT)

👉 Issue: “Website not opening”

Possible causes:

* Interface down
* DNS failure
* Firewall block

👉 You must identify exact cause

---

👉 Issue: “Server unreachable”

* Could be network, service, or firewall
* Need systematic approach

---

## 🔥 Proof of Learning

✔ Detected interface issue
✔ Diagnosed DNS failure
✔ Identified firewall block
✔ Fixed all issues step-by-step

👉 **Conclusion:**
I can troubleshoot real-world incidents under pressure using structured approach.

---

## 🧠 My Understanding

* Troubleshooting must be systematic
* Multiple issues can exist at once
* Always verify after fixing
* Root cause is more important than symptoms
* Calm thinking is key