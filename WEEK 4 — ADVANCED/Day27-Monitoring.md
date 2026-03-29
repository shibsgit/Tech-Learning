## 🐧 Day 27 – Monitoring Mindset

### 🎯 Goal

Develop the mindset of a NOC/SRE engineer by identifying what to monitor and defining alert scenarios.

---

## 📚 Concepts Covered

* What is monitoring
* NOC vs SRE mindset
* Key system & network metrics
* Alerting principles
* Proactive vs reactive troubleshooting

---

## 🧠 What is Monitoring?

Monitoring means:
👉 **Continuously observing system and network health to detect issues early**

---

## 🧠 NOC / SRE Mindset

* Don’t wait for failure ❌
* Detect issues early ✅
* Think in terms of:

  * Availability
  * Performance
  * Reliability

---

## ⚙️ What to Monitor (VERY IMPORTANT)

### 🔹 System Level

* CPU usage
* Memory usage
* Disk usage

---

### 🔹 Network Level

* Interface status
* Packet loss
* Latency

---

### 🔹 Service Level

* SSH service
* Web server (nginx/apache)
* Application services

---

### 🔹 Logs

* Errors
* Failed logins
* Service crashes

---

## 🧪 LAB PRACTICE (THINKING EXERCISE 🔥)

👉 Instead of commands, this is **analysis-based lab**

---

### 🔹 Step 1: Identify Critical Metrics

Example:

| Component | What to Monitor   |
| --------- | ----------------- |
| CPU       | High usage (>80%) |
| Memory    | Low free memory   |
| Disk      | >90% usage        |
| Network   | Packet loss       |
| Service   | Running or failed |

---

### 🔹 Step 2: Define Alert Scenarios

Example:

* CPU > 80% → Alert
* Disk > 90% → Alert
* SSH down → Critical alert
* No internet → Network alert

---

### 🔹 Step 3: Map Commands to Monitoring

| Metric  | Command            |
| ------- | ------------------ |
| CPU     | `top`              |
| Memory  | `free -m`          |
| Disk    | `df -h`            |
| Network | `ping`, `ip addr`  |
| Service | `systemctl status` |
| Logs    | `journalctl`       |

---

### 🔹 Step 4: Simulate Issue

👉 Example:

* Stop SSH:

```bash id="d26m1"
sudo systemctl stop ssh
```

👉 Detect:

```bash id="d26m2"
systemctl status ssh
```

---

### 🔹 Step 5: Define Response

👉 If SSH down:

* Restart service
* Check logs
* Verify port

---

## ⚠️ Common Mistakes

❌ Only react after failure
❌ Not monitoring logs
❌ Ignoring small warnings

---

### ✔ Correct Approach

✔ Monitor continuously
✔ Set thresholds
✔ Act early

---

## 🔥 Real-World Scenario (VERY IMPORTANT)

👉 Issue: “Server suddenly slow”

### Monitoring approach:

1. Check CPU → `top`
2. Check memory → `free -m`
3. Check disk → `df -h`
4. Check logs → `journalctl`

👉 Identify root cause before failure

---

👉 Issue: “Service randomly stops”

* Monitor service status
* Set alert if service stops

---

## 🔥 Proof of Learning

✔ Identified key system and network metrics
✔ Defined alert conditions
✔ Mapped monitoring tools to metrics
✔ Simulated failure and response

👉 **Conclusion:**
I can think like a NOC/SRE engineer and proactively monitor systems.

---

## 🧠 My Understanding

* Monitoring is proactive, not reactive
* Systems must be observed continuously
* Alerts help prevent failures
* Logs are critical for diagnosis
* Thinking matters more than commands