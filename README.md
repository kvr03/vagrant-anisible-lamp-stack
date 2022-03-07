# vagrant-anisible-lamp-stack
### This repository will create a lamp stack using anisible playbooks and vagrant file


##### Tested on
+ vagrant version = 2.2.19

### Description
* Lamp stack: Ubuntu,apache2,mysql,python.
* Vagrantfile creates two vm's web and database.
* In web vm portforwarding is enabled from guest:80 to host:8080.
* Configuration files can be found under apache_ubuntu.