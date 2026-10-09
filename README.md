# ansible-ubuntu
Automate inital server setup using Ansible.

# How it Works
The general idea is that given a newly-created server and you would like to automate its initial setup, you would just run this script, instead of running most of the setup commands manually.

# Current Functionality
Currently, this is able to automate the following:
- Upgrading the distro
- Creates a regular user
- Install a few useful packages

# Setup
First, Ansible needs to be installed locally. This project uses `pipenv` (see `Pipfile`) by default.

- Install the dependencies (creates the virtualenv automatically)
`pipenv install`

# Usage Instructions

- Clone this repo
`git clone git@github.com:kevgathuku/ansible-ubuntu.git`
- Change directory into the newly-created folder
`cd ansible-ubuntu`
- Copy the `hosts.example` file to `hosts`
`cp hosts.example hosts`
- Open the `hosts` file and replace `127.0.0.1` with your actual server address(es)
You can fill in one or more server addresses here, each in a new line.

For example, a sample `hosts` file would look like this

```
[main]
127.0.0.1
127.0.0.2
```

When you've done this, let's finally get this running
```shell
pipenv run ansible-playbook -i hosts playbook.yml
```
