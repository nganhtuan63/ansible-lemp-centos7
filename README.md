ansible-lemp
============

Full webstack for PHP developing - LEMP - Centos 7, Nginx, Percona Database, PHP-FPM 5

1. Requirements
	- Vagrant with Virtual Box
	- Ansible

2. Get Centos 7 Box
	- You can create clean - fresh your centos 7 base box.
	This is my guide: 
	https://docs.google.com/document/d/1MXsEFN6GFrRGJqcIsuTJAXqLXaHFPcx7Np_6WnZzBo8/edit?usp=sharing

	- You can download my clear - fresh centos 7 base box:
	<uploading to my db - update later>

3. Check out this git
	git clone git@github.com:gxcsoft/ansible-lemp-centos7.git

4. Local vagrant developement machine
	- Move to check out folder
	- vagrant box add gxc your_centos_7_box_location
	- vagrant up
	- vagrant provision (to run ansible if vagrant up is not run provision automatically)
	- vagrant ssh (access to your new virtual machine)

5. Production server
	- Move to check_out_folder/ansible
	- Create your_server_role_config.yml. Example:
		---
		- hosts: host_config_name
		  sudo: yes
		  roles:
		  - common
		  - percona
		  - nginx
		  - php-fpm-55
		  - nginx-conf

	- Add server ip address in to hosts:
		[host_config_name]
		128.199.179.75
		
	- Type this command to run ansible (ansible must be installed)
		ansible-playbook -i ./hosts -u your_server_ssh_account your_server_role_config.yml

Any questions? Please create new issue or send me an email <tung@gxccms.com>

