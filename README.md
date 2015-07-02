# ansible-deluge
Spin up a torrenting server running Deluge in the cloud using ansible

**This is now deprecated in favour of the [AtoMiC-ToolKit](https://github.com/htpcBeginner/AtoMiC-ToolKit)**

# How it Works
The general idea is that given a server in the cloud e.g. on DigitalOcean and you would like to install Deluge on it,    
you just give Ansible your server address and you get back the Deluge BitTorrent Client fully configured and running on    
port `8112` of the server.

# Setup
First, Ansible needs to be installed, preferrably in a virtualenv. Let's do that

- Create a new virtual environment.    
`mkvirtualenv torrent`
- Activate the virtualenv    
`workon torrent`
- Install Ansible    
`pip install ansible`

# Usage Instructions

- Clone this repo    
`git clone https://github.com/kevgathuku/ansible-deluge`
- Change directory into the newly-created folder     
`cd ansible-deluge`
- Open the `hosts` file and replace `hostname1` and `hostname2` with your actual server address(es)    
You can fill in one or more server addresses here.

For example, a sample `hosts` file would look like this

```
[main]
127.0.0.1
```

When you've done this, let's finally get this running
```shell
ansible-playbook -i hosts playbook.yml
```

Now you can access the Deluge Web UI at `address:8112`     
where `address` is the address you provided in the hosts file
