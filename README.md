# Introduction to Linux Commands
# 1. Introduction to Linux
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
  - Ubuntu
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
## 2.1 Logging into a Linux System
1. **Local Login**: Physically at the machine, using a keyboard and monitor.
2. **SSH (Secure Shell)***: Remotely access a machine over a network.

## 2.2 Overview of the Linux Terminal:
## Components:
1. Shell: Interpreter that processes commands. Common shells include Bash, Zsh, and Fish.
2. Prompt: Indicates readiness for user input.
3. Command Line: Area for entering commands.
4. Terminal Emulator: Software that emulates a physical terminal.

## 2.3 Basic Commands for Navigation
**cd (Change Directory):**
Change the current working directory.
```bash
cd /path/to/directory
``````
**ls (List):**
List files and directories in the current directory.
```bash
ls
`````
**pwd (Print Working Directory):**
Display the current working directory's full path.
```bash
pwd
````

**Practice Exercise:**
1. Have students practice logging in using SSH to a remote machine.
2. Navigate through directories using cd, list contents with ls, and print the working directory with pwd.

   

# 3. File and Directory Management
## 3.1 Creating and Deleting Files and Directories:

**mkdir (Make Directory):**
Create a new directory.
```bash
mkdir directory_name
````
**touch:**
Create an empty file or update the access and modification time of a file.
```bash
touch filename
``````
**rm (Remove):**
Remove files or directories.
```bash
rm filename
rm -r directory_name  # Remove directory and its contents
``````
## 3.2 Copying and Moving Files and Directories:

**cp (Copy):**
Copy files or directories.
```bash
cp source destination
``````
**mv (Move):**
Move files or directories (also used for renaming).
```bash
mv source destination
``````
## 3.3 Listing and Viewing File Content:

**ls (List):**
List files and directories in the current directory.
```bash
ls
``````
**cat (Concatenate):**
Display the contents of a file.
```bash
cat filename
`````
**more and less:**
View the contents of a file one screen at a time.
```bash
more filename
less filename
`````

**Practice Exercise:**
1. Create a directory, navigate into it, and create files using touch.
2. Copy and move files between directories using cp and mv.
3. List files and view their content using ls, cat, more, and less.


# 4. Text Manipulation
## 4.1 Working with Text Files:

**echo:**
Display a line of text or enable/disable the echoing of commands.
```bash
echo "Hello, Linux!"
``````
**Text Editors:**
nano: Simple text editor for beginners.
```bash
nano filename
``````
**vim: Powerful and efficient text editor.**
```bash
vim filename
``````
## 4.2 Searching for Text in Files:
**grep (Global Regular Expression Print):**
Search for a specific pattern or text in files.
```bash
grep pattern filename
``````
## 4.3 Redirecting and Combining Commands:
**> (Output Redirection):**
Redirects command output to a file, overwriting existing content.
```bash
command > filename
``````
**>> (Append):**
Appends command output to a file.
```bash
command >> filename
``````
**| (Pipe):**
Passes the output of one command as the input to another.
```bash
command1 | command2
``````
**Practice Exercise:**
1. Use echo to create and display text.
2. Create and edit text files with nano and vim.
3. Search for specific patterns in files using grep.
4. Redirect and combine commands using >, >>, and |.

# 5. Permissions and Ownership

# 6. System Information

# 7. Package Management

# 8. Tips and Tricks
