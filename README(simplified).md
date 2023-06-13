LINUX COMMANDS:

-Check Password Policy: sudo chage -l username

-Check UFW is started: sudo ufw status

-Check SSH is started: sudo systemctl status ssh

-Check chosen OS: lsb_release -a || cat /etc/os-release

-Check sudo group: getent group sudo

-Check user42 group: getent group user42

-Create new user: sudo adduser new_username

-Assign password: 
(sudo vim /etc/pam.d/common-password)
Find: password      requisite       pam_pwquality.so retry=3
Change to: password requisite pam_pwquality.so retry=3 minlen=10 ucredit=-1 dcredit=-1 maxrepeat=3 clearreject_username difok=7 enforce_for_root

(sudo vim /etc/login.defs)
Find: PASS_MAX_DAYS 9999 PASS_MIN_DAYS 0 PASS_WARN_AGE 7
Change to: PASS_MAX_DAYS 30 PASS_MIN_DAYS 0 PASS_WARN_AGE 7
(sudo reboot)

-Create "Evaluating" Group: (sudo groupadd evaluating) (sudo usermod -aG evaluating your_new_username)

-Check new user belongs to "evaluating": (getent group evaluating)

-Change Password Policy for New User: (sudo apt-get install libpam-pwqu) (sudo vim /etc/pam.d/common-password)
Find: password        requisite       pam_deny.so
Replace With: password        requisite       pam_pwquality.so  retry=3 minlen=10 ucredit=-1  maxrepeat=3 reject_username difok=7 enforce_for_root

-Check machine hostname is correctly formatted as btomlins42: (hostnamectl)

-Modify hostname by replacing with new login: (sudo hostnamectl set-hostname new_hostname)
(sudo reboot)

-View VM partitioning: (lsblk)

-Check sudo installation: (dpkg -l | grep sudo)

-Assign new user to sudo group: (sudo usermod -a -G sudo example)
(getent group sudo | cut -d: -f4 | tr','\n')

-See imposed rules for sudo: (sudo visudo ls)

-Verify /var/log/sudo exists: (cd /var/log/sudo) (cat sudo.log)

-Run a command via sudo and cheack if log has updated: (sudo echo "hello world") (cat sudo.log)

-Check UFW is installed properly: (sudo ufw status numbered)

-List active UFW rules, rule must exist for port 4242: (sudo ufw status numbered)

-Add rule to open port 8080: (sudo ufw allow 8080)

-Delete new rule: (sudo ufw delete 4) (sudo ufw delete 2)

-Check SSH service is installed and working: (sudo service ssh status)

-Verify SSH service only uses port 4242: (sudo nano /etc/ssh/sshd_config)

-Login as new user, then login using: (ssh new_user@127.0.0.1 -p 4242)

-Check you cannot user SSH with teh "root" user: (ssh btomlins42@127.0.0.1 -p 4242

-See monitoring.sh script: (sudo su-) (cd /usr/local/bin && vim monitoring.sh) (chmod +x monitoring.sh) (./monitoring.sh)

-Make sure monitoring.sh runs with dynamic values: (sudo crontab -u root -e) Change 10 value to 1

-Stop and start script: (sudo cronstop) (sudo cronstart)

-Check script still exists in the same place upon restart: (sudo reboot) (sudo crontab -u root -e)


EVALUATION CHECKLIST:

-A VM is a computer inside a computer

-Debian: Commutinity driven development with a wide variety of use cases (servers, desktop OS etc.)
Debian adhears to Free Software Principles: freedome to run, study, modify and distribute.

-Rocky: Led by Rocky Enterprise Software Foundation, designed and developed for large scale operations and businesses.

-I chose debian because it was reccommended in the subject pdf, far easier to install for a beginner, more user-friendly, 
has a much larger and more active community than Rocky which allows for more detailed setup tutorials and other support.

-Aptitude and apt are both package management tools used to install, upgrade and manage software packages.

-Aptitude: More advanced and interactive, smarter at resolving complex packages

-Apt: Easier/more straight forward to use

-AppArmor: Provides additional layer of defence (compared to UFW) by restricting an application's privliges and actions to
what is explicitly permitted by its security policy.

-LVM: Logical Volume Manager, for manipulation of partitions or logical volume on a storage device.

-SSH: Secure Shell, allows for communication between clients and hosts to be done in encrypted form, preventing unauthorised access.

-UFW: Uncomplicated Firewall, modifies the firewall of a device, used to configure which ports to allow connections and which to close.

-SUDO: Super-user Do, used to execute commands requiring higher privileges

-Password Policy: (sudo vim /etc/login.defs)

-Advantages of a Password Policy: Increases security of the system

-Disadvantages of a Password Policy: Challenging to create a new password if change is required frequently and 
to create a new password each time a reset is required.

-Sudoers File: Contains the configurations of user privileges, (sudo visudo) opens the sudoers file to edit user privileges.

-Monitoring.sh Script: Used to monitor performance and status of a server or system, data on system resource utilization, network traffic and other metrics.

-Wall Command: Used to broadcast a massage to all users currently logged into the system

-Cron (From the Greek word "chronos", means the measure of time): A utility program that enables the scheduling of commands or scripts to run at a specific time.
