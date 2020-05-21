# System setup 

This project is not yet finished nor is it stable.

## Project information

This project serves the purpose to setup-up a fresh System with as few steps as possible.


### Current condition

Currently it is only created to work on Ubuntu.
It is mostly tested tested on WSL as well as Zorin OS (Ubuntu based os).


### Outlook

Additionally to an improved system setup on Ubuntu, Arch, Debian and Fedora will hopefully be included in the future.


## Installation

Clone this repo `git clone https://gitlab.com/till-personal/system-setup.git` to a desired folder. 
Run the given `setup.sh` script to install ansible and setup the repository folder for useage.

## Usage

Before running the ansible playbook you need to configure it to your desired state.
This prosses is not yet optimized and still takes a few steps. This will be improved in the future.

### Configuration

`system_setup.yml` contains a list of all roles that will be executet.
To prevent a roles from executing, comment the line with a `#` infront of the dash.

Some roles need aditional configuration. If no configuration is given, the default values are taken.
To override the defaults, redefine the variable in `host_vars/localhost` in a file of your choice.
Every configuration file uses `YAML` syntax.
`vars.yml` defines some basics paths and configurations on what should be installed.
To set your own configuration, create a file inside `host_vars/localhost` or use add to the existing `vars.yml`.
It is recomended to encrypt this file using `ansible-vault`, if it contains sensitive data. 

The `vault.yml` exists for ease of production and can only be used with the correct password.
For ansible to run, this file needs to be removed if the password is unknown.

Since ansible needs root permissions for some actions, you also need to provide the sudo password. 
This can be done by setting the `ansible_become_pass` variable to your sudo password.
Alternativly you can set the `ask_vault_pass` option in `ansible.cfg` to `true`. 
This cases ansible to ask for a sudo password directly after you start it.
Since this project structure may be changing, the `ask_vault_pass` option might be set to `true` by default. You want to disable it if 
you choose to use the password file approuch, since this option overrides the password file.

__It is recommended to rafrain from changing variables in any other place than [host_vars/localhost](host_vars/localhost).__

The possible configurations of a role are documented in their respected folder (`roles/{role}/README.md`).


### Execution

Since this Project is in the very early stages, some settings may need to be ajusted for ansible to run properly.
If you encrypted your config file with `ansible-vault` you need to provide a password. 
To provide a password you can either run ansible with the option `--ask-vault-pass` or create a password file e.g. `.vault_pass.txt`.
To give ansible the password file you can set the enviroment variable `export ANSIBLE_VAULT_PASSWORD_FILE=.vault_pass.txt` or run with 
the option `--vault-password-file .vault_pass.py`.


After all is set up you can start the system setup by running `ansible-playbook system_setup.yml`
