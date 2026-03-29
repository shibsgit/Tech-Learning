## 🐧 Day 29 – Interview Practice

### 🎯 Goal

Develop the ability to confidently explain Linux networking concepts and troubleshoot scenarios in interviews.

---

## 📚 Concepts Covered

* Explaining technical concepts clearly
* Structured troubleshooting answers
* Interview communication skills
* Real-world scenario thinking
* Confidence building

---

## ⚙️ Tasks

* Explain Linux networking aloud
* Answer troubleshooting questions

---

## 🧪 PRACTICE LAB (INTERVIEW SIMULATION 🔥)

👉 Do this like a **mock interview**

---

### 🔹 Task 1: Explain Linux Networking (Aloud)

👉 Speak this in your own words:

```bash id="d29i1"
Linux networking involves interfaces, IP addressing, routing, and DNS.

First, a device gets an IP address (static or DHCP).
Then routing decides where packets go.
DNS resolves domain names to IP addresses.
Finally, services and ports handle communication.
```

### ✅ Objective:

* Speak clearly
* Keep it simple
* Show understanding

---

### 🔹 Task 2: “How Would You Troubleshoot No Internet?”

👉 Answer like this:

```bash id="d29i2"
First, I check the interface using ip addr.
Then I verify IP address is assigned.
Next, I check routing using ip route.
Then I test connectivity using ping.
If IP works but domain doesn’t, I check DNS using nslookup.
Finally, I check firewall rules using iptables.
```

---

### 🔹 Task 3: “SSH Not Working – What Will You Do?”

```bash id="d29i3"
First, I check if SSH service is running using systemctl status ssh.
Then I check if port 22 is listening using ss -tuln.
Next, I verify firewall rules using iptables.
Then I check logs using journalctl -u ssh.
Finally, I try to connect again using ssh.
```

---

### 🔹 Task 4: “Server Slow – What Will You Check?”

```bash id="d29i4"
I check CPU usage using top.
Then memory using free -m.
Then disk usage using df -h.
If needed, I check logs for errors.
Then I identify the root cause and fix it.
```

---

## ⚠️ Common Interview Mistakes

❌ Jumping randomly
❌ Giving theory only
❌ Not explaining steps

---

### ✔ Correct Approach

✔ Step-by-step explanation
✔ Use real commands
✔ Think like troubleshooting flow

---

## 🔥 Real Interview Scenario

👉 Interviewer asks:

**“How do you troubleshoot network issue?”**

👉 Your answer:

1. Check interface
2. Check IP
3. Check route
4. Check DNS
5. Check firewall
6. Verify connectivity

👉 This is **perfect structured answer 🔥**

---

## 🔥 Proof of Learning

✔ Explained Linux networking clearly
✔ Answered troubleshooting questions step-by-step
✔ Used real commands in explanation
✔ Practiced speaking confidently

👉 **Conclusion:**
I can confidently explain Linux networking and troubleshooting in interviews.

---

## 🧠 My Understanding

* Communication is as important as knowledge
* Structure is key in interviews
* Real examples make answers strong
* Confidence comes from practice
* Think like engineer, not student