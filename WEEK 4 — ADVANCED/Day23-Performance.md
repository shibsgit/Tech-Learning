## 🐧 Day 23 – Processes & Performance

### 🎯 Goal

Learn how to monitor system performance and detect CPU, memory, and disk-related issues.

---

## 📚 Concepts Covered

* What is a process
* CPU usage monitoring
* Memory (RAM) usage
* Disk usage
* System performance troubleshooting

---

## 🧠 What is a Process?

A process is a **running program in the system**.

👉 Each process uses:

* CPU
* Memory
* System resources

---

## ⚙️ Commands Used

```bash id="d23n1"
top        # Real-time process monitoring
htop       # Interactive process viewer
free -m    # Memory usage
df -h      # Disk usage
```

---

## 🧪 LAB PRACTICE

### 🔹 Step 1: Monitor Processes (top)

```bash id="d23n2"
top
```

### 📌 Output (sample):

```bash id="d23o1"
%Cpu(s): 30.0 us
MiB Mem : 2048 total, 1500 free
```

### ✅ Explanation:

* CPU usage
* Running processes
* Memory stats

👉 Press `q` to exit

---

### 🔹 Step 2: Advanced Monitoring (htop)

```bash id="d23n3"
htop
```

### 📌 Explanation:

* Better UI than top
* Shows CPU, memory, processes visually

---

### ❗ If not installed:

```bash id="d23n4"
sudo apt install htop
```

---

### 🔹 Step 3: Check Memory Usage

```bash id="d23n5"
free -m
```

### 📌 Output:

```bash id="d23o2"
Mem: 2048 total, 500 used, 1500 free
```

### ✅ Explanation:

Shows RAM usage in MB

---

### 🔹 Step 4: Check Disk Usage

```bash id="d23n6"
df -h
```

### 📌 Output:

```bash id="d23o3"
/dev/sda1  20G  15G  5G  75%
```

### ✅ Explanation:

* Total disk
* Used space
* Available space

---

## ⚠️ Common Issues + Fix

### ❌ High CPU Usage

```bash id="d23e1"
top
```

👉 Identify process with high CPU

---

### ✔ Fix:

```bash id="d23f1"
kill -9 PID
```

---

### ❌ Low Memory

```bash id="d23e2"
free -m
```

👉 Memory almost full

---

### ✔ Fix:

* Stop unnecessary services
* Restart system if needed

---

### ❌ Disk Full

```bash id="d23e3"
df -h
```

👉 100% usage

---

### ✔ Fix:

```bash id="d23f2"
du -sh *
rm unwanted-files
```

---

## 🔥 Real-World Scenario (VERY IMPORTANT)

👉 Issue: “Server is slow”

### Step-by-step:

1. Check CPU:

```bash id="d23r1"
top
```

2. Check memory:

```bash id="d23r2"
free -m
```

3. Check disk:

```bash id="d23r3"
df -h
```

👉 Identify bottleneck

---

👉 Issue: “Application not responding”

* High CPU → process overload
* Low memory → system slow
* Disk full → logs/app fail

---

## 🔥 Proof of Learning

✔ Monitored processes using `top` and `htop`
✔ Checked memory usage
✔ Checked disk usage
✔ Identified system bottlenecks

👉 **Conclusion:**
I can detect CPU, RAM, and disk performance issues in Linux.

---

## 🧠 My Understanding

* Processes consume system resources
* High CPU → overload
* Low memory → performance issues
* Disk full → system failure
* Monitoring is key for troubleshooting