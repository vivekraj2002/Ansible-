![image](https://github.com/vivekraj2002/Ansible-/assets/139589508/26759fb1-df8c-4b2c-8f2a-ec7dcd4f30fa)

# Ansible-

[![PyPI version](https://img.shields.io/pypi/v/ansible-core.svg)](https://pypi.org/project/ansible-core)
[![Docs badge](https://img.shields.io/badge/docs-latest-brightgreen.svg)](https://docs.ansible.com/ansible/latest/)
[![Chat badge](https://img.shields.io/badge/chat-IRC-brightgreen.svg)](https://docs.ansible.com/ansible/latest/community/communication.html)
[![Build Status](https://dev.azure.com/ansible/ansible/_apis/build/status/CI?branchName=devel)](https://dev.azure.com/ansible/ansible/_build/latest?definitionId=20&branchName=devel)
[![Ansible Code of Conduct](https://img.shields.io/badge/code%20of%20conduct-Ansible-silver.svg)](https://docs.ansible.com/ansible/latest/community/code_of_conduct.html)
[![Ansible mailing lists](https://img.shields.io/badge/mailing%20lists-Ansible-orange.svg)](https://docs.ansible.com/ansible/latest/community/communication.html#mailing-list-information)
[![Repository License](https://img.shields.io/badge/license-GPL%20v3.0-brightgreen.svg)](COPYING)
[![Ansible CII Best Practices certification](https://bestpractices.coreinfrastructure.org/projects/2372/badge)](https://bestpractices.coreinfrastructure.org/projects/2372) 

1. [Introduction of ansible](#Introduction-of-ansible)
2. [Design Principles](#Design-Principles)
3. [Installation & Setup & Getting Started](#Installation-&-Setup-&-Getting-Started)
4. [Features of ansible](#Features-of-ansible)
5. [Ansible Workflow](#Ansible-Workflow)
6. [Ansible Playbooks](#Ansible-playbook)
7. [Ansible Commands](#Ansible-commands)
8. [Inventory of Ansible](#Inventory-of-Ansible)
9. [Working of Ansible](#Working-of-Ansible)
10. [Ansible Tower](#Ansible-Tower)
11. [Authors](#Authors)
12. [conclusion](#conclusion)
   

# Introduction of ansible

Ansible is a radically simple IT automation system. It handles
configuration management, application deployment, cloud provisioning,
ad-hoc task execution, network automation, and multi-node orchestration. Ansible makes complex
changes like zero-downtime rolling updates with load balancers easy. More information on the Ansible [website](https://ansible.com/).

## Design Principles

* Have an extremely simple setup process with a minimal learning curve.
* Manage machines quickly and in parallel.
* Avoid custom-agents and additional open ports, be agentless by
  leveraging the existing SSH daemon.
* Describe infrastructure in a language that is both machine and human
  friendly.
* Focus on security and easy auditability/review/rewriting of content.
* Manage new remote machines instantly, without bootstrapping any
  software.
* Allow module development in any dynamic language, not just Python.
* Be usable as non-root.
* Be the easiest IT automation system to use, ever.

## Installation & Setup & Getting Started

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

Ansible works by connecting to your nodes and pushing out a small program called Ansible modules to them. Then Ansible executed these modules and removed them after finished. The library of modules can reside on any machine, and there are no daemons, servers, or databases required.

![image](https://github.com/vivekraj2002/Ansible-/assets/139589508/7ac376f4-de20-426f-98ff-097f2ff5ef37)

In the above image, the Management Node is the controlling node that controls the entire execution of the playbook. The inventory file provides the list of hosts where the Ansible modules need to be run. The Management Node makes an SSH connection and executes the small modules on the host's machine and install the software.


## Ansible Playbooks

Playbooks are the files where the Ansible code is written. Playbooks are written in YAML format. YAML means "Yet Another Markup Language," so there is not much syntax needed. Playbooks are one of the core features of Ansible and tell Ansible what to execute, and it is used in complex scenarios. They offer increased flexibility.

Playbooks contain the steps which the user wants to execute on a particular machine. And playbooks are run sequentially. Playbooks are the building blocks for all the use cases of Ansible.

Ansible playbooks tend to be more configuration language than a programming language.

Through a playbook, you can designate specific roles to some of the hosts and other roles to other hosts. By doing this, you can orchestrate multiple servers in very different scenarios, all in one playbook.

### Playbook Structure

Each playbook is a collection of one or more plays. Playbooks are structured by using Plays. There can be more than one play inside a playbook.

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

## Coding Guidelines

We document our Coding Guidelines in the [Developer Guide](https://docs.ansible.com/ansible/devel/dev_guide/). We particularly suggest you review:

* [Contributing your module to Ansible](https://docs.ansible.com/ansible/devel/dev_guide/developing_modules_checklist.html)
* [Conventions, tips, and pitfalls](https://docs.ansible.com/ansible/devel/dev_guide/developing_modules_best_practices.html)

## Branch Info

* The `devel` branch corresponds to the release actively under development.
* The `stable-2.X` branches correspond to stable releases.
* Create a branch based on `devel` and set up a [dev environment](https://docs.ansible.com/ansible/latest/dev_guide/developing_modules_general.html#common-environment-setup) if you want to open a PR.
* See the [Ansible release and maintenance](https://docs.ansible.com/ansible/devel/reference_appendices/release_and_maintenance.html) page for information about active branches.

## Roadmap

Based on team and community feedback, an initial roadmap will be published for a major or minor version (ex: 2.7, 2.8).
The [Ansible Roadmap page](https://docs.ansible.com/ansible/devel/roadmap/) details what is planned and how to influence the roadmap.

## Authors

Ansible was created by [Michael DeHaan](https://github.com/mpdehaan)
and has contributions from over 5000 users (and growing). Thanks everyone!

[Ansible](https://www.ansible.com) is sponsored by [Red Hat, Inc.](https://www.redhat.com)

## License

GNU General Public License v3.0 or later

See [COPYING](COPYING) to see the full text.
