# Install [Docker CE](https://docs.docker.com/install/linux/docker-ce/debian/) & [docker-compose](https://docs.docker.com/compose/install/) on Debian 9 (stretch) with [Ansible](https://www.ansible.com/)

1. Clone this repository locally:
```git clone https://github.com/moovs/docker-with-ansible.git```
2. Add your ssh-key to the host you want to install docker:
```ssh-copy-id -i ~/.ssh/id_rsa.pub user@host```
- This logs into the server host, and copies keys to the server, and configures them to grant access by adding them to the authorized_keys file.
3. Just set up your server's IP in hosts file for example:
``` 
[my_group]
my_domain ansible_ssh_host=192.168.0.0 ansible_ssh_user=my_user
```
4. And run: 
```ansible-playbook -i hosts ./roles/docker/main.yml```
5. You have installed docker CE & docker-compose on your host :alien:
