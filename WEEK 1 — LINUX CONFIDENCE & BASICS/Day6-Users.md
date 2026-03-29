## 🐧 Day 6 – Users & sudo

### 🎯 Goal

Learn how to manage users and control privileged access securely using sudo.

---

## 📚 Concepts Covered

* User creation and management
* Password setup
* Privilege escalation (`sudo`)
* Root vs normal user
* Secure access control

---

## ⚙️ Commands Used

```bash
useradd nocuser        # Create new user
passwd nocuser         # Set password
sudo su                # Switch to root user
```

---

## 👤 User Basics

* Linux is a **multi-user system**
* Each user has:

  * Username
  * UID (User ID)
  * Home directory

---

## 🔐 Root vs Normal User

| Type        | Access         |
| ----------- | -------------- |
| Root        | Full control   |
| Normal User | Limited access |

👉 Root can modify anything
👉 Normal users need `sudo` for admin tasks

---

## 🧪 LAB PRACTICE

### 🔹 Step 1: Create User

```bash
sudo useradd nocuser
```

---

### 🔹 Step 2: Set Password

```bash
sudo passwd nocuser
```

👉 Enter password when prompted

---

### 🔹 Step 3: Switch User

```bash
su - nocuser
```

### 📌 Output:

```bash
nocuser@hostname:~$
```

### ✅ Explanation:

You are now logged in as `nocuser`

---

### 🔹 Step 4: Test Access (Without sudo)

```bash
ls /root
```

### 📌 Output:

```bash
Permission denied
```

### ✅ Explanation:

Normal users cannot access root directory

---

### 🔹 Step 5: Use sudo (Switch to Root)

```bash
sudo su
```

### 📌 Output:

```bash
root@hostname:~#
```

### ✅ Explanation:

You now have root privileges

---

## ⚠️ Common Issues + Fix

### ❌ Error: User not in sudo group

```bash
sudo su
```

### Output:

```bash
nocuser is not in the sudoers file
```

---

### ✔ Fix:

```bash
sudo usermod -aG sudo nocuser
```

👉 Adds user to sudo group

---

### ❌ Error: Cannot login as user

```bash
su - nocuser
```

👉 Might fail if password not set

---

### ✔ Fix:

```bash
sudo passwd nocuser
```

---

## 🔥 Real-World Scenario (VERY IMPORTANT)

👉 In companies:

* Users are created for teams (NOC, DevOps)
* Limited access is given for security

Example:

* NOC user → read logs
* Admin → full access

---

## 🔥 Proof of Learning

✔ Created user using `useradd`
✔ Set password using `passwd`
✔ Switched user and tested access
✔ Used `sudo` for admin privileges

👉 **Conclusion:**
I can manage users and control access in a multi-user Linux environment.

---

## 🧠 My Understanding

* Linux supports multiple users
* Root has full control
* `sudo` allows temporary admin access
* Access control is critical for system security