  ------------------------------------------------------------------

## Chapter 2 – Using Essential Tools

# theory 
- Shell
- Bash
- Alias
- Internal command
- External command
- Redirection
- Device files
- Pipe
- History
- Bash completion
- Environment
- Variables
- Login shell
- Subshell

# command / variable
- `$PATH`
- `echo`
- `which`
- `type`
- `history`
- `--help`
- `man`
- `man -k`
- `mandb`
- `apropos`
`
# files
- `/etc/profile`
- `/etc/bashrc`
- `~/.bash_profile`
- `~/.bashrc`
- `/etc/motd`
- `/etc/issue`

# file configurations
- ` export MY_VAR="some_value`
- ` export PATH=$PATH:/my/custom/directory`


------------------------------------------------------------------

## Chapter 3 – Essential File Management Tools

# theory
- Filesystem Hierarchy Standard (FHS)
- Root directory
- Device file
- Glob / wildcards
- Absolute pathname
- Relative pathname
- Inodes
- Hard links
- Soft / symbolic links
- Compression

# command/variable
- `mount`
- `df`
- `findmnt`
- `touch`
- `ls`
- `cp`
- `mv`
- `mkdir`
- `rmdir`
- `rm`
- `ln`
- `tar`

# files

# file configurations

------------------------------------------------------------------

## Chapter 4 – Working with Text Files

- `less`
- `cat`
- `head`
- `tail`
- `cut`
- `sort`
- `wc`
- `grep`
- `sed`
- `awk`

------------------------------------------------------------------
3 thenbuer recurisv the fne bnubme nubmer fgh 
console 
temina,. 

## Chapter 5 – Connecting to Red Hat RHEL



- Console
- Terminal
- `sudo`
- TTY / `term`
- Subshell
- `su`
- Working with multiple terminals
- `chvt`
- `w`
- `who`
- `systemctl reboot`
- `systemctl halt`
- `systemctl poweroff`
- `ssh`
- Forward X11
- `scp`
- `sftp`
- `rsync`
- Key-based login
- Public key
- Private key
- `ssh-keygen`
- `ssh-copy-id`

# files
~/ssh
~/.ssh/authorized_keys
~/.ssh/config
/etc/ssh/ssh_config
/etc/ssh/sshd_config
------------------------------------------------------------------

## Chapter 6 – User and Group Management

### User Types and Privilege
- Privileged users
- Unprivileged users
- `root`
- `id`
- `sudo`
- `su`
- `pkexec`
- `visudo`

### User Databases and Files
- `/etc/passwd`
- `/etc/shadow`
- `/etc/group`
- `vipw`

### User Management Commands
- `useradd`
- `usermod`
- `userdel`
- `passwd`
- `/etc/default/useradd`
- `/etc/login.defs`
- `chage`
- `groups`

### Groups
- Primary group
- Secondary group
- `vigr`
- `groupadd`
- `groupmod`
- `groupdel`
- `lid`
- `gpasswd`

---

## Chapter 7 – Permission Management

### Ownership and Permissions
- Ownership
- `find`
- `chown`
- `newgrp`
- `groups`
- `gpasswd`
- `vigr`
- Read, write, execute
- `chmod`

### Special Permissions and Attributes
- SUID permissions
- SGID permissions
- Sticky bit
- `umask`
- Extended attributes: `A a c D d I i s u`

---

## Chapter 8 – Configuring Networking

### Addressing and Notation
- IPv4 address
- IPv6 address
- Class A, Class B, Class C networks
- Subnet mask
- Binary notation
- MAC address

### Networking Concepts and Tools
- Protocols and ports
- Fixed IP addressing
- DHCP
- `ip address`
- `ip route`
- `ip link`
