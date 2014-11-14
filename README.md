ansible-lemp-centos7
====================

Full webstack for PHP developing - LEMP - Centos 7, Nginx, Percona Database, PHP-FPM 5

- Requirements
	- Vagrant with Virtual Box
	- Ansible

- Get Centos 7 Box
	- You can create clean - fresh your centos 7 base box.
	This is my guide: 
	https://docs.google.com/document/d/1MXsEFN6GFrRGJqcIsuTJAXqLXaHFPcx7Np_6WnZzBo8/view?usp=sharing

	- You can download my clear - fresh centos 7 base box:
	https://drive.google.com/file/d/0B03Th23o5fswV3ZNWEFSNTRHdkk/view?usp=sharing

	- Default installed account:
		- root/gxccms.com
		- vagrant/gxccms.com

- Check out this git. Type this command:
	```
		git clone git@github.com:gxcsoft/ansible-lemp-centos7.git
	```
	
- Local vagrant developement machine
	- Move to check out folder
	- vagrant box add gxc your_centos_7_box_location
	- vagrant up
	- vagrant provision (to run ansible if vagrant up is not run provision automatically)
	- vagrant ssh (access to your new virtual machine)

- Production server
	- Move to check_out_folder/ansible
	- Create your_server_role_config.yml. Here is an example:
	```
		---
		- hosts: host_config_name
		  sudo: yes
		  roles:
		  - common
		  - percona
		  - nginx
		  - php-fpm-55
		  - nginx-conf
	```

	- Add server ip address in to hosts. Here is an example:
	```
		[host_config_name]
		128.199.179.xx
	```

	- Type this command to run ansible (ansible must be installed)
	```
		ansible-playbook -i ./hosts -u your_server_ssh_account your_server_role_config.yml
	```

- Any questions? Please add new issue or send me an email <tung@gxccms.com>

