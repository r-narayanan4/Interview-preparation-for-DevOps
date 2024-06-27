# Shell Scripting Interview Questions

## What is Shell Scripting?

Shell scripting is the process of writing and executing a sequence of commands in a shell (command-line interface) to automate tasks or perform specific operations. It involves creating scripts (text files containing commands) that can be executed by the shell interpreter.

## Components of Shell Scripting

1. **Shell Interpreter:** The shell interpreter is the program that interprets and executes the commands written in the shell script. Common shell interpreters include Bash (Bourne Again Shell), sh (Bourne Shell), zsh (Z Shell), and csh (C Shell).

2. **Commands:** Shell scripts consist of various commands that perform specific actions, such as file manipulation, text processing, system administration, etc.

3. **Variables:** Variables are used to store data and values within shell scripts. They can be assigned values, manipulated, and used in commands or expressions.

4. **Control Structures:** Control structures such as if-else statements, loops (for, while), and case statements are used to control the flow of execution within shell scripts based on conditions.

5. **Functions:** Functions allow you to group a set of commands together and execute them as a single unit. They improve code organization, readability, and reusability.

## Benefits of Shell Scripting

1. **Automation:** Shell scripts automate repetitive tasks and streamline workflows, saving time and effort.

2. **Customization:** Shell scripts can be tailored to specific requirements and environments, providing flexibility and customization options.

3. **Integration:** Shell scripts can interact with other programs, utilities, and system resources, enabling seamless integration into complex systems.

4. **Portability:** Shell scripts are portable across different Unix-like operating systems, making them versatile tools for system administration and development tasks.

## Common Uses of Shell Scripting

1. **System Administration:** Shell scripts are used for system maintenance, configuration, monitoring, and troubleshooting tasks.

2. **File Management:** Shell scripts automate file and directory operations, such as copying, moving, renaming, and deleting files.

3. **Text Processing:** Shell scripts process text files, extract information, search for patterns, and perform text transformations using commands like grep, awk, and sed.

4. **Software Installation:** Shell scripts install, configure, and manage software packages and dependencies on Unix-based systems.

5. **Backup and Recovery:** Shell scripts automate backup creation, scheduling, and recovery processes to ensure data integrity and disaster recovery.

Overall, shell scripting is a powerful tool for system administrators, developers, and DevOps engineers to automate tasks, improve productivity, and manage complex systems efficiently.


## Basic Shell Scripting Questions for DevOps Engineers

Below are some basic shell scripting questions tailored for DevOps engineers:

1. **Automating Docker Container Deployment:**
   Write a shell script to automate the deployment of a Docker container.

2. **Disk Usage Monitoring and Email Alerting:**
   Create a script to check the disk usage on a Linux server and send an email alert if it exceeds a certain threshold.

3. **Web Server Uptime Monitoring and Restart:**
   Develop a script to monitor the uptime of a web server and restart it if it becomes unresponsive.

4. **Database Backup Automation:**
   Write a script to automate the backup of a database and upload it to a cloud storage provider.

5. **Software Packages Installation and Configuration:**
   Create a script to install and configure a set of software packages required for a development environment.

6. **Infrastructure Provisioning Automation:**
   Develop a script to automate the provisioning of infrastructure resources using a cloud provider's API.

7. **System Performance Monitoring and Logging:**
   Write a script to monitor system performance metrics (CPU usage, memory usage, disk I/O, etc.) and log them to a file.

8. **Kubernetes Cluster Deployment Automation:**
   Create a script to automate the deployment of a Kubernetes cluster.

9. **SSL Certificate Renewal Automation:**
   Develop a script to automate the SSL certificate renewal process for a web server.

10. **Microservice Architecture Deployment Automation:**
    Write a script to automate the deployment of a microservice architecture using Docker Compose or Kubernetes.

These questions cover a range of tasks commonly performed by DevOps engineers and require scripting knowledge to automate. They can be used for assessing a candidate's proficiency in shell scripting and DevOps practices during interviews or skill assessments.



# Shell Scripting Questions and Answers

## 1. List some of the commonly used shell commands.
- `ls` - List directory contents.
- `cp` - Copy files and directories.
- `mv` - Move or rename files and directories.
- `mkdir` - Create directories.
- `touch` - Change file timestamps or create empty files.
- `grep` - Search text using patterns.
- `top` - Display tasks and system resource usage.
- `df` - Report file system disk space usage.

## 2. Write a simple shell script to list all processes.
To list all processes:
```sh
ps -ef
# To list process IDs alone:
ps -ef | awk -F " " '{print $2}'
```


### 3. Write a script to print only errors from a remote log.
```markdown
# Print Only Errors from a Remote Log

```sh
curl google.com | grep HREF
```


### 4. Write a shell script to print numbers divided by 3 & 5 and not by 15 from 1-30.
```markdown
# Print Numbers Divided by 3 & 5 and Not by 15 from 1-30

```sh
for i in {1..100}; do
    if ([`expr $i % 3` == 0] || [`expr $i % 5` == 0]) && [ `expr $i % 15` != 0]; then
        echo $i
    fi;
done
```


### 5. Write a script to print the number of "S" in Mississippi.
```markdown
# Print Number of "S" in Mississippi

```sh
x=mississippi
grep -o "s" <<<"$x" | wc -l
```


### 6. How will you debug the shell script?
```markdown
# Debugging a Shell Script

Use `set -x` to enable debugging mode for your shell script.
```

### 7. What is crontab in Linux? Can you provide an example of usage?

# Crontab in Linux

Crontab is a command to schedule tasks to run at specific times or intervals.

Example usage:
```sh
# Run a script every day at 2 AM
0 2 * * * /path/to/script.sh
```


### 8. How to open a read-only file?
```markdown
# Open a Read-Only File

Use `vim -R` to open a file in read-only mode:
```sh
vim -R test.txt
```


### 9. What is the difference between soft and hard links?
```markdown
# Difference Between Soft and Hard Links

- **Hard Link**: Creates a mirror copy of the original file. Even if the original file is deleted, the hard link remains and the data is preserved.
- **Soft Link (Symbolic Link)**: Creates an alias for the file. If the original file is deleted, the soft link becomes invalid.
```

### 10. What is the difference between break and continue statements?
# Difference Between Break and Continue Statements

- **Break**: Terminates the execution of the current loop.
- **Continue**: Skips the current iteration and continues with the next iteration of the loop.

### 11. What are some disadvantages of shell scripting?

# Disadvantages of Shell Scripting

- Not suited for large and complex tasks.
- Each shell command execution launches a new process, which can be inefficient.


### 12. What are the different types of loops and when to use them?

# Types of Loops

- **For Loop**: Use when you know the exact number of iterations.
- **While Loop**: Use when the number of iterations is not known in advance and depends on a condition.
- **Until Loop**: Similar to while loop but continues until a condition becomes true.


### 13. Is bash dynamically or statically typed and why? What is meant by dynamic or statically typed?

# Bash Typing System

Bash is dynamically typed because variables can hold values of any type and can change types at runtime.

- **Dynamically Typed**: Variables do not have a fixed type and can hold different types of values.
- **Statically Typed**: Variables have a fixed type and can only hold values of that type.


### 14. Explain about a network troubleshooting utility.

# Network Troubleshooting Utility: Traceroute

`traceroute` is used to diagnose network issues by tracing the path packets take to reach a destination.

Example usage:
```sh
traceroute google.com
```


### 15. How will you sort a list of names in a file?
```markdown
# Sort a List of Names in a File

Use the `sort` command to sort a list of names:
```sh
sort filename.txt
```


### 16. How will you manage logs of a system that generate huge log files every day?
```markdown
# Manage Logs of a System

Use the `logrotate` command to manage large log files.

Example configuration:
```sh
# /etc/logrotate.d/myapp
/var/log/myapp/*.log {
    daily
    rotate 7
    compress
    missingok
    notifempty
    create 0640 myapp myapp
}
```



