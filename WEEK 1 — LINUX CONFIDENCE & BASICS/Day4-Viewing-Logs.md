## 🐧 Day 4 – Viewing Files & Logs

### 🎯 Goal

Learn how to read configuration files and monitor logs effectively, especially during troubleshooting or incidents.

---

## 📚 Concepts Covered

* Viewing file contents
* Reading large files efficiently
* Real-time log monitoring
* Difference between `cat`, `less`, and `tail`

---

## ⚙️ Commands Used

```bash id="k4m9pl"
cat /etc/hosts              # View full file
less /etc/passwd            # View large file (scrollable)
tail -f /var/log/syslog     # Live log monitoring
```

---

## 🧪 LAB PRACTICE

### 🔹 Step 1: View Small File

```bash id="n2k8pl"
cat /etc/hosts
```

### 📌 Output:

```id="l9k2qp"
127.0.0.1   localhost
```

### ✅ Explanation:

Displays entire file content at once
👉 Best for small files

---

### 🔹 Step 2: View Large File

```bash id="p8k3dl"
less /etc/passwd
```

### 📌 Output (sample):

```id="r2k9lm"
root:x:0:0:root:/root:/bin/bash
```

### ✅ Explanation:

* Opens file in scrollable mode
* Use:

  * `↑ ↓` → scroll
  * `q` → quit

👉 Best for large files

---

### 🔹 Step 3: Live Log Monitoring

```bash id="d2k9ps"
tail -f /var/log/syslog
```

### 📌 Output (live):

```id="x8k2lm"
Mar 30 systemd[1]: Started service
```

### ✅ Explanation:

* Shows last lines of log
* `-f` → follow new logs in real time

👉 Used during incidents / troubleshooting

---

## ⚠️ Common Issues + Fix

### ❌ Error: Permission Denied

```bash id="q9k2lm"
tail -f /var/log/syslog
```

### ✔ Fix:

```bash id="w8k3pl"
sudo tail -f /var/log/syslog
```

---

### ❌ Problem: File too large with `cat`

```bash id="y2k9dl"
cat bigfile.log
```

👉 Terminal floods with data

---

### ✔ Solution:

```bash id="u8k2ps"
less bigfile.log
```

---

## 🔥 Real-World Scenario (VERY IMPORTANT)

👉 During network/server issue:

```bash id="e2k9lm"
tail -f /var/log/syslog
```

👉 You can:

* Watch errors live
* Track service failures
* Monitor system behavior

---

## 🔥 Proof of Learning

✔ Viewed config files using `cat`
✔ Read large files using `less`
✔ Monitored logs in real-time using `tail -f`

👉 **Conclusion:**
I can read system configs and monitor logs during incidents.

---

## 🧠 My Understanding

* `cat` is for small files
* `less` is for large files
* `tail -f` is for real-time monitoring
* Logs are critical for troubleshooting