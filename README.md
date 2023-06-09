# Born2BeRoot
An introduction to virtualization using Debian Linux.

A Virtual Machine (VM)
-is like a computer within a computer.
-a software based emulation of a physical computer system.
-a VM is an isolated environment, seperate from your main computer system. Here, you can run different operating systems, software, applications, experiments, and tests without affecting your main computer.
-a VM works by mimicking the hardware componenets of a physical computer: CPU, RAM, storage, and network interfaces, creating a virtualised environment that behaves like a physical computer. Back to Evaluation Checklist

The differences between Rocky and Debian
-Debian has a community driven development model and a large community of contributers and users. Debian aims to be a universal Operating System, suitable for a wide range of use cases including desktop systems and personal servers. It adheres to the Free Software Principles (FSP): freedom to run, study, modify, and distribute software.
-Rocky is led by the Rocky Enterprise Software Foundation that oversees the development and distribution of Rocky Linux. Rocky provides an enterprise-grade linux that serves as a drop-in replacement for CentOS. It is designed, developed and tested to meet the demands of larger scale businesses and organisations. Back to Evaluation Checklist

The subject.pdf reccommends Debian
-for beginners in system administration, as setting up Rocky is more complex.
-Debian is user-friendly.
-Debian being older than Rockey, has a larger, active community of users and developers which means there is access to extensive documentation and resources for troubleshooting. Back to Evaluation Checklist

The difference between aptitude and apt
-aptitude more advanced and interactive, while apt is simpler and more straightforward.
-the main difference between aptitude and apt is how they handle package dependencies (other software needed for a program to work). aptitude is smarter at resolving complex dependencies and finding the best solution. It can suggest alternative options if there are conflicts between packages. apt, on the other hand, is simpler and more straightforward in resolving dependencies.
-Another difference is how you use them. apt has shorter and easier-to-remember commands, like apt update or apt install, while aptitude uses slightly different commands like aptitude update or aptitude install.
-aptitude has a special text interface that lets you browse and search for packages interactively, while apt doesn't have that feature. Back to Evaluation Checklist

AppArmor
-provides an additional layer of defense by restricting an application's privileges and actions to only what is explicitly permitted by its security policy.
-using AppArmor, system administrators and developers can enhance the security of their systems by limiting the potential impact of security breaches or unauthorized access to sensitive resources. It adds an extra layer of protection to help prevent applications from causing harm or accessing data they shouldn't have access to. Back to Evaluation Checklist

LVM
-stands for Logical Volume Manager.
-it allows the manipulation of partitions or logical volume on a storage device. Back to Evaluation Checklist

SSH
-stands for Secure Shell.
-an authentication mechanism between a client and a host.
-uses encryption techniques so that all communication between clients and hosts is done in encyypted form, preventing unauthorised access, protecting sensitive data. Back to Evaluation Checklist

UFW
-stands for Uncomplicated Firewall.
-an interface that modifies the firewall of a device without compromising security.
-used to configure which ports to allow connections, and which ports to close.
-useful in conjunction with SSH. Back to Evaluation Checklist

Short for "superuser do"
-sudo is a command used to execute other commands requiring higher priveledges and permissions.
-allows a user with admin priveleges to temporarily gain "root" or superuser priveledges. Back to Evaluation Checklist

To set up the password policy
-the command is sudo vim /etc/login.defs. Here we can adjust the frquency of:
-the maximum number of days before a password expiry.
-the minimum number of days allowed before the modification of a password.
-the number of days before a user receives a warning message their password is to expire. Back to Evaluation Checklist

The advantages of the password policy
-include increasing the security of the system.
-the disadvantages include the challenge of having to change passwords if frequent, and it can be difficult to create new and different passwords each time. Back to Evaluation Checklist

The sudoers file
-contains the configurations of user priveledges.
-using the command sudo visudo opens the sudoer's fie, and here, you can edit user priveledges. Back to Evaluation Checklist

The monitoring.sh script
-is used to monitor the performance and status of a server or system.
-it gathers data on system resource utilizaiton (e.g. CPU, memory, disk usage), network traffic and other metrics. Back to Evaluation Checklist

The wall command
-is used to broadcast a message (i.e. the monitoring.sh script) to all users currently logged on to the system. Back to Evaluation Checklist

Cron
-from the Greek word "chronos", means the measure of time.
-is a utility program that enables the scheduling of commands or scripts to run automatically at specified intervals.
-crontab is the configuration file where you can specify the commands to run and when.
-each asterisk *, accounts for: minute; hour; day; month; day of the week, in this order. Back to Evaluation Checklist
