The Assignment

    Create and delete ninja directory on host machine
         ansible all -m command -a "mkdir /kamal"

         ansible all -m command -a "rm -rf /kamal"

    Set hostname on all nodes from remote machine

        ansible 192.168.33.10 -m hostname -a "name=test1"

    Fetch os of all nodes and store o/p into a file, use min two different machine of different flavour of os.
        ansible all -m command -a 'cat /etc/os-release' > /kamal

    Add three group into hosts file through ansible module.

          Debian ( ip 192.168.33.101 of debian machine)
          Centos ( ip 192.168.33.10 of centos machine)
          All ( ip 192.168.33.10, 192.168.33.100, 192.168.33.101 of all nodes )
         
        ansible localhost -m lineinfile -a "path=/etc/ansible/hosts line=[Debian]\n192.168.33.101\n[Centos]\n192.168.33.10\n[All]\n192.168.33.10\n192.168.33.100\n192.168.33.101"

Problem statement: Using Adhoc command

Step 1:

    * Install apache on Debian machine

        ansible Debian -m command -a "apt-get update"
        ansible Debian -m apt -a "name=default-jdk state=present"
        ansible Debian -m a	pt -a "name=tomcat7 state=present"
      
        ansible Debian -m lineinfile -a "path=/etc/default/tomcat7 regexp='^JAVA_OPTS='  line='JAVA_OPTS=-Djava.security.egd=file:/dev/./urandom -Djava.awt.headless=true -Xmx512m -XX:MaxPermSize=256m -XX:+UseConcMarkSweepGC'"




    * Cross check apache isntalled or not from remote machine
         ansible Debian -m apt -a "name=tomcat7 state=installed"
       
    * Apache runn  on 8082 port
      
    * Create two virtual host
    * Restart apache from remote machine
        ansible all -m command -a "systemctl restart tomcat7"

Step2:

   * Install nginx on centos machine
       ansible centos -m yum -a "name=epel-release state=present"
        ansible centos -m yum -a "name=nginx state=present"

   * Nginx run on 8080 port.

         ansible centos -m lineinfile -a "path=/etc/nginx/nginx.conf regexp='^(.*)listen       80 default_server;(.*)$' line='listen       8080 default_server; '"

Step3:

   * Configure Nginx - configure it to run as reverse proxy to apache
      still working on this question...

