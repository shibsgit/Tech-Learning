🐧 Day 1 – Terminal & Navigation
🎯 Goal

Feel comfortable working inside the Linux terminal and navigating the system without using GUI.

📚 Concepts Covered
What is a terminal
Current working directory
Absolute vs relative path
Navigation using CLI
Command history
⚙️ Commands Used
pwd        # Print current directory
ls         # List files and folders
cd /       # Go to root directory
cd ~       # Go to home directory
history    # Show command history
🧪 LAB PRACTICE
🔹 Step 1: Open Terminal
Open your Linux terminal (or Git Bash / WSL)
🔹 Step 2: Check Current Directory
pwd
📌 Output:
/home/user
✅ Explanation:

Shows your current working directory

🔹 Step 3: List Files
ls
📌 Output:
Documents  Downloads  Desktop
✅ Explanation:

Lists all files and folders in current directory

🔹 Step 4: Go to Root Directory
cd /
pwd
📌 Output:
/
✅ Explanation:

Moves to root (/) which is top of Linux file system

🔹 Step 5: Go to Home Directory
cd ~
pwd
📌 Output:
/home/user
✅ Explanation:

~ represents home directory

🔹 Step 6: Use Command History
history
📌 Output:
1 pwd
2 ls
3 cd /
4 cd ~
✅ Explanation:

Shows previously executed commands

⚠️ Common Mistakes + Fix
❌ Error:
cd wrongfolder
Output:
No such file or directory
✔ Fix:
ls
cd correct-folder-name
🔥 Proof of Learning

✔ Navigated between root (/) and home (~)
✔ Used pwd to verify location
✔ Listed files using ls
✔ Used history to track commands

👉 Conclusion:
I can now navigate anywhere in Linux using CLI only without GUI.

🧠 My Understanding
Linux navigation is based on directory structure
/ is root, ~ is home
CLI is faster and more powerful than GUI
Practice improves speed and confidence