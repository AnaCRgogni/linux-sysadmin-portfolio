# Commands Used - Users, Groups, and Permissions Lab

## Group Management

sudo groupadd support
sudo groupadd sysadmins
getent group support
getent group sysadmins

##User Management
sudo useradd -m -s /bin/bash helpdesk01
sudo useradd -m -s /bin/bash junioradmin
id helpdesk01
id junioradmin

##Add Users to Groups
sudo usermod -aG support helpdesk01
sudo usermod -aG support,sysadmins junioradmin
id helpdesk01
id junioradmin

##Shared Directory Setup
sudo mkdir -p /srv/support-docs
sudo chown root:support /srv/support-docs
sudo chmod 2770 /srv/support-docs
ls -ld /srv/support-docs

##Test Access as Different Users
sudo -u helpdesk01 touch /srv/support-docs/helpdesk-note.txt
sudo -u junioradmin touch /srv/support-docs/admin-note.txt
ls -l /srv/support-docs

##ACL Setup and Verification
sudo apt install acl -y
getfacl /srv/support-docs
sudo setfacl -m u:junioradmin:rwx /srv/support-docs
getfacl /srv/support-docs
ls -ld /srv/support-docs

##Unauthorized User Test
sudo useradd -m -s /bin/bash outsider01
id outsider01
sudo -u outsider01 touch /srv/support-docs/outsider-note.txt

Expected result: Permission denied

##Default ACLs
sudo setfacl -d -m g:support:rwx /srv/support-docs
getfacl /srv/support-docs

##Useful Verification Commands
ls -ld /srv/support-docs
ls -l /srv/support-docs
getfacl /srv/support-docs
id helpdesk01
id junioradmin
id outsider01

