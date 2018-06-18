Assignment

Create an Ansible playbook to rotate ssh keys. Explaination - Replacing the keys you’re currently using with new keys, and removing the ability for old keys to be used to log into your systems.

         1. Create a new key
         2. Add new key to authorized_keys files on your nodes
         3. Test new key
         4. Remove previous keys from authorized_keys files on your nodes.
         5. again test the connectivity with the new keys.

Solution :

        1. Firstly i have created new ssh key file using command ssh-keygen for 'Vagrant' user at default location : /home/vagrant/.ssh/id_rsa1
        2. Now as per the given condition, i have taken reference of reference module and created a playbook.
           Please see below yaml file link :
           https://github.com/kamal24111991/AnsibleAssignment/blob/master/Day6Assignment/sshkeysrotation.yml
           
           Output screenshot:
           [[https://github.com/kamal24111991/AnsibleAssignment/blob/master/Day6Assignment/media/RotatingPlaybook.png]]
           [[ AnsibleAssignment/Day6Assignment/media/Validate.png ]]
           


