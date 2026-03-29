## 🐧 Day 24 – Bash Automation

### 🎯 Goal

Learn how to automate repetitive tasks using Bash scripting.

---

## 📚 Concepts Covered

* What is a Bash script
* Automating commands
* Script execution
* Basic logic in scripts
* Real-world automation use cases

---

## 🧠 What is Bash Automation?

Bash automation means:
👉 Writing scripts to **automatically execute tasks instead of doing them manually**

---

## ⚙️ Commands Used

```bash id="d24n1"
nano script.sh      # Create script
chmod +x script.sh  # Make executable
./script.sh         # Run script
```

---

## 🧪 LAB PRACTICE

### 🔹 Step 1: Create Script File

```bash id="d24n2"
nano ping_check.sh
```

---

### 🔹 Step 2: Write Script

```bash id="d24n3"
#!/bin/bash

GATEWAY="192.168.1.1"

ping -c 3 $GATEWAY > /dev/null

if [ $? -eq 0 ]; then
    echo "Gateway is reachable"
else
    echo "Gateway is NOT reachable"
fi
```

---

### 🔹 Step 3: Save & Exit

* Press `Ctrl + X`
* Press `Y`
* Press `Enter`

---

### 🔹 Step 4: Make Script Executable

```bash id="d24n4"
chmod +x ping_check.sh
```

---

### 🔹 Step 5: Run Script

```bash id="d24n5"
./ping_check.sh
```

### 📌 Output (success):

```bash id="d24o1"
Gateway is reachable
```

### 📌 Output (failure):

```bash id="d24o2"
Gateway is NOT reachable
```

### ✅ Explanation:

* Script checks connectivity automatically
* `$?` → exit status of last command

---

## ⚠️ Common Issues + Fix

### ❌ Permission Denied

```bash id="d24e1"
./ping_check.sh
```

### ✔ Fix:

```bash id="d24f1"
chmod +x ping_check.sh
```

---

### ❌ Script Not Running

👉 Missing shebang

---

### ✔ Fix:

```bash id="d24f2"
#!/bin/bash
```

---

### ❌ Wrong Gateway IP

👉 Script gives false result

---

### ✔ Fix:

* Verify gateway:

```bash id="d24f3"
ip route
```

---

## 🔥 Real-World Scenario (VERY IMPORTANT)

👉 NOC Monitoring Script:

* Automatically check network connectivity
* Alert if gateway unreachable

---

👉 Example usage:

* Run script every 5 minutes (cron job)
* Detect outages early

---

## 🔥 Proof of Learning

✔ Created Bash script
✔ Automated ping check
✔ Executed script successfully
✔ Understood exit status logic

👉 **Conclusion:**
I can automate repetitive network checks using Bash scripting.

---

## 🧠 My Understanding

* Bash scripts automate tasks
* Scripts reduce manual effort
* `$?` helps check success/failure
* Automation improves efficiency
* Useful for monitoring and troubleshooting