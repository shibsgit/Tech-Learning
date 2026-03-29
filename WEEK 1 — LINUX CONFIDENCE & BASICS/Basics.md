🐧 Linux Basics
📌 What is Linux?

Linux is an open-source, Unix-like operating system kernel created by Linus Torvalds in 1991.
An operating system acts as a bridge between hardware and user applications.

Linux is widely used in:

Servers (Web, Database, Cloud)
Networking devices (Routers, Switches)
Mobile devices (Android)
Embedded systems
Cybersecurity and DevOps environments

🧠 Why Linux is Important?
💡 Open-source (free to use & modify)
🔒 Highly secure and stable
⚡ High performance (used in servers & data centers)
🌍 Large community support
🔧 Highly customizable

# 🐧 Linux Architecture (In-Depth)

Linux architecture is a layered and modular design that enables efficient interaction between user applications and hardware while maintaining security, stability, and performance.

--------------------------------------------------

## 🧱 High-Level Architecture

User Applications
        ↓
System Libraries
        ↓
System Calls
        ↓
Kernel
        ↓
Hardware

--------------------------------------------------

## 🔹 1. Hardware Layer

The hardware layer consists of all physical components of the system.

Components:
- CPU → Executes instructions
- RAM → Stores temporary data
- Disk → Persistent storage
- NIC → Network communication

Key Points:
- Hardware cannot understand user-level instructions directly
- It only interacts with the kernel through low-level signals

--------------------------------------------------

## 🔹 2. Kernel (Core of Linux)

The kernel is the central component of the Linux operating system.

- Runs in kernel space (privileged mode)
- Has full access to hardware resources
- Acts as a bridge between hardware and user space

--------------------------------------------------

### 🧠 Kernel Responsibilities

1. Process Management
- Creation and termination of processes
- Scheduling of CPU time
- Assigning Process IDs (PID)
- Context switching between processes

2. Memory Management
- Allocation and deallocation of memory
- Virtual memory management
- Paging and swapping mechanisms

3. File System Management
- Handles file storage and retrieval
- Maintains directory structure
- Uses Virtual File System (VFS) to support multiple file systems

4. Device Drivers
- Interface between kernel and hardware devices
- Controls hardware like disk, keyboard, network interfaces

5. Networking
- Implements TCP/IP protocol stack
- Handles packet routing and communication

6. Security and Permissions
- User authentication and authorization
- File and process access control

--------------------------------------------------

### 🔧 Kernel Type

Linux uses a Monolithic Kernel:
- All core services run in kernel space
- Provides high performance
- Supports Loadable Kernel Modules (LKM) for flexibility

--------------------------------------------------

## 🔹 3. System Calls

System calls provide the interface between user applications and the kernel.

Key Points:
- Applications cannot access hardware directly
- All requests must go through system calls
- Ensures controlled and secure access to system resources

Examples:
- File operations
- Process creation
- Input/output handling

--------------------------------------------------

## 🔹 4. System Libraries

System libraries act as intermediaries between applications and system calls.

Key Points:
- Provide APIs for application development
- Simplify complex system call usage
- Example: Standard C Library (glibc)

Flow:
Application → Library → System Call → Kernel

--------------------------------------------------

## 🔹 5. User Space

User space is where all user-level programs and applications run.

Characteristics:
- Limited access to system resources
- Safer environment compared to kernel space
- Errors do not crash the entire system

--------------------------------------------------

### 🖥️ Components of User Space

1. Shell
- Interface between user and kernel
- Interprets user commands

2. Utilities
- Basic tools for system operations
- File handling, text processing, system monitoring

3. Applications
- Editors, browsers, servers, and other programs

--------------------------------------------------

## 🔄 Execution Flow (Conceptual)

1. User enters a command or runs an application
2. Shell interprets the command
3. System libraries are invoked
4. System call is generated
5. Kernel processes the request
6. Hardware performs the action
7. Output is returned to the user

--------------------------------------------------

## 🔥 User Space vs Kernel Space

User Space:
- Limited access
- Safe execution environment
- Application-level operations

Kernel Space:
- Full access to hardware
- Critical for system stability
- Handles core system functions

--------------------------------------------------

## 📂 Linux File System Structure

/
├── /bin      → essential user commands
├── /etc      → configuration files
├── /home     → user directories
├── /var      → logs and variable data
├── /proc     → process and kernel information
├── /dev      → device files

--------------------------------------------------

## 🧠 Key Concepts (Interview Focus)

- Kernel is the core of the operating system
- System calls act as a bridge between user space and kernel
- Linux uses a monolithic kernel architecture
- Virtual File System (VFS) enables multiple file system support
- User space is isolated for stability and security

--------------------------------------------------

## 🧠 Summary

- Linux architecture follows a layered design
- The kernel manages all hardware and system resources
- Applications interact with hardware through system calls
- System libraries simplify communication with the kernel
- The separation of user space and kernel space ensures system stability

--------------------------------------------------
🧩 Linux Distributions (Distros)

Linux comes in different distributions:

Ubuntu → Beginner-friendly
Debian → Stable and secure
Red Hat (RHEL) → Enterprise-level
Kali Linux → Security & penetration testing
CentOS / Rocky Linux → Server environments

📂 Linux File System Structure

Important directories:

Directory	Purpose
/	Root directory (everything starts here)
/home	User files
/etc	Configuration files
/var	Logs & variable data
/bin	Essential commands
/usr	User programs
/tmp	Temporary files

⚙️ Basic Linux Commands

pwd        # Show current directory
ls         # List files
cd         # Change directory
mkdir      # Create directory
rm         # Remove files/directories
cp         # Copy files
mv         # Move/rename files
touch      # Create file
cat        # View file content

🔐 Linux Users & Permissions

Linux is a multi-user system
Each file has:
Owner
Group
Permissions

Permission types:

r → Read
w → Write
x → Execute

Example:

chmod 755 script.sh
chown user:user file.txt

🧑‍💻 Types of Users

Root user → Full access (superuser)
Normal user → Limited access
System user → Used by services

🧾 Package Management

Linux uses package managers to install software:

apt → Ubuntu/Debian
yum / dnf → RHEL/CentOS
pacman → Arch Linux

Example:

sudo apt update
sudo apt install nginx
🔄 Process Management
A process = running program

Commands:

ps aux
top
kill PID

🌐 Networking Basics

ip a        # Show IP address
ping        # Check connectivity
netstat     # Network status
ss          # Socket statistics

📊 Linux Use Cases

Web servers (Apache, Nginx)
Cloud platforms (AWS, Azure, GCP)
Networking (Routers, Firewalls)
DevOps & Automation
Cybersecurity

🧠 Key Takeaways
Linux = Powerful, secure, open-source OS
Kernel is the core component
Everything in Linux is a file
CLI (Command Line Interface) is very important
Used heavily in networking and servers