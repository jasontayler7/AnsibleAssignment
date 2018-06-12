The Assignment

-Use pip to install the ansible package and its dependencies to your control machine.
    
    sudo yum install python-pip
    sudo pip install ansible
    ansible --version

-Display the Ansible version and man page to STDOUT.

  ansible 2.5.1
  config file = /etc/ansible/ansible.cfg
  configured module search path = [u'/home/kamal/.ansible/plugins/modules', u'/usr/share/ansible/plugins/modules']
  ansible python module location = /usr/lib/python2.7/dist-packages/ansible
  executable location = /usr/bin/ansible
  python version = 2.7.15rc1 (default, Apr 15 2018, 21:51:34) [GCC 7.3.0]

https://github.com/kamal24111991/AnsibleAssignment/blob/master/Day1Assignment/media/STDOUT.png
     

-Check all the possible parameters you need to know in ansible.cfg file.

fork=10
    
https://github.com/kamal24111991/AnsibleAssignment/blob/master/Day1Assignment/media/forkvalue.png
    

-Ansible Inventory: Check the default inventory file for ansible control master and use inventory, run ansible ping commands on various inventory groups. Try this on minimum of two virtual machines.(You can use any of these Docker/Vagrant)
       
       Created [machine] entry in /etc/ansible/hosts
       Remote machine 192.168.33.100
       Remote machine 192.168.33.10
https://github.com/kamal24111991/AnsibleAssignment/blob/master/Day1Assignment/media/pingpong.png


    In ~/.ansible.cfg file (create the file if it doesn't exist already) do the following:

    Create a new directory ~/.ansible/retry-files and set retry_files_save_path to it.
    
https://github.com/kamal24111991/AnsibleAssignment/blob/master/Day1Assignment/media/forkvalue.png
    
    Set the Ansible system forks to 10
    Change the value of fork to 10 in /etc/ansible/ansible.cfg


Problem statement: Using Adhoc command

- Host a static website on minimum three hosts using inventory, content of static website is "Index page of Ansible assignment"
Document root /opt/html

Installed the nginx on remote machine using Ansible command.

https://github.com/kamal24111991/AnsibleAssignment/blob/master/Day1Assignment/media/NginxInstall.png

Transfer the Index.html file from master server to remote server path /opt/html.

Manually change the config file of nginx and alter document nginx default document root path /usr/share/nginx/html to /opt/html

Restarted the service of nginx and now static website contetnt serve on the dirctory /opt/html

Please also see attached static website content hosted on Vagrant 
https://github.com/kamal24111991/AnsibleAssignment/blob/master/Day1Assignment/media/Staticwebsite1.png

https://github.com/kamal24111991/AnsibleAssignment/blob/master/Day1Assignment/media/staticwebsite2.png
