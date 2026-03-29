## 🐧 Day 17 – Log Analysis

### 🎯 Goal

Learn how to analyze system logs and identify root causes of failures using `journalctl`.

---

## 📚 Concepts Covered

* What are system logs
* Importance of logs in troubleshooting
* `systemd` journal logs
* Service-specific logs
* Root cause analysis

---

## 🧠 What are Logs?

Logs are **records of system events and errors**.

👉 Used to:

* Diagnose issues
* Track failures
* Monitor system behavior

---

## ⚙️ Commands Used

```bash id="d16ln1"
journalctl -xe        # View recent system logs
journalctl -u ssh     # View logs for specific service
```

---

## 🧪 LAB PRACTICE

### 🔹 Step 1: View System Logs

```bash id="d16ln2"
journalctl -xe
```

### 📌 Output (sample):

```bash id="d16lo1"
Mar 30 systemd[1]: Failed to start ssh.service
```

### ✅ Explanation:

* Shows recent logs with errors
* `-xe` → extended + recent entries

---

### 🔹 Step 2: View Service Logs

```bash id="d16ln3"
journalctl -u ssh
```

### 📌 Output (sample):

```bash id="d16lo2"
sshd[1234]: Failed password for user
```

### ✅ Explanation:

* Shows logs only for SSH service
* Useful for focused troubleshooting

---

### 🔹 Step 3: Filter Recent Logs

```bash id="d16ln4"
journalctl -u ssh -n 20
```

### 📌 Explanation:

Shows last 20 log entries

---

### 🔹 Step 4: Live Log Monitoring

```bash id="d16ln5"
journalctl -u ssh -f
```

### ✅ Explanation:

* `-f` → follow logs in real time
* Useful during active troubleshooting

---

## ⚠️ Common Issues + Fix

### ❌ Permission Denied

```bash id="d16le1"
journalctl -xe
```

### ✔ Fix:

```bash id="d16lf1"
sudo journalctl -xe
```

---

### ❌ No Logs Found

```bash id="d16le2"
journalctl -u ssh
```

👉 Possible reason:

* Service name incorrect

---

### ✔ Fix:

```bash id="d16lf2"
systemctl list-units --type=service
```

---

### ❌ Too Many Logs

```bash id="d16le3"
journalctl -xe
```

👉 Hard to read

---

### ✔ Fix:

```bash id="d16lf3"
journalctl -xe | less
```

---

## 🔥 Real-World Scenario (VERY IMPORTANT)

👉 Issue: “SSH service not working”

### Step-by-step:

1. Check service:

```bash id="d16lr1"
systemctl status ssh
```

2. Check logs:

```bash id="d16lr2"
journalctl -u ssh
```

👉 Identify error:

* Permission issue
* Config issue
* Port conflict

---

👉 Issue: “Service failed to start”

```bash id="d16lr3"
journalctl -xe
```

👉 Look for:

* “Failed”
* “Error”
* “Permission denied”

---

## 🔥 Proof of Learning

✔ Viewed system logs
✔ Analyzed service-specific logs
✔ Identified failure reasons
✔ Used logs for troubleshooting

👉 **Conclusion:**
I can perform root cause analysis using system logs.

---

## 🧠 My Understanding

* Logs are the first place to check during issues
* `journalctl` is powerful for debugging
* Service logs help isolate problems
* Errors in logs reveal root cause
* Real troubleshooting depends on log analysis