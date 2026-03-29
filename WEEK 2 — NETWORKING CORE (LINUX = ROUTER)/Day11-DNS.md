## 🐧 Day 11 – DNS Troubleshooting

### 🎯 Goal

Understand how DNS works and learn how to diagnose and fix name resolution issues.

---

## 📚 Concepts Covered

* What is DNS (Domain Name System)
* Name resolution (domain → IP)
* DNS servers
* `/etc/resolv.conf` configuration
* DNS troubleshooting workflow

---

## 🌐 What is DNS?

DNS converts **domain names → IP addresses**

Example:

* `google.com` → `142.x.x.x`

👉 Without DNS, you must remember IPs instead of names

---

## ⚙️ Commands Used

```bash id="d11n1"
nslookup google.com        # DNS query test
dig google.com             # Detailed DNS info
cat /etc/resolv.conf       # DNS server config
```

---

## 🧪 LAB PRACTICE

### 🔹 Step 1: Test DNS (nslookup)

```bash id="d11n2"
nslookup google.com
```

### 📌 Output (sample):

```bash id="d11o1"
Server:  8.8.8.8
Address: 8.8.8.8#53

Name: google.com
Address: 142.x.x.x
```

### ✅ Explanation:

* DNS server used
* Domain resolved to IP

---

### 🔹 Step 2: Detailed DNS Query (dig)

```bash id="d11n3"
dig google.com
```

### 📌 Output (important part):

```bash id="d11o2"
ANSWER SECTION:
google.com.  300  IN  A  142.x.x.x
```

### ✅ Explanation:

Shows detailed DNS response including record type

---

### 🔹 Step 3: Check DNS Configuration

```bash id="d11n4"
cat /etc/resolv.conf
```

### 📌 Output:

```bash id="d11o3"
nameserver 8.8.8.8
```

### ✅ Explanation:

System uses this DNS server for resolution

---

## ⚠️ Break & Fix Scenario (VERY IMPORTANT 🔥)

### ❌ Break DNS

```bash id="d11e1"
sudo nano /etc/resolv.conf
```

👉 Change to invalid DNS:

```bash id="d11e2"
nameserver 1.1.1.1.1
```

---

### 🔹 Test Again

```bash id="d11e3"
nslookup google.com
```

### Output:

```bash id="d11e4"
Temporary failure in name resolution
```

---

### ✔ Fix DNS

```bash id="d11f1"
sudo nano /etc/resolv.conf
```

👉 Set correct DNS:

```bash id="d11f2"
nameserver 8.8.8.8
```

---

### 🔹 Verify Fix

```bash id="d11f3"
nslookup google.com
```

---

## 🔥 Real-World Scenario (VERY IMPORTANT)

👉 Issue: “Internet working but website not opening”

### Step-by-step:

1. Test IP connectivity:

```bash id="d11r1"
ping 8.8.8.8
```

✔ Works → network OK

---

2. Test DNS:

```bash id="d11r2"
nslookup google.com
```

❌ Fails → DNS issue

---

3. Fix DNS:

```bash id="d11r3"
cat /etc/resolv.conf
```

👉 Update nameserver

---

## 🔥 Proof of Learning

✔ Tested DNS using `nslookup`
✔ Used `dig` for detailed analysis
✔ Checked DNS config file
✔ Broke and fixed DNS resolution

👉 **Conclusion:**
I can diagnose and fix DNS-related issues in Linux.

---

## 🧠 My Understanding

* DNS resolves domain names to IPs
* `nslookup` is quick test tool
* `dig` gives detailed DNS info
* `/etc/resolv.conf` stores DNS servers
* DNS failure = website not reachable