##Scenario

A company needs a shared support folder.

Users:
- helpdesk01
- junioradmin

Groups:
- support
- sysadmins

Shared directory:
- /srv/support-docs

Goal:
- support group members can access the shared folder
- files belong to the support group
- permissions are verified with Linux commands

##Main Learning Points
- groupadd creates groups
- useradd creates users
- usermod -aG adds users to groups safely
- chown changes owner and group
- chmod changes standard permissions
- chmod 2770 enables setgid on a shared directory
- setfacl adds advanced ACL permissions
- getfacl verifies ACL permissions
- sudo -u tests commands as another user
