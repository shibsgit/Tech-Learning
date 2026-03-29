## 🐧 Day 9 – IP Addressing

### 🎯 Goal

Learn how to assign and remove IP addresses in Linux and verify connectivity.

---

## 📚 Concepts Covered

* What is an IP address
* Static IP assignment
* Subnet mask (`/24`)
* Interface-based IP configuration
* Connectivity basics

---

## 🌐 What is an IP Address?

An IP address is a **unique identifier for a device on a network**.

Example:

* `192.168.1.10` → Private IP
* `/24` → Subnet mask (255.255.255.0)

---

## ⚙️ Commands Used

```bash id="d9n1"
ip addr add 192.168.1.10/24 dev eth0   # Add IP
ip addr del 192.168.1.10/24 dev eth0   # Remove IP
ip addr                                # Verify IP
```

---

## 🧪 LAB PRACTICE

### 🔹 Step 1: Check Current IP

```bash id="d9n2"
ip addr
```

### 📌 Output (sample):

```id="d9o1"
eth0: inet 192.168.1.5/24
```

### ✅ Explanation:

Shows current IP assigned to interface

---

### 🔹 Step 2: Add New IP

```bash id="d9n3"
sudo ip addr add 192.168.1.10/24 dev eth0
```

---

### 🔹 Step 3: Verify IP

```bash id="d9n4"
ip addr
```

### 📌 Output:

```id="d9o2"
inet 192.168.1.10/24
```

### ✅ Explanation:

New IP successfully assigned

---

### 🔹 Step 4: Test Connectivity

```bash id="d9n5"
ping -c 3 192.168.1.1
```

### 📌 Output:

```id="d9o3"
64 bytes from 192.168.1.1: icmp_seq=1 ttl=64 time=1 ms
```

### ✅ Explanation:

Confirms network connectivity

---

### 🔹 Step 5: Remove IP

```bash id="d9n6"
sudo ip addr del 192.168.1.10/24 dev eth0
```

---

### 🔹 Step 6: Verify Removal

```bash id="d9n7"
ip addr
```

### 📌 Output:

```id="d9o4"
(No 192.168.1.10 present)
```

### ✅ Explanation:

IP successfully removed

---

## ⚠️ Common Issues + Fix

### ❌ Error: Permission Denied

```bash id="d9e1"
ip addr add 192.168.1.10/24 dev eth0
```

### ✔ Fix:

```bash id="d9f1"
sudo ip addr add 192.168.1.10/24 dev eth0
```

---

### ❌ Wrong Interface Name

```bash id="d9e2"
ip addr add ... dev eth0
```

👉 Interface may be:

* `ens33`
* `enp0s3`

---

### ✔ Fix:

```bash id="d9f2"
ip addr
```

👉 Use correct interface name

---

### ❌ No Connectivity

👉 Possible reasons:

* Interface DOWN
* Wrong subnet
* Gateway missing

---

## 🔥 Real-World Scenario (VERY IMPORTANT)

👉 Server not reachable:

1. Check IP:

```bash id="d9r1"
ip addr
```

2. Add IP if missing:

```bash id="d9r2"
sudo ip addr add 192.168.1.10/24 dev eth0
```

3. Test:

```bash id="d9r3"
ping gateway-ip
```

---

## 🔥 Proof of Learning

✔ Checked existing IP using `ip addr`
✔ Assigned new IP
✔ Verified connectivity using ping
✔ Removed IP successfully

👉 **Conclusion:**
I can manage and troubleshoot IP addressing in Linux.

---

## 🧠 My Understanding

* IP address identifies a device in network
* `/24` defines subnet
* `ip addr add` assigns IP
* `ip addr del` removes IP
* Connectivity must always be verified