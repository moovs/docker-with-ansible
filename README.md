# 1. Install [Docker CE](https://docs.docker.com/install/linux/docker-ce/debian/) & [docker-compose](https://docs.docker.com/compose/install/) on Debian 9 (stretch) with [Ansible](https://www.ansible.com/)

Step 1. Clone this repository locally:
```git clone https://github.com/moovs/ansible.git```
Step 2. Add your ssh-key to the host you want to install docker:
```ssh-copy-id -i ~/.ssh/id_rsa.pub user@host```
- This logs into the server host, and copies keys to the server, and configures them to grant access by adding them to the authorized_keys file.
Step 3. Just set up your server's IP in hosts file for example:
``` 
[my_group]
my_domain ansible_ssh_host=192.168.0.0 ansible_ssh_user=my_user
```
Step 4. And run: 
```ansible-playbook -i hosts ./roles/docker/main.yml```
Done ✅ 5. You have installed docker CE & docker-compose on your host :alien:

***
# 2. Install [MegaCLI](http://hwraid.le-vert.net/wiki/DebianPackages) on Debian 9 (stretch) with [Ansible](https://www.ansible.com/)

1. If you want to install MegaCLI for RAID status you need to make the first three steps the same as described above, just change it.<br />
```step 4```<br />
to:<br />
```ansible-playbook -i hosts ./roles/megacli/main.yml```
