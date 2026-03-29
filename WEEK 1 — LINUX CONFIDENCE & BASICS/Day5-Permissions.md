## 🐧 Day 5 – Permissions & Ownership

### 🎯 Goal

Understand how file permissions and ownership work in Linux and how to fix permission-related issues.

---

## 📚 Concepts Covered

* File permissions (read, write, execute)
* Numeric (octal) permission system
* File ownership (user & group)
* Permission-related errors and fixes

---

## ⚙️ Commands Used

```bash id="k2m9pl"
chmod 644 file        # Set read/write for owner, read for others
chmod 755 script.sh   # Executable script permissions
chown user:user file  # Change ownership
```

---

## 🔐 Permission Basics

### Format:

```id="p9k2lm"
-rwxr-xr-x
```

| Part  | Meaning            |
| ----- | ------------------ |
| `-`   | File type          |
| `rwx` | Owner permissions  |
| `r-x` | Group permissions  |
| `r-x` | Others permissions |

---

### Numeric Representation

| Number | Permission |
| ------ | ---------- |
| 7      | rwx        |
| 6      | rw-        |
| 5      | r-x        |
| 4      | r--        |

👉 Example:

```id="x2k8pl"
755 = rwx r-x r-x
644 = rw- r-- r--
```

---

## 🧪 LAB PRACTICE

### 🔹 Step 1: Create Test File

```bash id="n8k2pl"
touch file.txt
ls -l
```

---

### 🔹 Step 2: Change Permission (644)

```bash id="r2k9lm"
chmod 644 file.txt
ls -l
```

### 📌 Output:

```id="d8k2ps"
-rw-r--r-- file.txt
```

### ✅ Explanation:

* Owner: read + write
* Others: read only

---

### 🔹 Step 3: Make Script Executable

```bash id="y2k9dl"
touch script.sh
chmod 755 script.sh
ls -l
```

### 📌 Output:

```id="u8k2lm"
-rwxr-xr-x script.sh
```

### ✅ Explanation:

Script can now be executed

---

### 🔹 Step 4: Change Ownership

```bash id="e2k9pl"
chown user:user file.txt
ls -l
```

### 📌 Output:

```id="w8k3ps"
user user file.txt
```

### ✅ Explanation:

Changes file owner and group

---

## ⚠️ Break & Fix Scenario (VERY IMPORTANT 🔥)

### ❌ Break Permission

```bash id="q2k9lm"
chmod 000 file.txt
```

👉 No one can access the file

---

### ✔ Fix Permission

```bash id="t8k2pl"
chmod 644 file.txt
```

---

### ❌ Script Not Executing

```bash id="p2k9dl"
./script.sh
```

### Error:

```id="l8k2ps"
Permission denied
```

---

### ✔ Fix:

```bash id="m2k9lm"
chmod +x script.sh
```

---

## 🔥 Real-World Scenario

👉 Web server config issue:

* File not readable → website breaks

### Fix:

```bash id="v2k8pl"
chmod 644 config.conf
```

---

👉 Script not running in automation:

### Fix:

```bash id="z2k9dl"
chmod 755 deploy.sh
```

---

## 🔥 Proof of Learning

✔ Changed file permissions using `chmod`
✔ Made script executable
✔ Changed ownership using `chown`
✔ Broke and fixed permission issues

👉 **Conclusion:**
I can troubleshoot and fix permission-related failures in Linux.

---

## 🧠 My Understanding

* Permissions control access to files
* `chmod` modifies permissions
* `chown` changes ownership
* Wrong permissions can break applications
* Always verify using `ls -l`