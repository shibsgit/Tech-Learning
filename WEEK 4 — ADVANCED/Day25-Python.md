## 🐧 Day 25 – Python + Linux

### 🎯 Goal

Learn how to use Python with Linux to automate network checks and basic tasks.

---

## 📚 Concepts Covered

* Running Python in Linux
* Automating network checks using Python
* Using system commands inside Python
* Combining Python + Linux for automation

---

## 🧠 Why Python + Linux?

👉 Python helps:

* Automate repetitive tasks
* Replace manual CLI work
* Build monitoring scripts

👉 Widely used in:

* Networking
* DevOps
* Automation

---

## ⚙️ Commands Used

```bash id="d25n1"
python3 script.py     # Run Python script
python3 --version     # Check Python version
```

---

## 🧪 LAB PRACTICE

### 🔹 Step 1: Check Python Installed

```bash id="d25n2"
python3 --version
```

### 📌 Output:

```bash id="d25o1"
Python 3.x.x
```

---

### 🔹 Step 2: Create Python Script

```bash id="d25n3"
nano network_check.py
```

---

### 🔹 Step 3: Write Script

```python id="d25n4"
import os

gateway = "192.168.1.1"

response = os.system(f"ping -c 3 {gateway} > /dev/null")

if response == 0:
    print("Gateway is reachable")
else:
    print("Gateway is NOT reachable")
```

---

### 🔹 Step 4: Run Script

```bash id="d25n5"
python3 network_check.py
```

### 📌 Output (success):

```bash id="d25o2"
Gateway is reachable
```

### 📌 Output (failure):

```bash id="d25o3"
Gateway is NOT reachable
```

---

## ⚠️ Common Issues + Fix

### ❌ Python not found

```bash id="d25e1"
python3
```

### ✔ Fix:

```bash id="d25f1"
sudo apt install python3
```

---

### ❌ Script not running

👉 Wrong file name

---

### ✔ Fix:

```bash id="d25f2"
ls
python3 correct-name.py
```

---

### ❌ Ping not working

👉 Network issue

---

### ✔ Fix:

```bash id="d25f3"
ping 192.168.1.1
```

---

## 🔥 Real-World Scenario (VERY IMPORTANT)

👉 Automated monitoring system:

* Python script checks connectivity
* Runs periodically
* Alerts if network fails

---

👉 Example use:

* Replace manual ping checks
* Combine with cron for automation

---

## 🔥 Proof of Learning

✔ Created Python script
✔ Executed network check using Python
✔ Verified connectivity results
✔ Integrated Python with Linux commands

👉 **Conclusion:**
Python + Linux can be used together for network automation.

---

## 🧠 My Understanding

* Python can run Linux commands
* Useful for automation tasks
* Reduces manual effort
* Works well with networking tools
* Foundation for advanced automation