## Lab Environment

For this portfolio, I am using an Ubuntu Linux environment to practice Linux system administration tasks while preparing for the LFCS exam.

This lab will be used to practice:
- Linux command line
- User and group management
- File permissions
- Storage and filesystems
- Networking
- Systemd services
- Bash scripting
- Troubleshooting

1. Why I chose a VM

I chose to use a virtual machine for this lab because it provides a safe and isolated environment for system administration practice.

Using a VM allows me to:
- Practice Linux administration without risking my personal operating system
- Take snapshots before major changes
- Restore the system after mistakes
- Create troubleshooting scenarios intentionally
- Document a clean and repeatable lab environment
- Practice tasks similar to real junior sysadmin work

2. VM specifications

- Virtualization software: Oracle VirtualBox
- Guest OS: Ubuntu Server 24.04 LTS
- Hostname: sys-admin-lab
- CPU: 2 cores
- RAM: 2 GB
- Disk: 25 GB
- Network mode: Bridge Adapter
- Main user: ana-lab


3. Initial system update

After installing Ubuntu Server, I updated the package list and installed available updates.

sudo apt update
sudo apt upgrade -y

4. System verification Summary

- Hostname: sys-admin-lab
- Operating system: Ubuntu Server 24.04 LTS
- Shell user: ana
- Disk layout: verified with `lsblk`
- Disk usage: verified with `df -h`
- Memory usage: verified with `free -h`
- Network interfaces: verified with `ip addr`
- Systemd installed: verified with `systemctl --version`

5. Snapshot strategy

I am using snapshots to protect the lab environment before making major system changes.

Snapshots allow me to save the current state of the virtual machine and restore it later if I make a mistake or intentionally break the system for troubleshooting practice.

My snapshot plan:

clean-install: taken after the Ubuntu Server installation and initial system update
before-users-groups-lab: before practicing user, group, sudo, and permission tasks
before-storage-lab: before practicing disks, partitions, filesystems, swap, and LVM
before-networking-lab: before practicing IP configuration, DNS, SSH, firewall rules, and routing
before-troubleshooting-lab: before creating intentional errors for troubleshooting practice

This strategy makes the lab safer because I can experiment, make mistakes, troubleshoot problems, and return to a working state.

6. Validation

I validated the lab setup by confirming that the VM boots successfully and that the main system administration tools are available.

I verified the environment using the following commands:

hostname
hostnamectl
lsb_release -a
uname -r
whoami
id
lsblk
df -h
free -h
ip addr
systemctl --version

Validation checklist:

The VM starts correctly
The hostname is configured
The operating system version is confirmed
The kernel version is confirmed
The lab user can log in
Disk layout is visible with lsblk
Filesystem usage is visible with df -h
Memory and swap information are visible with free -h
Network interfaces are visible with ip addr
Systemd is installed and available

This confirms that the VM is ready for future Linux system administration labs.

7. What I learned

This project helped me understand the importance of preparing a safe and repeatable Linux lab environment before practicing system administration tasks.

I learned that a virtual machine is useful because it allows me to practice without risking my personal operating system. I can take snapshots, make configuration changes, troubleshoot errors, and restore the system if needed.

I also practiced using basic system inspection commands to understand the current state of a Linux system before making changes. This is important because system administrators need to check the environment carefully before configuring users, storage, networking, services, or security settings.

