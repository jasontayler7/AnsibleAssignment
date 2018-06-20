## The Assignment

 
1. Create 5 users with password, and these five users should have same permissions for a directory named ninja.(Directory can be created with the 5 users permmission.)
1. Create ssh key for each user so that  all those 5 users will be able to login through ssh.

1. Creat Logical Volume in any node machine.
1. need to installl lvm2 first using ansible.
1. Create ext4 type File System on the newly created logical volume.
1. Mount newly created file system.


Solution :

Step 1 Install lvm2

Step 2 Created Volume Group

Step 3 Created logical volume

Step 4 mount the newly created lvm and created entry in fstab

Please see yaml file links :

User management : https://github.com/kamal24111991/AnsibleAssignment/blob/master/Day8Assignment/users.yml

![usernameplaybook](https://github.com/kamal24111991/AnsibleAssignment/blob/master/Day8Assignment/media/usernameplaybook.png)


Please see yaml file links :

LVM :https://github.com/kamal24111991/AnsibleAssignment/blob/master/Day8Assignment/lvm.yml

![lvmvalidate](https://github.com/kamal24111991/AnsibleAssignment/blob/master/Day8Assignment/media/lvmvalidate.png)

 ![lvdisplay](https://github.com/kamal24111991/AnsibleAssignment/blob/master/Day8Assignment/media/lvdisplay.png)
 
 ![extensionvalidate](https://github.com/kamal24111991/AnsibleAssignment/blob/master/Day8Assignment/media/extensionvalidate.png)


