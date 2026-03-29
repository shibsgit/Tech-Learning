## 🐧 Day 2 – Linux Directory Structure

### 🎯 Goal

Understand where important files and configurations are stored in Linux.

---

## 📚 Concepts Covered

* Linux file system hierarchy
* Purpose of key directories
* Config files vs log files
* System vs user directories

---

## 📂 Important Directories

### 🔹 `/etc` → Configuration Files

* Stores system-wide configuration files
* Examples:

  * network configs
  * service configs

---

### 🔹 `/var` → Variable Data

* Stores data that changes frequently

#### `/var/log`

* System logs
* Application logs

---

### 🔹 `/bin` → Essential Commands

* Basic commands required for system operation
* Examples:

  * ls
  * cp
  * mv

---

### 🔹 `/usr` → User Programs

* Installed applications and libraries
* `/usr/bin` → user-level commands
* `/usr/lib` → libraries

---

## ⚙️ Commands Used

```bash id="v4k9p2"
ls /etc
ls /var/log
tree /
```

---

## 🧪 LAB PRACTICE

### 🔹 Step 1: Explore `/etc`

```bash id="n2k8ls"
ls /etc
```

### 📌 Output:

```id="m8q2zp"
passwd  hosts  ssh  network
```

### ✅ Explanation:

Contains configuration files (users, network, services)

---

### 🔹 Step 2: Explore Logs

```bash id="p7k2xn"
ls /var/log
```

### 📌 Output:

```id="z9k3lm"
syslog  auth.log  kern.log
```

### ✅ Explanation:

Contains system and application logs

---

### 🔹 Step 3: View Full Structure

```bash id="r2k9dl"
tree /
```

### 📌 Output (shortened):

```id="j3m8qp"
/
├── bin
├── etc
├── home
├── var
```

### ✅ Explanation:

Shows hierarchical structure of Linux file system

---

## ⚠️ Common Issues + Fix

### ❌ Error: tree command not found

```bash id="g8k2ps"
tree /
```

### Output:

```id="k2m9zl"
command not found
```

### ✔ Fix:

```bash id="f9k3dn"
sudo apt install tree
```

---

## 🔥 Proof of Learning

✔ Explored `/etc` → identified config files
✔ Explored `/var/log` → identified log files
✔ Understood directory hierarchy using `tree`

👉 **Conclusion:**
I know where system configs and logs are stored in Linux.

---

## 🧠 My Understanding

* `/etc` stores configuration files
* `/var/log` stores logs
* `/bin` contains essential commands
* `/usr` contains applications and libraries
* Linux follows a structured hierarchy