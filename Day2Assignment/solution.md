Perform the following operations using ad-hoc commands and ansible modules :

    Fetch and display to STDOUT Ansible facts using the setup module.
         ansible localhost -m setup -a "fact_path='/tmp'"

    Fetch and display only the "virtual" subset of facts for each host.
         ansible all -m setup -a 'gather_subset=virtual'

    Fetch and display the value of fully qualified domain name (FQDN) of each host from their Ansible facts.
         ansible all -m command -a 'hostname'


    Display the uptime of all hosts using the command module.

        ansible all -m command -a 'uptime'

    Ping all hosts except the 'control' host using the --limit option
        ansible all -m ping '--limit=!192.168.33.100'	

    Setup Java8 on the hosts in the "App" group using the apt module.
    I am using centos system, So i used yum module to instal java version 8. 
    
Installed java 8 on all the nodes.
        ansible all -m yum -u root -a "name=java-1.8.0-openjdk state=present"

    Setup and enable the EPEL package repository on the hosts in the "web" group using the yum module.

    CentOS systems use the latest epel-release package
        ansible all -m yum -u root -a "name=epel-release state=present"

    RHEL systems should use https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
    Create inventory groups app and web

    set a cron on ansible control machine that will run every 1 minute , and perform below tasks:-

    execute ansible adhoc commands on client machines (cannot be control machine) , to create a file in /var/log/ninja_name on all the client nodes, append system_hostname [:space:] system_time in the file every 1 minute using ansible facts.

        ansible all -m file -a 'dest=/opt/new.txt state=touch'
        ansible all -m command -a 'echo hostname >> /var/log/kamal'
        ansible all -m command -a 'echo date >> /var/log/kamal'   

