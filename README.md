![image](https://github.com/vivekraj2002/Ansible-/assets/139589508/26759fb1-df8c-4b2c-8f2a-ec7dcd4f30fa)

# Ansible-


1. [Introduction of ansible](#Introduction-of-ansible)
2. [Design Principles](#Design-Principles)
3. [Installation Setup and Getting Started](#Installation-Setup-and-Getting-Started)
4. [Features of ansible](#Features-of-ansible)
5. [Ansible Workflow](#Ansible-Workflow)
6. [Ansible Playbooks](#Ansible-Playbooks)
7. [Ansible Commands](#Ansible-Commands)
8. [Inventory of Ansible](#Inventory-of-Ansible)
9. [Working of Ansible](#Working-of-Ansible)
10. [Ansible Tower](#Ansible-Tower)
11. [conclusion](#conclusion)
   

# Introduction of ansible

Ansible is an open-source IT automation tool that simplifies and automates various manual IT processes, including provisioning, configuration management, application deployment, and orchestration. It is designed to be minimal, consistent, secure, and highly reliable, with an extremely low learning curve for administrators, developers, and IT managers.

## Design Principles

* **Agentless architecture**: Ansible uses an agentless architecture, which means it does not require any software or agents to be installed on the managed nodes. This reduces maintenance overhead by avoiding the installation of additional software across IT infrastructure.

* **Simplicity**: Ansible is designed to be simple, powerful, and easy to learn and use. It uses straightforward YAML syntax for code that reads like documentation.

* **Modularity**: Ansible uses modules to break down complex tasks into smaller, more manageable pieces.

## Installation Setup and Getting Started

### Prerequisites

1. Basic knowledge of linux.
2. A system with a supported OS (Linux, macOS, or Windows).

   
### Installation 
 Ubuntu-
 ```
sudo apt-get install ansible
```
get repositiries of ansible
```
sudo apt-add-repository ppa:ansible/ansible
```
check version of ansible
```
ansible --version
```
OUTPUT
```
ansible 2.9.6
  config file = /etc/ansible/ansible.cfg
  configured module search path = ['/home/vivek/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /usr/lib/python3/dist-packages/ansible
  executable location = /usr/bin/ansible
  python version = 3.8.10 (default, Nov 22 2023, 10:22:35) [GCC 9.4.0]
```





You can install a released version of Ansible with `pip` or a package manager. See our
[installation guide](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) for details on installing Ansible
on a variety of platforms.


## Features of ansible

* Ansible is an open source, command-line IT automation software application written in Python. It can configure systems, deploy software, and orchestrate advanced workflows to support application deployment, system updates, and more. Ansible's main strengths are simplicity and ease of use.

* Management
* Security
* Application deployment
* Provisioning
* Ansible
* Automation mesh
* Agentless
* Automation execution environments
* Inventories

## Ansible Workflow

Ansible works by connecting to our nodes and pushing out a small program called Ansible modules to them. Then Ansible executed these modules and removed them after finished. The library of modules can reside on any machine, and there are no daemons, servers, or databases required.

![image](https://github.com/vivekraj2002/Ansible-/assets/139589508/7ac376f4-de20-426f-98ff-097f2ff5ef37)

In the above image, the Management Node is the controlling node that controls the entire execution of the playbook. The inventory file provides the list of hosts where the Ansible modules need to be run. The Management Node makes an SSH connection and executes the small modules on the host's machine and install the software.


## Ansible Playbooks

Playbooks are the files where the Ansible code is written. Playbooks are written in YAML format. YAML means "Yet Another Markup Language," so there is not much syntax needed. Playbooks are one of the core features of Ansible and tell Ansible what to execute, and it is used in complex scenarios. They offer increased flexibility.

Playbooks contain the steps which the user wants to execute on a particular machine. And playbooks are run sequentially. Playbooks are the building blocks for all the use cases of Ansible.

Ansible playbooks tend to be more configuration language than a programming language.

Through a playbook, We can designate specific roles to some of the hosts and other roles to other hosts. By doing this, you can orchestrate multiple servers in very different scenarios, all in one playbook.

### Playbook Structure

Each playbook is a collection of one or more plays. Playbooks are structured by using Plays. There can be more than one play inside a playbook.

```
name: sample book
  - hosts: localhost
  tasks:
    - name: Update all packages to the latest version
      yum:
        name: '*'
        state: latest
    - name: run httpd
      service:
        name: httpd
        state: started
```

![image](https://github.com/vivekraj2002/Ansible-/assets/139589508/56c60157-1bc3-4c60-8c44-b17c085fe6a5)

## Ansible Commands

To install EPEL repo on Centos/RHEL systems.
```
sudo yum install epel-release
``` 
To install Ansible package on Centos/RHEL systems.
```
sudo  yum install -y ansible
```
To perform an update to the packages on Debian/Ubuntu systems.
```
sudo apt update
```  
To install the software properties-common-package on Debian/Ubuntu systems.
```
sudo apt install software-properties-common
``` 
To install Ansible personal package archive on Debian/Ubuntu systems.
```
sudo apt-add-repository ppa:ansible/ansible
```  
To install Ansible on Debian/Ubuntu systems.
```
sudo apt update
sudo apt install ansible
```  
To issue a ping command on all servers defined in the inventory file named hosts.
```
ansible -i hosts all -m ping
```
To issue a ping command only on hosts2.
```
ansible -i hosts all -m ping --limit host2
```  
To copy the file "testfile" on all hosts in the inventory file.
```
ansible -i hosts all -m copy -a "src=/root/test_ansible/testfile dest=/tmp/testfile"
```
To install ncdu package on all hosts.
```
ansible -i hosts all -m yum -a 'name=ncdu state=present'
```  
To remove ncdu package on all hosts.
```
ansible -i hosts all -m yum -a 'name=ncdu state=absent'
```
To build the directory structure for the role named role1.
```
ansible-galaxy init role1
```  
To dry-run p4.yml playbook.
```
ansible-playbook -i hosts p4.yml --check
```
To run a p4.yml playbook with password authentication for all hosts.
```
ansible-playbook -i hosts p4.yml -k
```
## Inventory of Ansible

Ansible works against multiple managed hosts in your infrastructure at the same time, using a list or group of lists is known as the inventory.

Once an inventory is defined, We use patterns to select the hosts or groups We want to run against to Ansible.

The default location for inventory is a file called /etc/ansible/hosts. We can also specify a different inventory file at the command line using the -i <path> option. We can pull the inventory file from dynamic or cloud sources or different formats (YAML, ini). Ansible has inventory plugins to make it flexible and customize.

### Hosts and group

The format is /etc/ansible/ hosts are in INI like format, such as:

```
mail.example.com  
  
[webservers]  
foo.example.com  
bar.example.com  
  
[dbservers]  
one.example.com  
two.example.com 
three.example.com
```
Heading in the brackets is a group name, which is used in classifying the systems. And deciding what policy we are controlling at what time and for what purpose. We can put the systems in more than one group.

For example, a server could be both a dbserver and a webserver.

If We have hosts that run on a non-standard SSH port, then We can put the port number after the hostname with the colon. The Ports listed in the SSH configuration file that can be used with the OpenSSH connection but not use with the paramiko connection.

To makes things explicit, it is suggested that We set them if items are not running on the default ports:
```
badwolf.example.com:5309
```
Suppose We have static IPs and want to set up some aliases that live in your host file, or we can connect through tunnels. Also, We can describe the hosts like the below example:
```
Jumper ansible_port=5555 ansible_host=192.0.2.50
```
## We run a command for check ansible host file :-

```
gedit /etc/ansible/hosts
```

## This is the default ansible 'hosts' file.

## It should live in /etc/ansible/hosts
   - Comments begin with the '#' character
  - Blank lines are ignored
  - Groups of hosts are delimited by [header] elements
  - You can enter hostnames or ip addresses
   - A hostname/ip can be a member of multiple groups

### Ex 1: Ungrouped hosts, specify before any group headers.

#green.example.com
#blue.example.com
#192.168.100.1
#192.168.100.10

### Ex 2: A collection of hosts belonging to the 'webservers' group

#[webservers]
#alpha.example.org
#beta.example.org
#192.168.1.100
#192.168.1.110

### If you have multiple hosts following a pattern you can specify
 them like this:

#www[001:006].example.com

### Ex 3: A collection of database servers in the 'dbservers' group

#[dbservers]
#
#db01.intranet.mydomain.net
#db02.intranet.mydomain.net
#10.25.1.56
#10.25.1.57

## Here's another example of host ranges, this time there are no
 leading 0s:

#db-[99:101]-node.example.com

![image](https://github.com/vivekraj2002/Ansible-/assets/139589508/6f79b855-1cc9-41db-9928-46aca8c4cec6)

#### Inventory basics formats 

We can create our inventory file in one of many formats, depending on the inventory plugins we have. The most common formats are INI and YAML. A basic INI /etc/ansible/hosts look like this :
```
mail.example.com

[webservers]
foo.example.com
bar.example.com

[dbservers]
one.example.com
two.example.com
three.example.com
```
Check here for build inventory [How to build inventory](https://docs.ansible.com/ansible/latest/inventory_guide/intro_inventory.html)

## Working of Ansible

Ansible interacts with our networks and sends little programs, known as modules, to them. These modules are utilized to complete automated tasks as systems designed to be resource models for the functioning at the desired state. Ansible runs these modules and eliminates them after they’re done. If modules weren’t available, We would have to depend on ad-hoc procedures and scripting to complete tasks. Ansible’s management node is the primary node overseeing the Playbook’s implementation.

![image](https://github.com/vivekraj2002/Ansible-/assets/139589508/f74aa2c3-ab0c-49b1-a285-9bb901ca9f34)

he manage node sets up an SSH connection before executing the modules and installing the product on the host workstations. Once the modules have been deployed, it eliminates them. So that’s how it works with Ansible. Python is used to create an Ansible script and connects remote hosts through SSH, specified in the inventory file. Ansible is agentless – implying that it doesn’t need any program to be installed on the nodes it controls.

## Ansible Tower

Ansible Tower employs a web-based user interface that makes it even more intuitive for IT team members of all system administration experience levels. When thinking of Ansible vs Ansible Tower, it’s helpful to consider Ansible Tower’s capabilities as an extension of those available in Ansible. 

### Its features include:

* Graphical user interface (GUI) dashboard
* Role-based access control 
* Job scheduling
* Multi-playbook workflows
* RESTful API
* External logging integrations
* Real-time job status updates

### Ansible Tower Architecture

There are three possible architectures available for Ansible Tower: single machine with integrated database, single machine with remote database, and high-availability multi-machine cluster. No matter which of the three you use, the primary architecture uses the same building blocks.

![image](https://github.com/vivekraj2002/Ansible-/assets/139589508/30e91854-64b8-404e-8832-71ef8963a6e0)


Users interface with the platform via the graphical web interface or its RESTful API.
Ansible Tower requires at least one host and one node.
Playbooks are prewritten YAML code that acts as the blueprint of automation tasks. They are lists of tasks that automatically execute against hosts.
Using Tower, a set, group, or classification of hosts runs playbooks.
Ansible Tower is agent-less, meaning it works by uploading modules to the node then executing them–no “agent” or need to install special software.


## conclusion

Ansible is a powerful open-source automation tool that simplifies the process of managing and orchestrating IT infrastructure, configuration management, application deployment, and various other tasks.

## THANKS.
