## Some basic command
show current date and time
```
date
```
show calender
```
cal         ---------> current month calender with current date
cal 2021    ---------> To show caleder of 2021 year
cal 09 2021 ---------> Show calender of September 2021
```
how to see hostname of a machine
```
hostname 
   or
uname -n
```
how to check os name, version and other details
```
cat /etc/os-release
```
how to check cpu crchitecture, kernal name, version, release
```
uname -s    // kernal name
uname -v    // kernal version
uname -r    // kernal release version

uname -p    // cpu architecture
```
how to see machine information. like hostname, os name and version, kernal name and version, cpu architecture etc..
```
hostnamectl
```
how to check ip address, network namespcae etc..
```
ifconfig
   or
ip a
```
how to install, remove and update package on CENTOS/RHEL (package means software. In linux it is called package)
```
yum install package-name -y
yum remove package-name -y
yum update package-name -y

// Example- install git package
yum install git -y
```
* **-y** - it automatically chooses **yes** for future questions, ```i.e. are you sure you want to install squid? [Y/n]?```

how to install, remove and update package on Ubuntu 
```
apt-get install package-name -y
apt-get remove package-name -y
apt-get update package-name -y

// Example- install git package
apt-get install git -y
```

how to check a package is install or not
```
which package-name

// Example- check git is install or not
which git
```
how to display username of current user
```
whoami
```

## Uses of echo command
echo command is used to display lines of text that are passed as an argument
```
[centos@linux-lab ~]$ echo "Hello World"
Hello World
```
write something to a file using echo
```
echo "write something" > filename
```
* **>** gratter than sign used to write something in file

append something into an existing file using echo
```
echo "write something" >> filename
```
* **>>** double gratter than sign used to append something in exesting file

clear content from a file using echo
```
echo > filename
```

## Uses of grep command
grep command is used to find anything from a file content or find anything from a command output

search anything from a file with grep
```
grep search-text(which you want to search) filename
```
Example - find **root** from /etc/passwd file
```
[centos@linux-lab ~]$ grep root /etc/passwd
root:x:0:0:root:/root:/bin/bash
operator:x:11:0:operator:/root:/sbin/nologin
```
search anything from output of any command with grep
```
write your command | grep search-text(which you want to search)
```

## Uses of less command
**less** is most useful for viewing the content of large files or the results of commands that produce many lines of output

View the content of file with less
```
less filename
```
view the output of any command that produce many lines with grep
```
write your command | less
```
scroll up page afetr executing less command
```
shift - page up OR Up Arrow
```
scroll down page afetr executing less command
```
shift - page down OR Down Arrow
```
exit from page after executing less command
```
press q
```
## Uses of haid and tail command
**haid** - used to print **N** numbers of line from **begining** of file. By default it print first 10 lines if we do not use **-n**

print first 10 line of a file
```
head filename        // it print first 10 lines
     or
head -n 15 filename  // it print first 15 lines
```
* **-n** - specify how many nuber of lines you want to see

print first N line of a command output
```
write your command | head -n specify-number-of lines
```

**tail** - used to print **N** numbers of line from **end** of file. By default it print last 10 lines if we do not use **-n**

print last 10 line of a file
```
tail filename        // it print last 10 lines
     
tail -n 15 filename  // it print last 15 lines

tail -f filename     // to follow a file containt at real time
```
* **-n** - specify how many nuber of lines you want to see

print last N line of a command output
```
write your command | tail -n specify-number-of lines
```

## Working with files and directories
write to a file using cat
```
cat > filename [press enter]
..... write something ......
enter ctrl+D to exit from file
```
* **>** gratter than sign used to write something in file

See file content using cat
```
cat filename 
```
See file content from bottom to top
```
tac filename
```
append something in existing file
```
cat >> filename [press enter]
..... write something ......
enter ctrl+D to exit from file
```
* **>>** double gratter than sign used to append something in exesting file
  concatenate multiple file content into a single file
```
cat file1 file2 > file3
```
* here **file1** and **file2** content are concatenate in **file3**

how to create a empty files
```
// create single file
touch filename

// create multiple files
touch file1 file2 file3
```
displays detailed information about given file. like file name, type, size etc..
```
stat filename
```
make a directory in linux
```
// create single directory
 mkdir dirname
 
// create multiple directory
mkdir dir1 dir2 dir3
```
make sub-directory with parent
```
 mkdir -p maindir/subdir
```
* **-p** it used to create parent directory if it not exist

how to change directory (means go from one directory to another directory)
```
 cd dirname
```
how to go parent directory from sub-directory
```
cd ..
```
* **..** it used to go parent directory from sub-directory

print working directory (means In which directory we are now). it showing the path of working directory
```
pwd
```
go to user directory from any open directory
```
 cd
```
how to create a hidden file or folder in linux
```
.filename
```
* add .(dot) before any file or folder name then it will be hidden

show list of non-hidden files and folder
```
 ls
 
 // show with details
 ls -l or ll
```
show list of all files and folder (hidden or non-hidden)
```
 ls -a
 
 // show with details
 ls -la or ll -a
```
copy file or directory
```
 cp source-path destination-path
 
 // Example - copy file1.txt in movie folder
 cp path/file1.txt movie
```
copy directories recursively (means copy directorie with it sub-directories)
```
cp -r source-path destination-path
```
* **-r** to used for recursive

move file or directory
```
 mv source-path destination-path
 
 // Example - move file1.txt in movie folder
 mv path/file1.txt movie
```
rename a file or directory.
```
mv oldname newname

// Example - rename file1.txt to myfile.txt
 mv file1.txt myfile.txt
```
remove directory. it can remove only empty directory
```
 rmdir dirname
 
 // remove multiple directory
 rmdir dir1 dir2 dir3
```
rm command is used in linux to remove files, directorys
```
 rm -rf directory-name or filename
 
 // remove multiple directory and files
 rm -rf dir1 dir2 file1 file2
```
* **r** - for delete recursively
* **f** - for delete forcefully

## Working with vi text editor

open a file command
```
 vi filename
```
insert in file vid editror
```
 press i
```
close insert option
```
 press Esc
```
exit from editor
```
 press :x then Enter
```
exit with save
```
 press :wq then enter
```
force exit
```
 press :q! then enter
```
Position the cursor at the beginning of the text you want to cut/copy.
```
 Press v to begin character-based visual selection, or V to select whole lines
```
Move the cursor to the end of the text to be cut/copied
```
 Press d (delete) to cut, or y (yank) to copy.
```
Move the cursor to the desired paste location.
```
 Press p to paste after the cursor, or P to paste before.
```

## Working on user and group in linux

how to create user
```
useradd username
```
how to add password to an user
```
passwd username
```
how to delete a user
```
userdel -r username
```
* **-r** - remove home directory and mail spool

show list of user
```
getent passwd
      or
cat /etc/passwd

|------------------------structure-------------------------------|
| ec2-user:x:1000:1000:Cloud User:/home/ec2-user:/bin/bash       |
| username:password:UID:GID:comment:home directory:default shell |
|----------------------------------------------------------------|
```
how to create group
```
groupadd groupname
```
how to delete a group
```
groupdel groupname
```
show list of group
```
getent group
      or
cat /etc/group

|---------------structure---------------------|
|  adm:x:4:ec2-user                           |
|  group name:password:GID:list of users      |
|---------------------------------------------|
```
add a single user to a group
```
gpasswd -a username groupname
```
* **-a** - for add user

add a multiple user to a group
```
gpasswd -M username1,username2,username3 groupname
```
* **-M** - for add multiple user

delete a user from a group
```
gpasswd -d username groupname 
```

## Permission / Access Modes

after execute ```ls -l``` command we can see details (like group, owner, permissions, type etc...) of file or directory
```
ls -l

-rw-r--r-- 12 centos centos 1636 Apr  8 20:51 filename.txt
|[-][-][-]    [----] [----] [--]              
| |  |  |        |      |     |
| |  |  |        |      |     +----------------------------> 7. File size in Byte
| |  |  |        |      +------------> 6. Group
| |  |  |        +-------------------> 5. Owner
| |  |  |
| |  |  +----------------------------> 4. Others Permissions. Three tiplle indecats read, write and execute.
| |  +-------------------------------> 3. Group Permissions. Three tiplle indecats read, write and execute.
| +----------------------------------> 2. Owner Permissions. Three tiplle indecats read, write and execute.
|
+------------------------------------> 1. (-) Means Regular file, (d) Means Directory, (l) Means link
```

* ```rw-```   read, write, not executeble
* ```-wx```   not readble, write and execute
* ```r-x```   read, not writble, execute
* ```rwx```   read, write and execute

change access permissions or mode of file or directory
```
chmod mode filename or directory-name

chmod 400 filename
      |||__________ [third digit]  - for others
      ||___________ [second digit] - for group
      |____________ [first digit]  - for owner
```

<table>
<tr>
<td colspan=2>Access Mode <td>File <td>Directory
<tr>
<td>r <td>4 <td>To display the content <td>To list the content
<tr>
<td>w <td>2 <td>To modify <td>To create and remove
<tr>
<td>x <td>1 <td>To execute a file <td>To enter into directory
</table>

* **0** = No Permission.
* 4 (r) + 2 (w) + 1 (x) = **7** = Read & Write & Execute
* 0 (r) + 2 (w) + 1 (x) = **3** = Write & Execute
* 4 (r) + 0 (w) + 1 (x) = **5** = Read & Execute
* 4 (r) + 2 (w) + 0 (x) = **6** = Read & Write

For an example - Change mode of ```sample.txt``` file
```
[centos@linux-lab ~]$ ls -l
-rw-rw-r-- 1 centos centos 0 Aug 10 08:42 sample.txt
 ---------
   
 // now sample.txt have mode (rw- rw- r--). I want to change mode of it to (rwx rwx rwx)

[centos@linux-lab ~]$ sudo chmod 777 sample.txt
[centos@linux-lab ~]$ ls -l
total 0
-rwxrwxrwx 1 centos centos 0 Aug 10 08:42 sample.txt
 ---------
```

change only owner of file or directory
```
chown username filename or directory-name
```
change only group of file or directory
```
chgrp groupname filename or directory-name
```
change both the owner and group of file
```
chown username:groupname filename or directory-name
```

## Soft link and Hard Link

1) **soft link** - is an actual link to the original file. It is similar to a Windows shortcut. If we delete original file, soft link has no value,
   because it points to a non-existing file. **Basically it used to create shortcut of file**

   * create soft link
   ```
    ln -s filename softlink-nae
   ```
   Example- We want to create soft link of sample.txt file
   ```
   [centos@linux-lab ~]$ ln -s sample.txt softsample
   [centos@linux-lab ~]$ ls -l
   lrwxrwxrwx 1 centos centos 10 Aug 10 14:42 softsample -> sample.txt   // this is the soft link of sample.txt file
   -rwxrwxrwx 1 centos centos  0 Aug 10 08:42 sample.txt
   ```

2) **hard link** - is a mirror copy of the original file. Even if we delete the original file, the hard link will still has the data of the original file
   because it is mirror copy of original file. **Basically it used for backup**

   * create hard link
   ```
    ln filename hardlink-name
   ```
   Example- We want to create hard link of sample.txt file
   ```
   [centos@linux-lab ~]$ ln sample.txt hardsample
   [centos@linux-lab ~]$ ls -l
   -rw-rw-r-- 2 centos centos 0 Aug 10 14:56 hardsample     // this is the hard link of sample.txt file
   -rw-rw-r-- 2 centos centos 0 Aug 10 14:56 sample.txt
   ```

## tar, gzip, wget

#### **tar** - is an archiver used to combine the multiple file into one

how to archive files or directory with tar
```
tar -cvf tarfilename.tar filename or directory-name
```
* **-cvf**  c for create, v for verbose (showing list files processed), f for force

Example -
```
[centos@linux-lab ~]$ tar -cvf animal.tar animal
[centos@linux-lab ~]$ ls -l
drwxrwxr-x 2 centos centos  4096 Aug 10 18:00 animal
-rw-rw-r-- 1 centos centos 10240 Aug 11 05:01 animal.tar // archive file of animal directory
```

how to extract archive file with tar
```
tar -xvf tarfilename.tar
```
* **-xvf**  x for extract, v for verbose (showing list files processed), f for force

Example -
```
[centos@linux-lab ~]$ ls -l
-rw-rw-r-- 1 centos centos 10240 Aug 11 05:14 animal.tar
[centos@linux-lab ~]$ tar -xvf animal.tar
[centos@linux-lab ~]$ ls -l
drwxrwxr-x 2 centos centos  4096 Aug 10 18:00 animal     // after extract we got animal directory
-rw-rw-r-- 1 centos centos 10240 Aug 11 05:14 animal.tar
```

#### **gzip** - is a compression tool used to reduce file size.

how to compress (zip) a file
```
gzip filename
```
Example - compress animal.tar file
```
[centos@linux-lab ~]$ ls -l
-rw-rw-r-- 1 centos centos 10240 Aug 11 05:14 animal.tar
[centos@linux-lab ~]$ gzip animal.tar
[centos@linux-lab ~]$ ls -l
-rw-rw-r-- 1 centos centos  186 Aug 11 05:14 animal.tar.gz // this is the compress file
```
* **.gz** is the extension of compress file

how to decompress (unzip) a file
```
gunzip compress-filename
```
Example - decompress animal.tar.gz file
```
[centos@linux-lab ~]$ ls -l
-rw-rw-r-- 1 centos centos  186 Aug 11 05:14 animal.tar.gz
[centos@linux-lab ~]$ gunzip animal.tar.gz
[centos@linux-lab ~]$ ls -l
-rw-rw-r-- 1 centos centos 10240 Aug 11 05:14 animal.tar
```

#### **wget** - is a non-interactive network downloader.

how to download a file from internet using wget
```
wget <url>
```
Example - we want to download jenkins.war file
```
[centos@linux-lab ~]$ wget https://get.jenkins.io/war-stable/2.289.3/jenkins.war
```

## Create linux service

create unit file name.service in /lib/systemd/system location
```
[Unit]
Description=Example systemd service.

**this is description of service which show on [systemctl status]

[Service]
ExecStart=/bin/bash /usr/bin/test_service.sh 
 
**ExecStart directive, which specifies the command that will be run to start the service.

[Install]
WantedBy=multi-user.target

**WantedBy= directive is the most common way to specify how a unit should be enabled
**multi-user.target means that the systemd-service will start when the system reach runlevel 2.In linux have 7 runlevel. 
**A runlevel is one of the modes that a Unix-based operating system will run in. 
Each runlevel has a certain number of services stopped or started, giving the user control over the behavior of the machine
```
start and enable service
```
systemctl status service_name  **check status of service is running or not
          start                **start a service
          restart              **restart a service
          stop                 **stop a service
          enable               **start service on boot
```
show list of service
```
systemctl list-unit-files **use --state=enabled show list of enabled service
```

## Linux process and ports

How to view all process
```
ps -aux

// find any process
ps -aux | grep "process name"
```

how to kill a process
```
kill pid   // pid means process id
```

how to showing list of listen (running) port
```
ss -tlnp
```
* **t** - for TCP ports
* **l** - for LISTEN port
* **n** - for showing port number
* **p** - for showing process which is attached this port

how to check a port is running or not
```
ss -anp | grep portnuber
```
* **a** - it used to fetch all ports and grep filter specific port number

how to kill running port. suppose we want to kill a port 8082
```
 1st - find pid
 ss -anp | grep 8082
 
 2nd - kill process
 kill -9 pid
```

## Working on FTP

install ftp client in linux
```
 yum install lftp
```
connect ftp server
```
 ftp xxx.xxx.xxx.xxx
```
show files and folder of ftp server
```
 ls
```
print current working directory iside ftp
```
 lpwd
```
change local directory from ftp
```
 lcd path-of-directory  //Ex: lcd /home/docker
```
download file from ftp to local directory
```
 pget file-name //Ex: pget mysql.ta
```
takes file from local directory and upload to ftp server
```
 put file-name //Ex: put mysql.tar
```

## Working on USB

show block list device with details. They show UUID, LABEL, NAME
```
 blkid
```
mount usb device which show on blkid command
```
  mount -L HP /media (..using label name)
  mount -U BXXX-XXXX (..using UUID)
  mount -t auto /dev/sda /media (..using name)
```
enter in usb device
```
  cd /media
```

## SSH Connection

connect remote mechine
```
 ssh username@hostname or ip
```
#### create ssh key for secure connection. create key in local mechine and copy it on remote mechine

* Generate Key on local machine
   ```
    ssh-keygen -t rsa -b 4096

    [-t type of encription, -b bits]
   ```
* copy key to remote mechine
   ```
    ssh-copy-id username@hostname or ip
   ```

#### Create ssh connection using identity file (like aws ec2)

* Generate ssh key on remote machine
  ```
   ssh-keygen -t rsa -b 4096 -C "kvm"
   
   [-t type of encription, -b bits, -C comment]
  ```
* Rename **id_rsa.pub** file to **authorized_keys**
  ```
   mv id_rsa.pub authorized_keys
  ```
* Open **id_rsa** file of remote machine and copy this file content
  ```
   cat .ssh/id_rsa
  ```
* Create .pem file in local machine and past **id_rsa** file content
  ```
   vi abc.pem
  ```
* Connect remote machine using identity file
  ```
   ssh -i abc.pem username@hostname or ip
   [-i = identity file location]
  ```
#### How to remove passphrase from ssh private key file
passphrase is a password of private key file that protect private key. Remove it using following way
```
ssh-keygen -p -f private-key-file
```

## Give sudo privilege to a user

open sudoers file
```
 sudo visudo
```
add user to sudoers file
```
 username ALL=(ALL) NOPASSWD:ALL
```

## Create environment variable in linux

open **.bashrc** file using vim editor
```
vi ~/.bashrc
```
Write this command end of the line at .bashrc file. This command create enviorment variable
```
export key=value

Example:- export JAVA_HOME=/etc/usr/jdk8/
```
Reload **.bashrc** script without looging
```
source ~/.bashrc
```
Show list of env variable
```
env or printenv
```
