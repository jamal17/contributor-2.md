

jacquie: x:1004:1004: jacquie, 1,,:/home/jacquie :/bme the user signs into the system, he/she is taken to their Home directory, where all their personal files reside. This field provides the absolute path to the user's home directory (/home/jamal in this case). 7. Shell: This field show, the user has access to the shell mentioned in this field (user 'jamal' has been given access to /bin/bash or simply bash shell).

jacquie: x:1004:1004: jacquie, 1,,:/home/jacquie :/bin/bash

matthew: x:1005:1005: matthew, 1,,:/home/matthew :/bin/bash

to get depth in file I will take the entry of my user name jamal

jamal : x : 1001 : 1001 : jamalibrahim , 1 ,, : /home/jamal : /bin/bash

{--1--}{--2--}{--3--}{--4--}{---------5----------}{-----6------}{----7-----}

this is what i mention before this example each user in the system have a separate entry on a separate line in the /etc/password file, and each entry being limited with a colon(:).

We have a seven filed have been generated.

1- Username field: This field show the user account name;this user name must be used every time when we log in to the system.

2- Password field: Second field is the password field; not showing the actual password though. The 'x' in this field show the password is encrypted and saved in the /etc/shadow file.

3- UID field: Every time when a user account is created, it is assigned with a user id or UID(UID for the user 'jamal' is 1001, in this case) and this field specifies the same.

4-** GID field**: Like the UID field, this field specifies which group the user belongs to, the group details being present in /etc/group file.

5- Comment/Description/User Info field: This field is the short comment/description/information of the user account.

6- User Home Directory: Every time the user sign in to the system, he is taken to his home directory, where all his personal files reside. This field provides the absolute path to the user's home director(/home/jamal in this case).

7- Shell: This field show, the user has access to the shell mentioned in this field (user 'jamal' has been given access to /bin/bash or simply bash shell).

Adding new user accounts to Linux system

There are tow option to add a user to the system eithet by using the desktop tools or by using command line. We can use the command line by using a simple command adduser with the new user name it will created account for the new user with some files that will help to configure his account. When running command adduser the system will ask additional information for the new user. I will explain this information step by step.


$ sudo adduser jamal

Adding user 'jamal' ...

Adding new group 'jamal'(100) 1001)...

Adding new user 'jamal'(1001001)with group 'jamal' ...

Creating home directory '/home/jamal' jamal/'...

Copying files from '/etc/skel; skel'...

Enter new UNIX password:

Retype new UNIX password:

Ppasswd:: password updated successfullysuccefully

Changing the user information for jamal

Enter the new value, or press ENTER for the defualtdefault

Full Name[]:jamal ibrahimFull name []: jamal ibrahim

Room Number[]:Room Number []:

Work Phone[]:Work Phone []:

Home Phone[]:Other []:

Is the information correct?[Y/n] Y

As we see in the above example, how the adduser command add the new user information to the file (/etc/passwd) and create the new home directory and establish with some files from the /etc/skel then ask for new password and identify the information. At the end of the line asked to confirm and verify information by answering yes, which is to confirm its validity or to to answer no to redo the whole processing.

**Deleting user account from Linux systemDeleting user account from Linux system.

After we learning how to add a new user to the system, also we will learn how to delete the user account from the linux system. To remove user's name or account from the local system/server/workstation we should use the command userdel.


userdel:jamal mail spool(/var/mail/jamal)not found

This is all about the adding AND DELETING THE NEW USER ACCOUNT TO THE lINUX SYSTEM.

Package Managementin/bash

matthew: x:1005:1005: matthew, 1,,:/home/matthew :/bin/bash

to get depth in the file I will take the entry of my username jamal.

This is all about the adding and deleting the new user account to the Linux system.
Creating Groups

Let's look at the group file, the /etc/group file contain the all group details as well as the users belong to each group. 

This tructure is very similar to /etc/passwd.

root/h/jamal>>> sudo cat /etc/group

jamal :x: 1001:

tyler :x: 1002:

awil :x: 1003:

jacquie :x: 1004:

matthew :x: 1005:

jamal : x : 1001 :

{---1---}{---2---}{---3-----}{---4---}

We have a total of 4 fields have been generated.

1- jamal indicates the user name.

2- X indicates encrypted password, it is not really used with groups.

3- 1001 it is a group ID(GID).

4- It is the users that are in the group it will list here.

The command for adding group is "groupadd"

root/h/jamal>>> sudo groupadd student

root/h/jamal>>> sudo cat /etc/group

student :x: 1006

** Deleting group from Linux system using the command groudel**

root/h/jamal>>> sudo groupdel student

root/h/jamal>>> sudo cat /etc/group

The student group is been deleted from the system.

Adding user to the group

we will create another group to add any user to the new group.

root/h/jamal>>> sudo groupadd Linux3

Then we will use the command sudo gpasswd -a (user account) (group name) to add any user to the new group we create.

root/h/jamal>>> sudo gpasswd -a jamal Linux3

we will run the command of grep to confirm.

root/h/jamal>>> sudo grep jamal /etc/passwd

Jjamal : x : :x: 1001 : :1001 : :jamal Iibrahim , ,1 ,, ,,: /home/jamal : :/bin/bash
{---1----}{---2---}{---3-----}{---4----}{---------------5---------------}{----------6------}{-------7-----}


/etc/passwd fields

1. **Username field**: This field show the user account name; this user name must be used every time when we log in to the system.

2. **Password field**: Second field is the Password field, not showing the actual password though. The 'x' in this field show the password is encrypted and saved in the /etc/shadow file.
3. **UID field**: Every time when a user account is created, it is assigned with a user id or UID (UID for the user 'jamal' is 1001, in this case) and this field specifies the same.
4. **GID field**: Similar to the UID field, this field specifies which group the user belongs to, the group details being present in /etc/group file.
5. **Comment/Description/User Info field**: This field is the short comment/description/information of the user account.

6. **User Home Directory**: Every ti

Elive is based on Debian, the same distribution flavor as Ubuntu, so we use .deb files for our packages and those files collectively live in a repository.
Also, we can run the command "sudo cat /etc/group to confirm

root/h/jamal>>> sudo cat /etc/group

jamal :x: 1001:

tyler :x: 1002:

awil :x: 1003:

jacquie :x: 1004:

matthew :x: 1005:

Linux3 :x: 1006:jamal

Debian Package Management

Debian Package Management details can be found in the Debian Manuals
