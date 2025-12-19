
------------------------------------------------------------------

# Chapter 2 – Using Essential Tools

### Theory 
- Shell
- Bash
- Alias
- Internal command
- External command
- Redirection(stdin, stdout, stderr, append)
- Device files
- Pipe
- History
- Bash completion
- Environment
- Variables(environment vs shell/local variables)
- Login shell
- Subshell
- Command search order (alias → functions → builtins → $PATH)
- Exit status and $?

### Commands / Variables
- `$PATH`
- `>`, `>>`, `2>`, `2>&1`,  `<`
- `echo`
- `printf`
- `which`
- `type`
- `alias, unalias`
- `history`
    Ctrl-r
    `!integer`
    `history -d integer`
    `!string`
    `history -c`
    `history -w`
- `$LANG`
- `--help`
- `man`
    `man -k`
    `man -k partition | grep 8`
- `mandb`
- `apropos`

### Files / File Configurations
- /etc/profile
- /etc/bashrc
- ~/.bash_profile
- ~/.bashrc
- ~/.bash_logout
- /etc/motd
- /etc/issue

### File Configurations
- ` export MY_VAR="some_value`
- ` export PATH=$PATH:/my/custom/directory`
- `MY_LOCAL_VAR="value" (non-exported shell variable)`
- `Simple aliases in ~/.bashrc, for example: alias ll='ls -l'`

### Man Pages
- man bash
- man sh
- man 1 intro
- man 1 man 

### Exam Tips
- Practice distinguishing internal vs external commands with type and which.
- Practice creating, exporting, and persisting variables/aliases via ~/.bashrc and ~/.bash_profile.
- Use man -k and apropos constantly so command discovery is automatic under time pressure.

------------------------------------------------------------------

# Chapter 3 – Essential File Management Tools

### Theory
- Device
- Root Directory
- Device File
- Globbing / wildcards
- Absolute Pathname
- Relative Pathname
- Hidden Files
- Inodes
- Hard Links
- Soft / Symbolic Links
- Compression   
- FHS File System Hierarchy 

### Command/Variables
- `find`
    `find -inum "inode number"`
    `find -name "pattern"`
    `find -iname "pattern`
    `find -type f/d/l`
    `find -size +100M/-1k`
    `find -user username/-group group`
    `find -mtime -1/+7`
    `find -perm 755/-644`
    `find -exec cmd {} \;`
    `find -delete`
- `mount`
- `df`
    `df -Th`
- `findmnt`
- `touch`
- `*, ?, [], [!]`
- `ls`
    `ls -l`
    `ls -a`
    `ls -lrt`
    `ls -d`
    `ls -R`
- `cp`
    `cp -R /etc /tmp`
    `cp /somedir/.* /tmp`
    `cp -a /somedir/ .`
    `cp -a /somedir/. .`
- `mv`
    `mv myfile /tmp`
    `mkdir somefiles; mv somefiles /tmp`
    `mv myfile mynewfile`
- `rm`
    `rm -rf`
- `mkdir`
    `mkdir -p`
- `rmdir`
- `ln`
    `ln /etc/hosts .`
    `ln -s /etc/hosts .`
    `ln -s /home /tmp`
- `tar`
    `tar -cvf /root/homes.tar /home`
    `tar -rvf /root/homes.tar /etc/hosts`
    `tar -uvf /root/homes.tar /home`
    `tar -tvf /root/homes.tar`
    `tar -xvf /archivename.tar`
    `tar -xvf /root/homes.tar`
    `tar -xvf homes.tar -C /tmp`
    `tar -xvf /root/etc.tar etc/hosts`
    `-z`, `-j`, `-J`
- `gzip`
- `bzip2`

### Files / File Configurations

### Man Pages 
man 7 file-hierarchy

### Exam Tips

------------------------------------------------------------------

# Chapter 4 – Working with Text Files

### Theory
- Line Anchor
- Escaping
- Regular Expressions

### Command/ Varaibles
- `less`
    `?sometext`
    `/sometext`
    `less +F /var/log/messages`
- `cat`
    `cat -n file`
- `head`
    `head -n 11 /etc/passwd | tail -n 1`
    `head -n 5 file`
- `tail`
    `tail -n 5 /etc/passwd`
    `tail -f /var/log/messages`
    `tail -n 5 file`
- `cut`
    `cut -d : -f 1 /etc/passwd`
    `cut -f 1 -d : /etc/passwd | sort`
- `sort`
    `sort /etc/passwd`
    `du -h | sort -rn`
    `sort -k3 -t : /etc/passwd`
    `ps aux | sort -k 4 -n`
- `wc`
    `ps aux | wc`
- `grep`
    `grep anna /etc/passwd`
    `grep ^anna /etc/passwd`
    `grep ash$ /etc/passwd`
    `grep '^anna' /etc/passwd`
    `^`, `$`, `.`, `[abc]`, `?`, `+`, `*`, `(...)`, `|`, `colou?r`
    `grep -i pattern file`
    `grep -v pattern file`
    `grep -r pattern /path`
    `grep -E 'pat1|pat2' file`
- `awk`
    `awk -F : '{ print $4 }' /etc/passwd`
    `awk -F : '/user/ { print $4 }' /etc/passwd`
    `awk -F: '{print $1,$3}' /etc/passwd`
    `awk -F: '$3 >= 1000 {print $1,$3}' /etc/passwd`
    `sed 's/old/new/g' file > file.new`
- `sed`
    `sed -n 5p /etc/passwd`
    `sed -i s/old-text/new-text/g ~/myfile`
    `sed -i -e '2d' ~/myfile`
    `sed -i -e '2d;20,25d' ~/myfile`
    `sort file | uniq`
    `sort file | uniq -c`

### Files / File Configurations
- man 7 regex

### Man Pages

### Exam Tips
- Always verify with non‑destructive commands before sed -i or overwriting files.
- Remember that on exam, using built‑in docs (man, --help) is allowed and expected.

------------------------------------------------------------------

# Chapter 5 – Connecting to Red Hat RHEL

### Theory
- Console
- Terminal
- Changing Terminals wth alt-ctrl F1-F6
- tty
- psudeo terminal
- Subshell
- Key-based login
- Public key
- Private key
- X11 server
- Root User privileges
- SSH host keys
- shell environments

### Commands/ Variables
- `sudo`
- `term`
- `su`
- `chvt`
- `w`
- `who`
- `systemctl reboot`
- `systemctl halt`
- `systemctl poweroff`
- `ssh`
    `ssh root@192.168.29.161`
    `ssh -Y linda@server2`
    `-v`, `-Y`, `-p <>`
- `systemctl`
    `systemctl status sshd`
    `systemctl start|stop|enable|disable sshd`
- `ip a | grep 'inet '`
- `sed -i -e '25d' ~/.ssh.known_hosts`
- `scp`
    `scp /etc/hosts server2:/tmp`
    `scp root@server2:/etc/passwd ~`
    `scp -r server2:/etc/ /tmp`
    `-P`
- `sftp`
    `sftp student@server2`
- `rsync`
    `-r`, `-l`, `-p`, `-n`, `-a`, `-A`, `-X`
- `ssh-keygen`
    `ssh-keygen -t ed25519`
- `ssh-copy-id`

### Files / File Configurations
- ~/ssh
- ~/.ssh/authorized_keys
- ~/.ssh/config
- /etc/ssh/ssh_config
    `ForwardX11 yes`
    `PermitRootLogin no`
    `PasswordAuthentication no`
    `PubkeyAuthentication yes`
- /etc/ssh/sshd_config

# Man Pages
- `man ssh`
- `man sshd_config`
- `man ssh-keygen`
- `man sftp`
- `man rsync`

# Exam Tips

------------------------------------------------------------------

### Chapter 6 – User and Group Management

# theory
- privileged users
- unprivileged users
- root
- Wheel group
- UID
- GUID
- Home directory
- Default shell
- Primary group

# commands/variables
- `last`, `lastb`
- `id`
- `sudo`
- `su`
- `whoami`
- `usermod -aG wheel user`
- `visudo`
- `pkexec`
- `vipw`
- `useradd`
- `userdel`
- `usermod`
- `chage`
- `passwd`
- `vigr`
- `groupadd`
- `groupdel`
- `groupmod`
- `lid`
- `groupmems`
- `groups`

# files
- /etc/sudoers.d/amy
- /etc/passwd
- /etc/shadow
- /etc/skel
- /etc/login.defs
- /etc/default/useradd
- /etc/profile
- /etc/bashrc
- ~/.profile
- ~/.bashrc
- /etc/group

# file configurations
- `ALL=/usr/bin/useradd, /usr/bin/passwd`
- `Defaults timestamp_timeout=240`
- `inda ALL=/usr/bin/useradd, /usr/bin/passwd, ! /usr/bin/passwd root`
- `export EDITOR=/usr/bin/vim`
- `CREATE_HOME yes`
- `PASS_MAX_DAYS, PASS_MIN_DAYS, and PASS_WARN_AGE`
- `ENV_PATH`

# man pages

------------------------------------------------------------------

### Chapter 7 – Permission Management

# theory
- ownership
- permissions
- read, write, execute
- SUID, GUID, sticky bit
- Default Permissions
- User-extended Attributes

# commands/variables
- `ls`
- `find`
- `chown`
- `newgrp`
- `groups`
- `exit`
- `chmod`
- `umask`
- `chattr`

# files

# file configurations

# man pages

------------------------------------------------------------------

### Chapter 8 - Configuring Networking

# theory
- Internet Protocol
- IPv4, IPv6
- classful Networking
- IPv4 subnet mask
- Binary notation
- Mac addresses
- Protocols and Ports
- Fixed / static IP addresses
- DHCP / dynamicall assigned IP address
- DNS domaoin name system
- FQDN fully qualified domain name

# commands/variables
- `ip addr, ip route, ip link`
- `ss`
- `systemctl status NetworkManager`
- `nmtui`
- `nmcli`
- `nmcli general permissions`
- `nmcli device status `
- `nmcli con add con-name dhcp type ethernet ifname ens33 ipv4.method auto`
- `nmcli con add con-name static ifname ens33 autoconnect no type ethernet ip4 10.0.0.10/24 gw4 10.0.0.1 ipv4.method manual`
- `nmcli connection show`
- `nmcli con mod static connection.autoconnect no`
- `nmcli con mod static ipv4.dns 10.0.0.10`
- `nmcli con mod static +ipv4.dns 8.8.8.8`
- `nmcli connection modify`
- `nmcli con mod static ipv4.addresses 10.0.0.100/24`
- `nmcli con mod static +ipv4.addresses 10.20.30.40/16`
- `nmcli connection up static`
- `hostnamectl set-hostname`
- `hostnamectl status`
- `nmcli con mod <connection-id> [+]ipv4.dns <ip-of-dns>`
- `nmcli con mod <con-name> ipv4.ignore-auto-dns yes`

# files
- /etc/hosts
- /etc/resolv.conf

# file configuraiton 

# man pages
- man 5 nm-settings
- man nmcli-examples
- man 5 hosts
- man 5 resolv.conf

# Exam Tips
- Do not specify the DNS servers directly in /etc/resolv.conf. They will be overwritten by NetworkManager when it is (re)started.

------------------------------------------------------------------

### Chapter 9 - Managing Software

# theory
- packages
- Red Hat Package Manager (RPM)
- repositories
- dependency
- BaseOS
- Application Stream
- Package Group 
- RPM
- module, stream, profile
- RPM filenames

# commands/variables
- `subscription-manager`
- `subscription-manager register`
- `subscription-manager list --available`
- `subscription-manager attach --auto`
- `subscription-manager list --consumed`
- `subscription-manager unregister`
- `createrepo`
- `dnf`
- `rpm`
- `repoquery` 
- `dnf-utils`

# files
- /etc/pki
- /etc/yum.repos.d.

# file configurations
- `[label]`
- `name= `
- `baseurl= `
- `gpgcheck= `
- `gpgkey= `

# man pages

# exam tips

------------------------------------------------------------------

### Chapter 10 - Managing Processese

# theory
- Shell jobs
- daemons
- Kernel threads
- foregrond process
- background process
- Process Identification Number
- cgroups: system, user, machine
- slices
- CPU weight
- signals
- SIGTERM, SIGKILL, SIGHUP
- zombies
- tuned daemon
- profiles

# Commands/Variables
- `fg`
- `jobs`
- `bg`
- `&`
- `Ctrl-C`
- `Ctrl-D`
- `Ctrl-Z`
- `ps`
- `nice`
- `renice`
- `kill`
- `pkill`
- `killall`
- `top`
- `uptime`
- `lscpu`
- `tuned-adm`

# files

# file configurations

# man pages
- man 7 signal

# Exam Tips
- Do not set process priority to –20; it risks blocking other processes from getting served.

------------------------------------------------------------------

### Chapter 11 - Working with Systemd

# theory
- Systemd
- unit
- mount
- socket
- target
- Managing dependencies

# commands/variables
- `systemctl`
- `systemctl -t service`
- `systemctl list-units -t service`
- `systemctl list-units -t service --all`
- `systemctl --failed -t service`
- `systemctl status -l your.service`
- `systemctl list-dependencies`
- `systemctl show`
- `systemctl show sshd`
- `systemctl edit sshd.service`

# files
- /usr/lib/systemd/system
- /etc/systemd/system
- /run/systemd/system

# file configurations
- Requires, Requisite, After, Before
- `export SYSTEMD_EDITOR="/bin/vim"`

# man pages

# Exam tips

------------------------------------------------------------------

### Chapter 12 - Schedualing Tasks

# thoery 
- systemd timers
- cron daemon
- systemd timer
- crond service

# commands/variables
- `systemctl cat logrotate.timer`
- `systemctl status crond`
- `crontab`
- `crontab -e`
- `crontab -e -u username`
- `at`
- `at 14:00`
- `at teatime`
- `at noon`
- `atq`
- `atrm`
- `atd`
- `batch`


# files
- /etc/crontab
- /etc/cron.d
- /etc/cron.hourly, cron.daily, cron.weekly, cron.monthly
- /etc/anacron

# file configuraitons

# man pages
- `man 5 systemd.timer`
- `man 7 systemd.time`
- `man 5 crontab`

# Exam timps
- Even if systemd timers are now the default solution for runningrecurring tasks, cron is still available. Make sure you master both for purposes of preparing for the RHCSA exam

------------------------------------------------------------------

### Chapter 13 - Configuring Logging

# theory
- systemd-journald
- Direct write
- rsysslogd
- logrotation
- facility, priority, destination

# commands/variables
- `tail -f`
- `logger`
- `logger -p kern.err hello`
- `journalctl`
- `journalctl -u sshd`

# files
- /var/log
- /var/log/messages
- /var/log/dmesg
- /var/log/secure
- /var/log/boot.log
- /var/log/audit/audit.log
- /var/log/maillog
- /var/log/httpd/
- /etc/systemd/journald.conf
- /etc/rsyslog.conf 
- /etc/logrotate.conf

# file configurations
- `Storage=auto`
- `Storage=volatile`
- `Storage=persistent`
- `Storage=none`

# Man pages
- `man 5 rsyslog.conf`
- `man logrotate`

# Exam Tips

------------------------------------------------------------------

### Chapter 14 - Managing Storage

# theory
- partitions
- MBR Master Boot Record
- BIOS Basic Input Output System
- GPT GUID Partition Table
- UEFI Unidfied Extensible Firmware Interface
- Storage Measurement Units
- MBR vs GPT partition limitations
- File Systems
- Swap Partitions
- Mounting File Systems
- UUID univerally unique identifier
- Creating systemd mount file 

# commands/variables
- `fdisk`
- `gdisk`
- `parted`
- `mkfs`
- `mkfs.xfs /dev/sdb1`
- `tune2fs -l /dev/sdd1`
- ` tune2fs -o`
- `tune2fs -o acl,user_xattr`
- `tune2fs -o ^acl,user_xattr`
- `tune2fs -O`
- `tune2fs -L`
- `e2label`
- `xfs_admin`
- `xfs_admin -L mylabel`
- `swap`
- `mkswap`
- `mkswap /dev/sdb6`
- `free -m`
- `swapon`
- `swapon /dev/sdb6`
- ` dd if=/dev/zero of=/swapfile bs=1M count=100`
- `mkswap /swapfile`
- `swapon /swapfile`
- `mount`
- `umount`
- `mount /dev/sdb5 /mnt`
- `blkid`
- `mount LABEL=mylabel /mnt`
- `findmnt --verify`
- `mount -a`
- `/run/systemd/generator/repo.mount`


# files
- /etc/fstab

# file configuration
- auto/ noauto, acl, user_xattr, ro, atime/noatime, noexec /exec

# Man pages
- `man 5 fs`

# Examp Tips

------------------------------------------------------------------

### Chapter 15 - Managing Adavanded Storage

# theory
- LVM logical volume manager
- Snapshot
- Physcial Volumes > Volume Group > Logical Volume
- Physical extent size
- Device Mapper
- logical extent

- Stratis
- Volume Managing File-System
- Thin Provisioning
- Snapshots
- Cache tier
- Programmtica API 
- Monitoring and Repair

# commands/variables
- `pvcreate`
- `set n lvm on`
- `pvcreate /dev/sdd1`
- `pvdisplay /dev/sdd1`
- `lsblk`
- `vgcreate vgdata /dev/sdd1`
- `vgcreate vgdata /dev/sdc`
- `pvs`
- `vgcreate -s`
- `vgdisplay`
- `lvcreate -n lvdata -l 100 vgdata`
- `mkfs`
- `ls -l /dev/mapper/vgdata-lvdata /dev/vgdata/lvdata`
- `vgextend`
- `vgreduce`
- `vgs`
- `lvextend`
- `lvresize`
- `lvresize -L +1G -r /dev/vgdata/lvdata`
- `lvresize -r -l 75%VG /dev/vgdata/lvdata` 
- `lvresize -r -l +75%VG /dev/vgdata/lvdata`
- `lvresize -r -l +75%FREE /dev/vgdata/lvdata`
- `lvresize -r -l 75%FREE /dev/vgdata/lvdata`
- `pvremove`
- `vgreduce`
- `stratis-cli`
- `stratisd`
- `systemctl enable --now stratisd`
- `stratis pool create`
- `stratis pool create mypool /dev/sde`
- `stratis pool add-data pool-name blockdevname`
- `stratis pool add-data mypool /dev/sde`
- `stratis fs create pool-name fsname`
- `stratis fs list`
- `x-systemd.requires=stratisd.service`
- `stratis pool add-data`
- `stratis blockdev`
- `stratis pool`
- `stratis filesystem`

# files

# file configuration

# Man pages

# Examp Tips

------------------------------------------------------------------

### Chapter 16 - Basic Kernel Management

# theory
- kernel
- I/O instructions
- Threads
- Hardware Initialization
- Driver
- Tainted Kernel
- /proc
- modules
- systemd-udevd process

# commands/variables
- `dmesg`
- `journalctl -k`
- `uname`
- `hostnamectl status`
- `udevadm`
- `lsmod`
- `modinfo`
- `modprobe`
- `modprobe -r`
- `lspci`
- `lspci -k`
- `dnf install kernel`
- `dnf upgrade kernel`

# files
- /proc

# file configuration

# Man pages

# Examp Tips

------------------------------------------------------------------

### Chapter 17 - Managing and Understanding the Boot Procedure

# theory
- Systemd
- emergency.target
- rescue.target
- multi-user.target
- graphical.target
- dependencie
- target unit file
- target isolation
- run level 0-6
- GRUB2 boot loader
- kernel
- initramfs

# commands/variables
- `systemctl enable`
- `systemctl disable`
- `systemctl isolote`
- `systemctl -t target --all`
- `systemctl get-default`
- `dnf group list`
- `dnf group install "server with gui"`
- `grub2-mkconfig`
- `rhgb`
- `quite`
- `grub2-mkconfig -o /boot/grub2/grub.cfg`
- `grub2-mkconfig -o /boot/efi/EFI/redhat/grub.cfg`

# files
- /etc/default/grub 
- /etc/grub.d.
- /boot/grub2/grub.cfg
- /boot/efi/EFI/redhat/grub.cfg 

# file configuration
- `GRUB_CMDLINE_LINUX`
- `GRUB_TIMEOUT`

# Man pages
- `man 7 booparam`

# Examp Tips

------------------------------------------------------------------

### Chapter 18 - Essential Troubleshooting Skills

# theory
- Boot procedure:
    1. Performating POST
    2. Selecting the bootable device
    3. Loading the boot order
    4. Loading the Kernel
    5. Starting /sbin/init
    6. Processing initrd.target
    7. Switching to the root file system
    8. Running the default target

- GRUB 2 menu

- Using Rescue Disk
    1. Install Red Hat Enterprise Linux 9 in Basic Graphics Mode
    7. Rescue a Red Hat Enterprise Linux System:
    3. Run a Memory Test
    4. Boot from Local Drive

- Resetting Root Password
    1. On system boot, press e when the GRUB 2 boot menu is shown
    2. Enter init=/bin/bash as a boot argument to the line that loads the kernel and press Ctrl-X to boot with this option
    3. Once a root shell is opened, type mount -o remount,rw / to get read/write access to the root filesystem.
    4. Now you can enter passwd and set the new password for the user root
    5. touch /.autorelabel to create the autorelabel file in the root directory
    6. exec /usr/lib/systemd/systemd to replace /bin/bash (which is the current PID 1) with Systemd.
    7. Verify that you can log in as the root user after rebooting.

# commands/variables
- `rd.break`
- `init=/bin/sh or init=/bin/bash`
- `systemd.unit=emergency.target`
- `systemd.unit=rescue.target`
- `chroot`
- `grub2-install`
- `grub2-install /dev/sda`
- `dracut`
- `grub2-install`
- `chroot /mnt/sysimage`
- `dracut --force`
- `fsck`
- `journalctl -xb`
- `mount -o remount,rw /`

# files
- /usr/lib/dracut/dracut.conf.d/*.conf c
- /etc/dracut.conf.d 

# file configuration

# Man pages

# Examp Tips

------------------------------------------------------------------

### Chapter 19 - An Introduction to Automation with Bash Shell Scripting

# theory
- shebang
- parent shell
- subshell
- $PATH
- variable
- conditional loops
- case statement


# commands/variables
- `bash`
- `TODAY=$(date +%d-%m-%y)`
- `if … then … else`
- `for`
- `while`
- `until`
- `case`
- ` || &&`
- `bash -x`

# files

# file configuration

# Man pages
- `man bash`

# Examp Tips

------------------------------------------------------------------

### Chapter 20  - Configuring SSH

# theory
- Dictionary attacks
- Disable root login 
- Disable password login
- Configure non-default port for ssh login
- Allow specific user to login ssh
- AUTHPRIV syslog facility
- Public/Private key passphrase
- SSH host keys and known_hosts / MITM protection
- StrictHostKeyChecking concept
- SELinux and ssh_port_t when changing SSH port
- Difference between TCPKeepAlive and ClientAlive* keepalives

# commands/variables
- `ssh-keygen`
- `ssh-copy-id`
- `ssh-agent`
- `ssh-add`
- `semanage port`
- `semanage port -l`
- `semanage port -a -t ssh_port_t -p tcp 2022`
- `semanage port -m`
- `firewall-cmd --add-service=ssh`
- `firewall-cmd --add-port=2022/tcp`

# files
- /etc/ssh/sshd_config 
- ~/.ssh/authorized-keys
- ~/.ssh/known_hosts

# file configurationo
- `port`
- `PasswordAuthenticaion`
- `PublicAuthentication`
- `AuthorizedKeysFile`
- `AllowUsers`
- `Allowgroups`
- `PermitRootLogin`
- `LoginGraceTime`
- `MaxAuthTries`
- `UseDNS`
- `MaxSessions`
- `TCPKeepAlive`
- `ClientAliveInterval`
- `ClientAliveCountMax`
- `ServerAliveInterval` 
- `ServerAliveCountMax`

# Man pages
- ssh(1)
- sshd(8)
- ssh_config(5)
- sshd_config(5)
- semanage-port(8)

# Examp Tips
- Practice: change SSH port + update SELinux + update firewalld + test login.
- Practice: configure key-based auth, disable password auth, verify login still works.
- Avoid locking yourself out: keep a second root/console session open while changing SSH.

------------------------------------------------------------------

### Chapter 21 - Managing Apache HTTP Services

# theory
- chroot environment

- Apache Virtual Hosts
    1. The client opens a browser and enters the website URL.
    2. DNS resolves the URL to the Apache server’s IP.
    3. Apache receives the request and inspects the HTTP headers to see which virtual host it targets.
    4. Apache loads that virtual host’s configuration to determine its document root.
    5. Apache serves the requested file from that document root.

- Virtual hosting recemndations
    1. Virtual-hosted Apache servers should handle every site through a virtual host.
    2. Create a _default_:80 virtual host as a catch-all so unmatched requests do not randomly hit the first configured vhost.
    3. Name-based virtual hosts share one IP but use different hostnames and are the most common setup.
    4. IP-based virtual hosts each use a unique IP and are typically used when a site must have its own address or for some TLS setups.

# commands/variables
- `dnf group install "Basic Web Server"`
- `dnf install curl`
- `systemctl status httpd mod_ssl`
- `systemctl enable --now httpd`
- `systemctl restart httpd`, 
- `systemctl is-enabled httpd`
- `httpd -t`
- `apachectl configtest`

# files
- /etc/httpd 
- /etc/httpd/conf/httpd.conf
- /etc/httpd/conf.d 
- /etc/httpd/conf.modules.d
- /etc/httpd/conf.d/ssl.conf

# file configuration
- `DocumentRoot`
- `ServerRoot`
- `Listen`
- `ServerName`, `ServerAlias`
- `<Directory>`, `AllowOverride`
- `ErrorLog`, `CustomLog`
- `LoadModule` 
- `SSLEngine on`
- `SSLCertificateFile`
- `SSLCertificateKeyFile`

# Man pages
- httpd(8)
- apachectl(8)
- httpd.conf(5)

# Examp Tips
- Always run httpd -t before restarting.​
- Know default doc root: /var/www/html.​
- Know default doc root: /var/www/html.​

------------------------------------------------------------------

# Chapter 22 - Managing SELinux

### theory
- MAC
- DAC
- policy
- Source Domain 
- Target Domain
- Context
- Rule
- Label
- Selinux modes: enforcing, permissive, disabled
- context labels
    1. User
    2. Role
    3. Type
- audit log
- source context
- target context
- subject (process) vs object(file/dir/port) type-enforcemtn based

### commands/variables
- `getenforce`
- `setenforce`
- `grub2-mkconfig -o /boot/grub2/grub.cfg`
- `sepolicy generate`
- `ls -Z`
- `chcon`
- `dnf whatprovides */semanage`
- `semanage fcontext -a -t httpd_sys_content_t "/mydir(/.*)?"`
- `man -k _selinux`
- `restorecon`
     `restorecon -Rv /`
     `restorecon -R -v /mydir`
- `semanage`
     `semanage port -a -t http_port_t -p tcp 8008`
     `semanage fcontext -l`
     `semanage fcontext -c`
     `semanage boolean -l`
     `semanage porl -l `
- `getsebool -a`
- `setsebool`
     `setsebool ftpd_anon_write on`
     `setsebool -P`
- `sealert`
- `sestatus`
- `ps -eZ`
- `id -Z`

### files
- /etc/default/grub
    `selinux=0`
    `enforcing=0`
- /etc/sysconfig/selinux
    `SELINUX=enforcing|permissive|disabled`
    `SELINUXTYPE=targeted`
- /var/log/audit/audit.log
- /etc/selinux
- /sys/fs/selinux

### Man pages
- selinux (8)
- semanage (8)
- sestatus (8)
- selinux_config(5)

### Exam Tips
- Note that SELinux is MAC on top of DAC and that DAC is still checked first
- Checking context with ls -Z / ps -Z.
- Using restorecon -Rv PATH before chcon or custom fcontext
- For services on non-default ports: change with semanage port -a/-m and verify with semanage port -l
- For weird service failures on exam, briefly try setenforce 0 to confirm SELinux is the cause, then revert to enforcing after fixing
- If semanage or sealert missing, install with dnf whatprovides */semanage or the package suggested by the exam system.
- Remember sestatus shows both current mode and config file setting.

------------------------------------------------------------------

# Chapter 23 - Configuring a Firewall

### theory
- Firewalld is frontend using nftables(rules are applied per zone to interfaces and sources)
- One‑liner for “rich rules” (more granular matching than simple service/port adds)
- firewall
- Netfilter
- Firewalld
- nftables
- zone
    1. block
    2. dmz
    3. drop
    4. external
    5. home
    6. internal
    7. public
    8. trusted
    9. work

### commands/variables
- `nft`
- `firewall-cmd`
    `firewall-cmd --runtime-to-permanent`
    `firewall-cmd --get-zones`
    `firewall-cmd --get-default-zone`
    `firewall-cmd --set-default-zone=<ZONE>`
    `firewall-cmd --get-services`
    `firewall-cmd --list-services`
    `firewall-cmd --add-service=<service-name> [--zone=<ZONE>]`
    `firewall-cmd --remove-service=<service-name>`
    `firewall-cmd --list-all-zones`
    `firewall-cmd --add-port=<port/protocol> [--zone=<ZONE>]`
    `firewall-cmd --remove-port=<port/protocol> [--zone=<ZONE>]`
    `firewall-cmd --add-interface=<INTERFACE> [--zone=<ZONE>]`
    `firewall-cmd --remove-interface=<INTERFACE> [--zone=<ZONE>]`
    `firewall-cmd --add-source=<ipaddress/netmask> [--zone=<ZONE>]`
    `firewall-cmd --remove-source=<ipaddress/netmask> [--zone=<ZONE>]`
    `firewall-cmd --permanent`
    `firewall-cmd --runtime-to-permanent`
    `firewall-cmd --reload`
    `firewall-cmd --zone=<ZONE> --list-all`
    `firewall-cmd --state`
    `firewall-cmd --add-rich-rule='rule family="ipv4" source address="192.0.2.10" service name="ssh" accept'`
- `firewall-config`

### files / file configurations
- /etc/firewalld/services
- /etc/firewalld/zones/
- /usr/lib/firewalld/services

### Man pages
- firewalld(1)
- firewall-cmd(1)
- firewall.zone(5)

### Exam Tips
- Assign interface to the correct zone
- Open a service or port in a specific zone and make it persistent
- Prefer services over ports when available
- If something works from localhost but not remotely, check:
    Service listening on the correct interface.
    firewalld zone and rules for that interface

------------------------------------------------------------------

# Chapter 24 - Accessing Network Storage

### theory
- NFS
- automount
- autofs

### commands/variables
- `mount`
- `showmount -e nfsserver`
- `autofs`
- `* -rw server2:/users/&`

### files/ file configurations
- /etc/exports
- /etc/fstab
    `server1:/share /nfs/mount/point nfs sync 0 0`
- /etc/auto.master.
    `/nfsdata /etc/auto.nfsdata`
- nfsdata/files
    `files -rw server2:/nfsdata`

### Man pages

### Exam Tips

------------------------------------------------------------------

# Chapter 25 - Configuring Time Services

### theory
- real-time clock RTC
- hardware time
- Coordinated Universal Time UTC
- System time
- time synchronization
- network time protocol NTP
- stratum
- chronyd process
- chrony service

### commands/variables
- `timedatectl`
    `timedatectl set-ntp 1`
    `timedatectl status`
    `timedatectl set-time "YYYY-MM-DD HH:MM:SS"`
    `timedatectl set-timezone Region/City`
    `timedatectl list-timezone`
    `timedatectl set-local-rtc [0|1]`
    `timedatectl set-ntp [0|1]`
- `date`
    `date -u`
    `date "+%Y-%m-%d %H:%M:%S"`
- `hwclock`
    `hwclock --show`
    `hwclock --hctosys`
    `hwclock --systohc`
    `hwclock --systohc --utc`
    `hwclock --systohc --localtime` 
- `chronyc`
    `chronyc tracking`
    `chronyc sources -v`
    `chronyc makestep`
- `systemctl`
    `systemctl status chronyd`
    `systemctl enable --now chronyd`
    `systemctl restart chronyd`
- `ln -sf /usr/share/zoneinfo/America/Los_Angeles /etc/localtime`
- `tzselect`

### files / file configurations
- /etc/chrony.conf 
    `server`
    `pool`
- /usr/share/zoneinfo
    `America/New_York`
- /etc/localtime
- /etc/adjtime

### Man pages
- man timedatectl
- man date
- man hwclock
- man chrony.conf
- man chronyc

### Exam Tips
- On the exam, always check timedatectl status first to see current time, time zone, and whether NTP is enabled
- If a task says “configure time service clients,” that means:
    1. Ensure chronyd is installed (dnf install chrony if needed).
    2. Edit /etc/chrony.conf to point to the correct NTP servers (if specified).
    3. Enable and start chronyd with systemctl enable --now chronyd or use timedatectl set-ntp 1
- Use timedatectl set-timezone instead of manually editing /etc/localtime unless the task specifically asks for the symlink method
- If the system is not syncing time, check:
    1. chronyd service status (systemctl status chronyd)
    2. Network connectivity to NTP servers (firewall, routing)
    3. Correct server entries in /etc/chrony.conf
- Remember that timedatectl set-time and date only affect system time; use hwclock --systohc to also update the hardware clock if needed

------------------------------------------------------------------

# Chapter 26 - Managing Containers

### theory
- overlay filesystem
- container
- container filej
- container engine
- container registry
- chroot jails
- namespace
    1. Mount
    2. Process
    3. Network
    4. User
    5. Interprocess communication
- Cgroups
- docker
- podman
- rootless containers
- CRI-o container runtime
- Container Orchestration
- Kubernetes
- OpenShift
- containter images
- open container initiative OCI
- image housekeeping
- managing containers
- orchrestration
- bind mounted directories
- linger

### commands/variables
- `podman`
    `podman run nginx`
    `podman run docker.io/library/nginx`
    `podman run docker.io/librarynginx`
    `podman run -d nginx`
    `podman run -it nginx`
    `podman run -it nginx /bin/sh`
    `podman run -it nginx /bin/sh`
    `podman ps`
    `podman ps -a`
    `podman info`
    `podman search`
    `podman login`
    `podman login registry.access.redhat.com`
    `podman inspect`
    `podman images`
    `podman pull`
    `podman run`
    `podman rmi`
    `podman build`
    `podman build -t imagename:tag`
    `podman build -t mymap:1.0`
    `podman images`
    `podman ps`
    `podman stop`
    `podman kill`
    `podman restart`
    `podman rm`
    `podman run -rm`
    `podman exec`
    `podman exec mycontainer uname -r`
    `podman exec -it mycontainer /bin/bash`
    `sudo podman run ...`
    `sudo podman ps`
    `podman run --name nginxport -d -p 8080:80 nginx`
    `sudo firewall-cmd --add-port 8080/tcp --permanent; sudo firewall-cmd --reload`
    `podman logs`
    `podman inspect`
    `podman run -d -e MYSQL_ROOT_PASSWORD=password -e MYSQL_USER=anna -e MYSQL_PASSWORD=password -e MYSQL_DATABASE=mydb -p 3306:3306 mariadb`
    `podman run -d --name mydb -v /home/$(id -un)/dbfiles:/var/lib/mysql:Z -e MYSQL_USER=user -e MYSQL_PASSWORD=password -e MYSQL_DATABASE=mydatabaseregistry.redhat.io/rhel9/mariadb-105`
    `podman unshare`
    `podman unshare cat /proc/self/uid_map`
    `podman generate`  
    `podman generate systemd --name mycontainer --files`
    `podman generate systemd`
- `buildah`
- `skopeo`
    `skopeo inspect`
- `semanage`
    `semanage fcontext -a -t container_file_t"/hostdir(/.*)?"; restorecon`
    `-v host_dir:container_dir`
    `host_dir:container_dir:Z`
- `systemctl`
    `systemctl enable --now myservice.service`
    `systemctl --user`
    `systemctl --user startmyservice.service`
    `systemctl --user enable container-mycontainer.service`
- `loginctl`
    `loginctl enable-linger myuser`

### files / file configurations
- /etc/containers/registries.conf 
- ~/containers/storage/
- Containerfile
- ~/.config/containers/registries.conf

### Man pages
- `man podman run`
- `man podman-generate-systemd`
- `man skopeo-inspect`
- `man buildah`

### Exam Tips
- Install tools first: dnf install podman docker-compose-plugin or dnf module install container-tools
- Common tasks: Pull image → run with -d -p host:container -v host:container:Z → expose port via firewall-cmd → make systemd service with podman generate systemd --user + loginctl enable-linger $(id -un) + systemctl --user enable --now
- Rootless by default on RHEL9; use podman unshare sysctl user.max_user_namespaces=15000 if namespace errors occur.
- Verify: podman ps, curl localhost:8080, check persistent data after restart
- Troubleshoot: podman inspect <container> for IP/ports; podman image prune for cleanup
