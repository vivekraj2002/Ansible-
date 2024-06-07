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

1. Introduction of ansible
2. Design Principles
3. Instalation & Setup & Getting Started
4. Features of ansible
5. Components of ansible
6. Alternative of ansible
7. Coding Guidelines
8. Authors
9. conclusion
   

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

## Instalation & Setup & Getting Started

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
