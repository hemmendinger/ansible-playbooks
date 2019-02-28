# ansible-playbooks
Various Ansible playbooks


# DeepstreamIO
## About
This creates a bare bones installation of Deepstream with Rethinkdb.

What it does not do:
- RethinkDB is installed but disabled, to enable see  http://www.rethinkdb.com/docs/guides/startup/
  - See section "Starting RethinkDB instances"
- Deepstream is installed but unconfigured and not running
- The RethinkDB interface for Deepstream is not installed
  - Install using: deepstream install storage rethinkdb
  - If using Deepstream Node.js interface the interface can be managed as an NPM module
- It performs no additional configuration beyond what is specified below
- It uses a minimal Ansible playbook structure 

What it does:
- Tested to work on Ubuntu 16.04
- Performs the "Basic setup" portion of the "Startup with systemd" section of the RethinkDB startup guide
- Installs:
  - RethinkDB from official repo
  - Deepstream from official repo
  - nodejs and npm 



## Running 
### Hosts and Python
Bare Ubuntu 16.04 (Xenial Xerus) may lack "/usr/bin/python" but will have python3 available. Set a host specific variable:

    HOST ansible_python_interpreter=/usr/bin/python3


### Verbose dry run
ansible-playbook main.yml -i hosts --ask-become-pass --check --verbose
