# Ansible Playbook for Installing Wordpress in both CentOS and Ubuntu

This Ansible Playbook will helps you to Install LAMP and LEMP in both CentOS and Ubuntu at a time. Ansible is an open source IT Configuration Management, Deployment & Orchestration tool. It aims to provide large productivity gains to a wide variety of automation challenges.


## Prerequisites
- Ansible version - 2.9
- Linux Master Server 
- Two Client Servers - CentOS, Ubuntu
- SSH PEM key for Remote Servers
- SSH User with sudo privilege

### Usage

This script will perform following operations;

- Installing Apache and Nginx Webserver
- Installing PHP and PHP Extenions
- Creating VirtualHosts
- Creating VirtualHost DocumentRoot
- Creating test.php info file
- Restarting and Enabling Services
- Installing MariaDB and MySQL Server
- Update root password in MariaDB and MySQL Server
- Removing anonymous users from Database
- Removing test databases
- Creating MariaDB and MySQL databases
- creating Database User & Database password
- Downloading Wordpress Tar File
- Extracting Wordpress Tar File
- Creating wordpress wp-config.php
- Post-Installation Restart of services
- Post-Installation Clean-Up of wordpress tmp files

# Ansible Installation

```sh
$ yum -y install ansible
```

## How to configure

With Ansible installed, you are ready to provision the remote server by following the below steps.

```sh
$ git clone https://github.com/sebinxavi/wordpress-setup.git
$ cd wordpress-setup
```

Open the file 'hosts' and edit the Remote hosts details

The Sample format is provided below,
```sh
[ubuntu]
172.31.45.194  ansible_user=ubuntu ansible_port=22 ansible_ssh_private_key_file=ubuntu.pem
[centos]
172.31.47.208  ansible_user=centos ansible_port=22 ansible_ssh_private_key_file=ubuntu.pem
```

- Add a Group name for the remote hosts. Example: centos/ubuntu
- Add the Remote Host IP addresse. Example: 172.31.43.55
- Add the Remote SSH User. Example: centos
- Add the SSH port number: Example: 22
- Import the SSH key file to the same location in which we are going to run the Ansible command and add the key name to the file hosts

Run the ansible-playbook from the master server by below command,

```sh
$ ansible-playbook -i hosts apache-nginx.yml
```

## Results
Access the IP address of the Remote Host servers in Browser and you can see the Wordpress page.

## Author
Created by [@sebinxavi](https://www.linkedin.com/in/sebinxavi/) - feel free to contact me and advise as necessary!

<a href="mailto:sebin.xavi1@gmail.com"><img src="https://img.shields.io/badge/-sebin.xavi1@gmail.com-D14836?style=flat&logo=Gmail&logoColor=white"/></a>
<a href="https://www.linkedin.com/in/sebinxavi"><img src="https://img.shields.io/badge/-Linkedin-blue"/></a>

