# Ansible Interview Questions

## 1. What is configuration management?

Answer: Configuration management is the process of systematically handling changes to a system's configuration in a way that maintains integrity over time. It involves establishing and maintaining consistency of a system's performance, functional, and physical attributes with its requirements, design, and operational information.

## 2. Can you write an Ansible playbook to install an HTTPd service and get it running?

Answer:

```yaml
---
- name: Install and start Apache HTTPd
  hosts: all
  become: true
  tasks:
    - name: Install Apache HTTPd
      package:
        name: httpd
        state: present

    - name: Start HTTPd service
      service:
        name: httpd
        state: started
        enabled: yes
```

## 3. What is Ansible dynamic inventory?

Answer: Ansible dynamic inventory is a feature that allows Ansible to use external sources (such as cloud providers, inventory management systems, or custom scripts) to dynamically generate inventory information, enabling automation of tasks across changing infrastructure.

## 4. Can you explain the structure of an Ansible playbook using roles?

Answer: In Ansible, a playbook with roles typically consists of a directory structure where roles are organized into directories, each containing tasks, handlers, variables, and other files related to the role. This modular structure enhances reusability and maintainability of playbooks.

## 5. What are handlers in Ansible, and why are they used? Example

Answer: Handlers in Ansible are tasks triggered by other tasks, typically to restart services or perform other actions only when changes occur. They are used to ensure that certain tasks are executed only if necessary, optimizing the playbook execution process. An example could be restarting a web server after configuration changes.

example:

```yaml
---
- name: Example Playbook with Handlers
  hosts: all
  tasks:
    - name: Update configuration file
      template:
        src: myapp.conf.j2
        dest: /etc/myapp.conf
      notify: Restart service

  handlers:
    - name: Restart service
      service:
        name: myapp
        state: restarted
```

## 6. Does Ansible support parallel execution of tasks?

Answer: Yes, Ansible supports parallel execution of tasks by default. It can execute tasks on multiple hosts concurrently, improving overall playbook execution speed.

## 7. How do you handle secrets in Ansible?

Answer: Secrets in Ansible can be managed using Ansible Vault, which allows encryption of sensitive data such as passwords, API keys, or certificates. Ansible Vault encrypts files containing sensitive information, ensuring they are securely stored and managed within version control systems.

## 8. Can you talk about how Ansible playbook helped your company?

Answer: Ansible playbooks have helped streamline and automate various tasks in our organization, including configuration management, application deployment, and infrastructure provisioning. They have improved operational efficiency, reduced manual errors, and provided better consistency across environments.

## 9. What is an inventory?

Answer: In Ansible, an inventory is a file (or multiple files) that contain a list of managed hosts or nodes that Ansible can connect to and perform tasks on. The inventory file specifies information such as the hostnames or IP addresses of the managed nodes, the connection details (such as SSH port and username), and any additional variables needed for configuration.

## 10. Explain Ansible architecture.

Answer: Ansible follows a client-server architecture where the control node (Ansible host) communicates with managed nodes (hosts) over SSH. It does not require any agents on managed nodes, making it agentless. Ansible uses YAML-based playbooks to define tasks and executes them remotely on managed nodes using SSH.



## 11. What are the advantages of using Ansible?

Answer: Ansible offers several advantages, including:

- Agentless architecture: No need to install agents on managed nodes, reducing overhead and complexity.
- Simple YAML syntax: Playbooks are easy to read, write, and understand.
- Easy to learn: Ansible has a shallow learning curve, making it accessible to beginners.
- Powerful automation: Automates repetitive tasks, speeding up deployment and configuration processes.
- Extensibility: Ansible can be extended using modules, plugins, and roles to suit various use cases.
- Community support: Active community provides resources, modules, and documentation to help users.

## 12. What is meant by Ad-Hoc commands? Give one example.

Answer: Ad-Hoc commands in Ansible are one-off commands used to perform quick tasks on managed nodes without the need for a playbook. They are useful for tasks that do not require a playbook's structure. 
Example: 

```shell
ansible all -m ping
```

## 13. What is a “playbook”?

Answer: A playbook in Ansible is a YAML file that defines a series of tasks to be executed on managed nodes. Playbooks allow users to automate complex tasks and orchestrate configurations across multiple systems. They typically include tasks, variables, handlers, and other directives necessary for the automation process.

## 14. Briefly explain Ansible modules.

Answer: Ansible modules are standalone scripts that Ansible uses to perform specific tasks on managed nodes. They are the building blocks of Ansible automation and provide a way to interact with remote systems, execute commands, manage services, and more. Modules can be written in any programming language and are typically idempotent, ensuring consistent state across executions.

## 15. What is meant by Infrastructure as code?

Answer: Infrastructure as code (IaC) is an approach to managing and provisioning infrastructure through code and automation. Instead of manually configuring servers and resources, infrastructure is defined, managed, and deployed using code and configuration files. This approach improves consistency, repeatability, and scalability of infrastructure management processes.

## 16. What is a YAML file, and how is it used in Ansible?

Answer: YAML (YAML Ain't Markup Language) is a human-readable data serialization format commonly used in Ansible for writing playbooks, inventories, and configuration files. YAML files use indentation to represent data structures, making them easy to read and write. In Ansible, YAML files define tasks, variables, roles, and other configurations necessary for automation.

## 17. What is Ansible Galaxy?

Answer: Ansible Galaxy is a community hub for sharing Ansible roles, modules, and collections. It provides a repository of reusable content that users can leverage to accelerate development and deployment processes. Ansible Galaxy allows users to search, download, and share Ansible content, promoting collaboration and best practices within the Ansible community.

## 18. Define Ansible Vault.

Answer: Ansible Vault is a feature in Ansible that provides encryption and decryption of sensitive data such as passwords, API keys, and certificates. It allows users to securely store and manage sensitive information within Ansible playbooks, inventories, and configuration files. Ansible Vault ensures that sensitive data is protected and can be safely shared and version-controlled.

## 19. What is meant by Tags?

Answer: Tags in Ansible are labels assigned to tasks, roles, or plays within a playbook to selectively execute or skip them during playbook execution. Tags allow users to control which tasks are run based on specific criteria, such as environment, role, or functionality. Tags provide flexibility and granularity in playbook execution, enabling targeted automation of tasks.

## 20. What is jinja template?

Answer: Jinja is a template engine used in Ansible to dynamically generate content in playbooks and templates. Jinja templates allow users to insert variables, expressions, and control structures into configuration files, enabling dynamic configuration based on runtime data. Jinja templates are written using template tags, variables, and filters, providing powerful templating capabilities within Ansible.


## 21. Give some ansible modules.

Answer: Ansible provides a wide range of modules to interact with various systems and perform tasks. Some common Ansible modules include:

- `command`: Execute commands on remote nodes.
- `copy`: Copy files to remote nodes.
- `apt/yum/pacman`: Manage package installation on Linux systems.
- `file`: Manage files and directories on remote nodes.
- `template`: Render Jinja templates on remote nodes.
- `service/systemd`: Manage services on remote nodes.
- `debug`: Print debug messages during playbook execution.
- `lineinfile`: Modify lines in files on remote nodes.
- `shell`: Execute shell commands on remote nodes.
- `wait_for`: Wait for certain conditions to be met on remote nodes.

## 22. What are types of authentication we used in ansible?

Answer: Ansible supports several types of authentication for connecting to managed nodes, including:

- SSH keys: Ansible can authenticate using SSH keys, either passwordless or with passphrase.
- Passwords: Ansible can authenticate using username and password credentials for SSH or other protocols.
- Kerberos: Ansible supports Kerberos authentication for connecting to managed nodes in environments where Kerberos is configured.
- Certificates: Ansible can authenticate using client-side certificates for SSL/TLS connections.

## 23. What requirements do you need to run the Ansible server?

Answer: To run an Ansible server, you need:

- A supported operating system: Ansible can run on Linux distributions such as Ubuntu, CentOS, and Red Hat Enterprise Linux.
- Python: Ansible requires Python (version 2.7 or later) to be installed on the control node.
- Network connectivity: The control node must have network connectivity to the managed nodes over SSH or WinRM (for Windows).
- Inventory: Ansible requires an inventory file containing a list of managed nodes and their connection details.

## 24. How does Ansible function?

Answer: Ansible functions by executing tasks defined in playbooks on managed nodes via SSH or WinRM. The control node connects to managed nodes using SSH or WinRM and transfers the necessary tasks and files to execute on the managed nodes. Ansible uses modules to perform tasks on managed nodes, and these modules are executed remotely, returning results to the control node.

## 25. What is meant by Configuration Management Tool?

Answer: A Configuration Management Tool is a software tool used to automate the process of configuring and managing software and infrastructure. It allows administrators to define and enforce desired system configurations, ensuring consistency, reliability, and repeatability across environments.

## 26. Define idempotency.

Answer: Idempotency is a property of Ansible tasks and modules wherein applying the same configuration multiple times results in the same outcome. In other words, if a task or module is idempotent, running it multiple times will not change the system state after the initial execution. This ensures that the system remains consistent and predictable.

## 27. What is Ansible Inventory and its types?

Answer: Ansible Inventory is a file or directory containing a list of managed nodes and their connection details, such as IP addresses, hostnames, and connection protocols. There are two types of Ansible Inventory:

- Static Inventory: A static inventory file contains a static list of managed nodes and their details.
- Dynamic Inventory: A dynamic inventory script generates inventory information dynamically based on external sources, such as cloud providers or inventory management systems.


## Practical Examples of Ansible

## 1. Dive Into Ansible

[Dive Into Ansible](https://github.com/spurin/diveintoansible) is a repository containing practical examples and tutorials for learning Ansible. It covers various topics such as playbooks, roles, modules, and best practices. You can explore different use cases and scenarios to understand how Ansible can be applied in real-world scenarios.

## 2. ANSIBLE by r-narayanan4

[ANSIBLE by r-narayanan4](https://github.com/r-narayanan4/ANSIBLE.git) is another repository providing practical examples and playbooks for Ansible automation. It includes scripts and configurations for automating tasks related to infrastructure provisioning, application deployment, and system configuration management. You can use these examples to learn Ansible concepts and develop your automation skills.

Feel free to explore these repositories to gain hands-on experience with Ansible.
