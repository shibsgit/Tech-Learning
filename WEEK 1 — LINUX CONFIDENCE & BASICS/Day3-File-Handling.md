## 🐧 Day 3 – File Handling

### 🎯 Goal

Learn how to safely create, copy, rename, and delete files in Linux.

---

## 📚 Concepts Covered

* File creation
* Copying files
* Renaming files
* Deleting files
* Safe file handling practices

---

## ⚙️ Commands Used

```bash id="z8k2lp"
touch test.txt          # Create file
cp test.txt test1.txt   # Copy file
mv test1.txt prod.txt   # Rename file
rm prod.txt             # Delete file
```

---

## 🧪 LAB PRACTICE

### 🔹 Step 1: Create a File

```bash id="k9d2pl"
touch test.txt
ls
```

### 📌 Output:

```id="l2m9qp"
test.txt
```

### ✅ Explanation:

Creates an empty file named `test.txt`

---

### 🔹 Step 2: Copy File

```bash id="m8k3pl"
cp test.txt test1.txt
ls
```

### 📌 Output:

```id="p3k9lm"
test.txt  test1.txt
```

### ✅ Explanation:

Creates a duplicate file

---

### 🔹 Step 3: Rename File

```bash id="n2k9dl"
mv test1.txt prod.txt
ls
```

### 📌 Output:

```id="r8k2zp"
test.txt  prod.txt
```

### ✅ Explanation:

Renames `test1.txt` → `prod.txt`

---

### 🔹 Step 4: Delete File

```bash id="d9k2ps"
rm prod.txt
ls
```

### 📌 Output:

```id="x3k8lm"
test.txt
```

### ✅ Explanation:

Deletes the file permanently

---

## ⚠️ Common Mistakes + Fix

### ❌ Mistake: Deleting wrong file

```bash id="q8k2lm"
rm test.txt
```

👉 File is permanently deleted (no recycle bin)

---

### ✔ Safe Method:

```bash id="y2k9pl"
rm -i test.txt
```

👉 Prompts before deletion

---

### ❌ Mistake: Overwriting file during copy

```bash id="u8k3pl"
cp test.txt prod.txt
```

👉 Overwrites existing file

---

### ✔ Safe Method:

```bash id="w2k9dl"
cp -i test.txt prod.txt
```

---

## 🔥 Real-World Scenario (VERY IMPORTANT)

👉 While editing config files:

```bash id="e9k2ps"
cp config.conf config.conf.backup
```

👉 Always take backup before modification

---

## 🔥 Proof of Learning

✔ Created files using `touch`
✔ Copied files using `cp`
✔ Renamed files using `mv`
✔ Deleted files using `rm` safely

👉 **Conclusion:**
I can safely handle and modify files, including configuration files.

---

## 🧠 My Understanding

* `touch` creates files
* `cp` duplicates files
* `mv` renames/moves files
* `rm` deletes files permanently
* Always take backup before modifying important files