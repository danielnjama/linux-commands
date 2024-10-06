# Fundamentals of Linux Administration

## Table of Contents
1. [Introduction to Linux](#1-introduction-to-linux)
2. [Getting Started with Linux Commands](#2-getting-started-with-linux-commands)
3. [File and Directory Management](#3-file-and-directory-management)
4. [Text Manipulation](#4-text-manipulation)
5. [Permissions and Ownership](#5-permissions-and-ownership)
6. [Package Management](#6-package-management)
7. [Networking Basics](#7-networking-basics)
# 1. Introduction to Linux
[![Watch the video](https://img.youtube.com/vi/mMz08R1Jq40/maxresdefault.jpg)](https://www.youtube.com/watch?v=mMz08R1Jq40)
## 1.1 Understanding the Linux Operating System
Define: Linux is an open-source, Unix-like operating system kernel first created by Linus Torvalds in 1991. It is the foundation of various operating systems known as Linux distributions (distros).

**Key Characteristics:**
- Open source and freely available.
- Multi-user and multitasking capabilities.
- Security and stability.
- Compatibility with a wide range of hardware.

## 1.2 Examples of popular Linux Distributions
  - Ubuntu
  - Red Hat
  - Debian
  - Parrot
  - Kali
  - CentOs
 
## 1.3 CLI VS GUI
## Advantages of CLI
- Efficiency: Performing tasks often faster than graphical interfaces.
- Scripting: Automation of repetitive tasks through scripts.
- Remote Access: SSH allows secure remote connections.
- Resource Efficiency: CLI uses fewer system resources compared to GUI.

  
# 2. Getting Started with Linux Commands
## 2.1 Overview of the Linux Terminal:
## Components:
1. Shell: Interpreter that processes commands.
2. Prompt: Indicates readiness for user input.
3. Command Line: Area for entering commands.
4. Terminal Emulator: Software that emulates a physical terminal.

Access to Linux terminal:
To access a Linux Terminal, you need any of the following: 
1. have access to a computer with Linux OS
2. access to a Linux server
3. access free Linux shell online:
  - https://www.webminal.org/
  - https://bellard.org/jslinux/

4. On windows, install software that will simulate a Linux shell. Eg:  VirtualBox or VMware with a Linux OS, MobaXterm software.



## 2.2 Logging into a Linux System
1. **Local Login**: Physically at the machine, using a keyboard and monitor.
2. **SSH (Secure Shell)**: Remotely access a machine over a network.

***How to access a Linux server***

***1. Local Login***

This method involves accessing the Linux system directly, using a physical keyboard and monitor attached to the machine. After booting, the login prompt appears, where you can input the username and password to access the system.

Steps for Local Login:
- Power on the Linux machine.
- At the login prompt, type in your username your password and press Enter.
- Upon successful authentication, you will be logged into the system.

***2. SSH (Secure Shell)***

SSH allows you to securely access a Linux system remotely over a network. It’s commonly used to manage servers and remote systems. Here’s how to access a Linux server using SSH.

***2.1: Default SSH Login***

To log in to a server via SSH with the default settings, which usually uses port 22:
```
ssh username@server_ip
```
- username is your remote server’s user.
- server_ip is the IP address/hostname of your Linux server.

***2.2 SSH with a Different Port***

If SSH is configured to run on a different port (other than the default port 22), you can specify the port using the -p flag:
```
ssh username@server_ip -p port_number
```


## 2.3 Basic Commands for Navigation
**cd (Change Directory):**
Change the current working directory.
```
cd /path/to/directory
```
Chage directory to the previous.
```
cd ..
```

Switch to Documents directory from any location
```
cd ~/Documents/
```

**ls (List):**
List files and directories in the current directory.
```
ls
```

List Files in a Specific Directory:
```
ls /path/to/directory
```
Long Format with Hidden Files current folder:
```
ls -la
```

Long Format with Hidden Files on specific folder:
```
ls -la ls /path/to/directory
```


**pwd (Print Working Directory):**
Display the current working directory's full path.
```
pwd
```
**df -h (Disk Free)**

The df command is used to check the available disk space on the file system. The -h option stands for human-readable format, which displays the sizes in a more readable format (KB, MB, GB).

```
df -h
```
**echo**: 
The echo command prints a line of text to the terminal or redirects it to a file.
```
echo "Hello, World!"
```

**man (Manual Pages)**

The man command displays the manual (help) page for any other command.

Example-: get more info on ls usage.
```
man ls
````
**Practice Exercise:**
1. Access a remote machine on SSH. Establish the home directory(default directory a user is placed in when they SSH)
2. Navigate through directories using cd, list contents with ls, and print the working directory with pwd.
3. Logout of the remote server. Mention the best practices 
4. Check the disk size allocated to the root (/) mount.
5. Identify the mount with the highest disk usage and mention the percentage. 

**Explore Further**
1. How to SSH Using a Key (Key-Based Authentication) - Upload ssh key and login in subsequently without entering password
2. How to Access AWS EC2 Instance via SSH
3. Explore other means on how to access EC2 instance.
4. Explore other df -h options such as return output in ascending/descending order, return output for only the mounts that are a given percentage only. 

   

# 3. File and Directory Management
## 3.1 Creating and Deleting Files and Directories:

**mkdir (Make Directory):**
Create a new directory.
```
mkdir directory_name
````
**touch:**
Create an empty file or update the access and modification time of a file.
```
touch filename
```
**echo**
Add content into the created file
```
echo "Hello, World!" > filename.txt
```

**rm (Remove):**
Remove files or directories.
```
rm filename
rm -r directory_name  # Remove directory and its contents
rmdir directory_name   #removes directory when empty
``````
## 3.2 Copying and Moving Files and Directories:

**cp (Copy):**
Copy files or directories.
```
cp source destination
``````
**mv (Move):**
Move files or directories (also used for renaming).
```
mv source destination
``````

**scp (Secure Copy)**
The scp command is used to securely transfer files between a local system and a remote system, or between two remote systems, using SSH for encryption.

Example:
1. Copying a File from Local to Remote:
```
scp file.txt username@remote_host:/path/to/destination/
```
This copies file.txt from your local machine to the remote machine at /path/to/destination/.

2. Copying a File from Remote to Local:
```
scp username@remote_host:/path/to/file.txt /local/path/
```
This copies file.txt from the remote server to your local machine

3. Using a Different SSH Port:
If the remote server uses a custom SSH port (other than the default port 22), use the -P option:

```
scp -P 2222 file.txt username@remote_host:/path/to/destination/

```
## 3.3 Listing and Viewing File Content:

**ls (List):**
List files and directories in the current directory.
```
ls
``````
**cat (Concatenate):**
Display the contents of a file.
```
cat filename
`````
**more and less:**
View the contents of a file one screen at a time.
```
more filename
less filename
`````

**Practice Exercise:**
1. Create 2 directories under /home, and name them your first and second names. create a file in your first name folder named exercise.txt. Add the text "Hello world!!!"
2. Create a copy of the exercise.txt file and name the copy new-exercise.txt.
3. Move the new-exercise.txt file to your second name folder.
4. Navigate to your second name folder, and add more lines of "Hello world!!!". Upto 5 lines.
5. Create a duplicate of the new-exercise.txt file and give it a name of your choice.
6. List files and view their content using ls, cat, more, and less.: 1. To confirm 2 files under your second name folder and confirm the content. 
7. Repeat the above by first moving to the root folder; ie: cd / then execute the above tasks from here.

**Explore Further**
1. Explore how to sync or move files in a folder from one server to another:: (remote-remote or remote-local)
2. How to scp a file from local server to EC2 instance using the key file (PEM)
3. Explore other methods that can be used to get files to a remote server, including but not limited to Cloning a github repo, wget method etc.


# 4. Text Manipulation
## 4.1 Working with Text Files:

**echo:**
Display a line of text
```
echo "Hello, Linux!"
``````
**Text Editors:**
nano: Simple text editor for beginners.
```
nano filename
``````
**vim: Powerful and efficient text editor.**
```
vim filename
``````
## 4.2 Searching for Text in Files:
**grep (Global Regular Expression Print):**
Search for a specific pattern or text in files.
```
grep pattern filename
``````
## 4.3 Redirecting and Combining Commands:
**> (Output Redirection):**
Redirects command output to a file, overwriting existing content.
```
command > filename
```
Example:
```
df -h > disk.txt
```
**>> (Append):**
Appends command output to a file.
```
command >> filename
```
Example:
```
df -h >> disk.txt
```
**| (Pipe):**
Passes the output of one command as the input to another.
```
command1 | command2
```
Example:
```
cat disk.txt | grep "home"
```
**Practice Exercise:**
1. Use echo to create and display text.
2. Create and edit text files with nano and vim.
3. Search for specific patterns in files using grep.
4. Redirect and combine commands using >, >>, and |.

# 5. Permissions and Ownership
## 5.1 Understanding Linux File Permissions:
Permissions are represented using a three-character string for each category (user, group, others).
To check on file permissions:
```
ls -l filename  #returns the permission of the named file
ls -l    #returns a list of files in the current directory, alongside their permissions.
``````
**Three Permission Categories:**
1. User (u): Owner of the file.
2. Group (g): Users in the file's group.
3. Other (o): Everyone else.

**Three Permission Types:**
- Read (r): Permission to read the file.
- Write (w): Permission to modify the file.
- Execute (x): Permission to execute the file or access a directory.
**Permission Representation:**

Permissions can also be represented numerically using a three-digit octal number. Each digit corresponds to a permission category, and the value is calculated by summing the values assigned to the read, write, and execute permissions:

4 for read (r)
2 for write (w)
1 for execute (x)

For example:

rwx is represented as 7 (4 + 2 + 1).
rw- is represented as 6 (4 + 2).
r-- is represented as 4 (4).

## 5.2 Changing File Permissions:

**chmod (Change Mode):**
Modify file permissions.
```
chmod permissions filename
``````
**Numeric Representation:**
Numeric values (e.g., 755) represent combinations of read, write, and execute permissions.
Changing File Ownership:

## 5.3 chown (Change Owner):
The chown command in Linux is used to change the ownership of files and directories. This includes changing the owner, the group, or both.

Usage:
```
chown [options] new_owner:new_group filename
```
- new_owner: The new user who will own the file.
- new_group: The new group that will be assigned ownership of the file.
- filename: The name of the file or directory whose ownership is to be changed.

Examples:

1. To change the owner of a file to a new user:
```
sudo chown john file.txt
```
This command makes john the owner of file.txt. The group remains unchanged.

2. Change the Owner and Group of a File::

To change both the owner and group at the same time:
```
sudo chown john:developers file.txt
```
This sets john as the owner and assigns the file to the developers group.

3. Change the Group Only

If you want to change only the group of a file without modifying the owner:
```
sudo chown :developers file.txt
```
This changes the group to developers while keeping the current file owner unchanged.

4. Change Ownership of a Directory and Its Contents Recursively

To change the ownership of a directory and all its contents, use the -R (recursive) option:
```
sudo chown -R john:developers /path/to/directory
```




Other Examples:
```
# Grant read and write permissions to the user
chmod u+rw filename

# Remove execute permission from the group
chmod g-x filename

# Add execute permission for others
chmod o+x filename

# Set specific permissions using numeric representation (e.g., read and write for user, read-only for group and others)
chmod 644 filename

``````

## Explain what permission 644 mean

File permission 644 is a numeric representation of the permissions assigned to a file in Linux. In the context of the three-digit octal number 644, each digit corresponds to a specific permission category: user (owner), group, and others.Here's a breakdown of what 644 means:

**User (Owner):**

- 6 corresponds to read (r) and write (w) permissions.
- The owner of the file has read and write permissions but does not have execute permission.

**Group:**

- 4 corresponds to read (r) permission.
- Members of the group associated with the file have only read permission.

**Others:**

- 4 corresponds to read (r) permission.
- Other users (those not the owner and not in the group) also have only read permission.

**Interpretation:**
- The owner can read and modify the file (rw-).
- Members of the group can read the file (r--).
- Others (any user not the owner or in the group) can also read the file (r--).

**Symbolic Representation:**
The symbolic representation of 644 is rw-r--r--, where:

- rw-: Read and write permissions for the owner.
- r--: Read-only permissions for the group.
- r--: Read-only permissions for others.

**Practice Exercise:**
1. Display the current permissions and ownership of a file using ls -l.
2. Use chmod to change permissions on a file.
3. Experiment with both symbolic and numeric representations.
4. Use chown to change the owner and group of a file.

# 6. Package Management
## 6.1 Introduction to Package Managers:

**Package Manager Definition:**
A tool for installing, updating, and managing software packages on a Linux system.
**Common Package Managers:**
1. apt (Advanced Package Tool): Used by Debian and Ubuntu-based systems.
2. yum (Yellowdog Updater Modified): Used by Red Hat-based systems.
**Package Repository:**
A centralized location where software packages are stored and can be downloaded and installed.

## 6.2 Installing and Removing Software Packages:
Installing with apt:
```
sudo apt install package_name
``````
Installing with yum:
```
sudo yum install package_name
``````
**Removing with apt and yum:**
```
sudo apt remove package_name
sudo yum remove package_name
```

## 6.4 Installing Different Extensions of Files in Linux
Some applications can be downloaded directly from the internet. The applications bear different extensions. See below how to install different extensions:

1 .deb (Debian Package) : For systems like Ubuntu or Debian, you can use dpkg or apt to install .deb files.
```
sudo dpkg -i package_name.deb
sudo apt-get install -f  # To fix any dependencies
```
2. .rpm (Red Hat Package Manager): On RHEL, CentOS, or Fedora systems, use rpm or dnf/yum to install .rpm files.
```
sudo rpm -i package_name.rpm

OR
sudo dnf install package_name.rpm
```
3. .tar.gz / .tar.bz2 (Compressed Archives): These are compressed archive files, often containing source code. You need to extract them first, then compile and install.
```
#Extract
tar -xzf package_name.tar.gz  # For .tar.gz files
tar -xjf package_name.tar.bz2  # For .tar.bz2 files

#Go to extracted folder and::
./configure
make
sudo make install
```

4. .AppImage (Portable Application): AppImages are self-contained executable applications.
```
chmod +x package_name.AppImage
./package_name.AppImage
```

5. .sh (Shell Script): .sh files are executable shell scripts that often contain installation instructions.
```
chmod +x script_name.sh
./script_name.sh
```



## 6.5 Checking Service Status
In Linux, the systemctl command is commonly used to manage and check the status of services.
- Check the status of a service:
```
sudo systemctl status <service_name>

OR
sudo service <service_name> status
```
This shows whether the apache2 service is running, stopped, or failed.
- Start a service:
```
sudo systemctl start <service_name>

OR

sudo service <service_name> start

```
- Stop a service
```
sudo systemctl stop <service_name>

OR

sudo service <service_name> stop

```
- Enable a service to start on boot:
```
sudo systemctl enable <service_name>

OR

sudo service <service_name> enable
```
- Disable a service from starting on boot:
```
sudo systemctl disable <service_name>

OR

sudo service <service_name> disable
```
- Restart a service:
```
sudo systemctl restart <service_name>

OR

sudo service <service_name> restart
```


## 6.6 Updating the System and Installed Packages:
Updating with apt:
```
sudo apt update      # Fetches the latest package information
sudo apt upgrade     # Upgrades installed packages
``````
Updating with yum:
```
sudo yum update      # Fetches and installs updates
``````

**Practice Exercise:**
1. Update package repository and Install nginx/httpd or any other package using apt or yum.
2. Start, stop and check the status of the installed package.
3. Remove the installed package.
4. Update the system and installed packages.


# 7. Networking Basics
1. **ssh (Secure Shell)**: Used to securely connect to a remote system over a network. See previous section on how to ssh into a Linux server.
2. **ping**: Used to test network connectivity between two machines by sending ICMP echo requests.
```
ping google.com
```
3. **wget** : A utility to download files from the web via HTTP, HTTPS, or FTP protocols.
```
wget http://example.com/file.zip
```
4. **scp (Secure Copy)**: Used to securely transfer files between a local system and a remote system, or between two remote systems, using SSH.
```
scp file.txt username@remote_host:/path/to/destination/
```
5. **rsync**: A fast and versatile file copying tool, especially useful for synchronizing files between local and remote systems.
```
rsync -avz /local/dir/ username@remote_host:/remote/dir/
```
This synchronizes the content of /local/dir/ with /remote/dir/. The -a preserves permissions and timestamps, -v is for verbosity, and -z compresses the data during transfer.

6. **Basic Ports**: Ports are logical channels through which network services communicate. Some common ports include:
- Port 22: SSH (Secure Shell)
- Port 80: HTTP (Web traffic)
- Port 443: HTTPS (Secure web traffic)
- Port 21: FTP (File Transfer Protocol)
- Port 25: SMTP (Simple Mail Transfer Protocol for email)
- Port 53: DNS (Domain Name System)

7. **DNS (Domain Name System)** : DNS translates human-readable domain names (like example.com) into IP addresses that computers use to identify each other on the network.

```
nslookup example.com
```
This command queries DNS to find the IP address associated with example.com. Alternatively, you can use dig for more detailed DNS queries:
```
dig example.com
```
