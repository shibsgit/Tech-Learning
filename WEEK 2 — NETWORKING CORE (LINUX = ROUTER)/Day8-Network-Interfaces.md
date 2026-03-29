## 🐧 Day 8 – Network Interfaces

### 🎯 Goal

Understand Linux network interfaces and how to check, enable, and disable them for troubleshooting.

---

## 📚 Concepts Covered

* What is a network interface
* Interface naming (eth0, ens33, etc.)
* IP address assignment
* Interface status (UP/DOWN)
* Basic network troubleshooting

---

## 🌐 What is a Network Interface?

A network interface is a **connection point between your system and the network**.

Examples:

* `eth0` → Ethernet
* `wlan0` → Wi-Fi
* `lo` → Loopback

---

## ⚙️ Commands Used

```bash id="d8n1"
ip addr                  # Show IP addresses & interfaces
ip link set eth0 down   # Disable interface
ip link set eth0 up     # Enable interface
```

---

## 🧪 LAB PRACTICE

### 🔹 Step 1: Check Interfaces

```bash id="d8n2"
ip addr
```

### 📌 Output (sample):

```id="d8o1"
2: eth0: <BROADCAST,UP,LOWER_UP> mtu 1500
    inet 192.168.1.10/24
```

### ✅ Explanation:

* `eth0` → interface name
* `UP` → interface is active
* `inet` → IP address

---

### 🔹 Step 2: Bring Interface Down

```bash id="d8n3"
sudo ip link set eth0 down
```

---

### 🔹 Step 3: Verify Status

```bash id="d8n4"
ip addr
```

### 📌 Output:

```id="d8o2"
eth0: <NO-CARRIER,DOWN>
```

### ✅ Explanation:

Interface is now disabled → no network connectivity

---

### 🔹 Step 4: Bring Interface Up

```bash id="d8n5"
sudo ip link set eth0 up
```

---

### 🔹 Step 5: Verify Again

```bash id="d8n6"
ip addr
```

### 📌 Output:

```id="d8o3"
eth0: <BROADCAST,UP>
```

### ✅ Explanation:

Interface is active again

---

## ⚠️ Common Issues + Fix

### ❌ Error: Permission Denied

```bash id="d8e1"
ip link set eth0 down
```

### ✔ Fix:

```bash id="d8f1"
sudo ip link set eth0 down
```

---

### ❌ Interface Name Not Found

```bash id="d8e2"
ip link set eth0 down
```

👉 Modern systems use names like:

* `ens33`
* `enp0s3`

---

### ✔ Fix:

```bash id="d8f2"
ip addr
```

👉 Use correct interface name

---

## 🔥 Real-World Scenario (VERY IMPORTANT)

👉 Internet not working:

1. Check interface:

```bash id="d8r1"
ip addr
```

2. If DOWN → bring UP:

```bash id="d8r2"
sudo ip link set eth0 up
```

👉 This is first step in **network troubleshooting**

---

## 🔥 Proof of Learning

✔ Checked interfaces using `ip addr`
✔ Disabled interface successfully
✔ Enabled interface again
✔ Verified interface state

👉 **Conclusion:**
I can troubleshoot and manage network interface issues in Linux.

---

## 🧠 My Understanding

* Network interfaces connect system to network
* `ip addr` shows IP and status
* Interfaces can be UP or DOWN
* Correct interface name is important
* Basic troubleshooting starts from interface