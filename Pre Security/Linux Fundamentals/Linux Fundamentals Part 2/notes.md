What is SSH and how does it work?
- Secure shell or SSH is a protocol between devices in an encrypted form
- using cryptography any input we send in a human-readable form is encrypted for travelling over a network
- where it is then unencrypted once it reaches the remote machine

- ssh allows us to remotely execute commands on another device remotely
- any data sent between the devices is encrypted when it is sent over a network such as the internet

Using SSH to login to your linux machine
- syntax is very simple only need to provide 2 things
- IP addr of the remote machine
- correct credentials to a valid acc to login with on remote machine
- ssh tryhackme@ipaddr

What directional arrow key would we use to navigate down the manual page?
- down

What flag would we use to display the output in a "human-readable" way?
- '-h'

Introduction to Flags and Switches
- majority of commands allow for aguments to be providede
- args are indicated by a hyphen and a certain keyword known as flags or switches
- ls -a (short for --all) shows hidden 
- commands that accept these will also have a --help option

The Man(ual) page
- great source of info for both system commands and applications available on both a linux machine, which is accessible on the machine itself and online
- we can use the man acommand and provide the command we want to read the documentation for

Filesystem Interaction Continued
touch -> touch -> create a file
mkdir -> make directory -> create a folder
cp -> copy -> copy a file or folder
mv -> move -> move a file or folder
rm -> remove -> remove a file or folder
file -> file -> determine the type of a file

Creating files & folders (touch, mkdir)
- touch takes one argument, the name we want to give the file we create
- e.g. touch note
- simply creates a blank file 
- you would need to use commands like echo or text editors such as nano to add content to the blank file
= similar process for making a folder
- mkdir mydirectory

Removing Files & Folders (rm)
- rm is extraordinary out of the cmds covered so far
- can simply remove filesusing rm
- need to provide the -R switch alongside the name of the directory you wish to remove
- rm note
- rm -R mydirectory

Copying & Moving Files & folders(cp, mv)
- cp takes 2 args
- the name of existing file, name we wish to assign to the new file when copying
- cp copies the entire contents of the existing file inot the new file
- cp note note2

- moving a file takes 2 args 
- rather than copying and/or creating a new file
- mv will merge or modify the 2nd file that we provide as an arg
- you can only use mv to move a file to a new folder
- you can also use mv to rename a file or folder
- mv note2 note3

Determining File Type
- files usually have extensions
- file command takes one arg
- file note
- note: ASCII text

How would you create the file named "newnote"?
- touch newnote

On the deployable machine, what is the file type of "unknown1" in "tryhackme's" home directory?
- ASCII text

How would we move the file "myfile" to the directory "myfolder" 
- mv myfile myfolder

What are the contents of this file?
-THM{FILESYSTEM}

Permissions 101
- certain users cannot access certain files or folders
- ls -l shows 10 columns
- columns are very important in determining certain characteristics of a file or folder and whether or not we have access to it
- a file or folder can have a couple of characteristics that determine both what actions are allowed and what user or group has the ability to perform the given action
- read, write, execute

Briefly - The difference between users and groups
- linux -> permissions can be granular, that whilst a user technically owns a file, if the permissions have been set, then a group of users can also have either the same or a different set of permissions to the exact same file without affecting the file owner itself.
- reak world context -> the system user that runs a web server must have permissions to read and write files for an effective web application
- however companies such as web hosting companies will have to want to allow their customers to upload their own files for their website without being the webserver system user -> compromising the security of every other customer

Switching between users
- swtiching between users on a linux install is easy thanks to the su command
- unless you are a root user (or using root permissions through sudo) then you are required to know two things to facilitate this transition of user accs
- the user we wish to switch to, the user's password
- the su command takes a couple of switches that may be of relevance
- e.g. executing a cmd once you log in or specifying a specific shell to use
- simply by providing -l switch to su we start a shell that is much more similar to the actual user logging into the system -> we inherit a lot more preoprties of the new user e.g. environment variables and the likes

On the deployable machine, who is the owner of "important"?
- user2

What would the command be to switch to the user "user2"?
- su user2

Output the contents of "important", what is the flag?
- THM{SU_USER2}

Common Directories

/etc
- this root directory is one of the most important directories on your system
- the etc folder is a commonplace location to store system files that are used by your os

** side note ** passwd and shadow files are two special files for Linux as they show how your system stores the passwords for each user in encrypted formatting called sha512

/var
- var being short for variable data
- one of the main root folders found on a linux install
- folder stores data that is frequently accessed or written by services or applications running on the system
- e.g. log files from running services and applications are written here (/var/log) 
- or other data that is not necessarily associated with a specific user (e.g. databases)

/root
- unlike the /home directory the /root folder is actually the home for the "root" system user
- there isnt anything more to this folder other than just understanding that this is the home directory for the "root" user
- worth mentioning as the logical presumption is that this user would have their data in a directory such as /home/root by default

/tmp
- unique root directory
- short for temporary
- its volatile and is used to store data that is only needed to be accessed once or twice
- similar to the memory on your computer, once the computer is restarted the contents of this folder are cleared out
- useful in pentesting -> that any user can write to this folder by default, meaining once we have access to this machine it serves as a good place to store things like our enumeration scripts

What is the directory path that would we expect logs to be stored in?
- /var/log

What root directory is similar to how RAM on a computer works?
- /tmp

Name the home directory of the root user 
- /root

