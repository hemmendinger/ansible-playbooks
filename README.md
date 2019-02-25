# ansible-playbooks
Various Ansible playbooks


# Running 
## Hosts and Python
Bare Ubuntu 16.04 (Xenial Xerus) may lack "/usr/bin/python" but will have python3 available. Set a host specific variable:

    HOST ansible_python_interpreter=/usr/bin/python3


## Verbose dry run
ansible-playbook main.yml -i hosts --ask-become-pass --check --verbose
