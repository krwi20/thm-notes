Where is Linux used?
- linux is considerably much more lightweight
- linux powers things such as:
- websites that you visit
- car entertainment/control panels
- point of sales systems
- critical infrastructures such as traffic light controllers
- first release was 1991

Flavours of Linux
- name linux is actually an umbrella term for multiple os's based on UNIX (another os)
- thanks to linux being open source, variants of linux come in all shapes and sizes
- butuntu & debian are some of the more commonplace distros
- you can run ubuntu as a server (such as websites and web apps) or as a fully-fledged desktop

Research: What year was the first release of a Linux operating system?
- 1991

first commands
command -> description
echo -> output any text that we provide
whoami -> find out what user we are currently logged in as

If we wanted to output the text "TryHackMe", what would our command be?
- echo TryHackMe

What is the username of who you're logged in as on your deployed Linux machine?
- tryhackme

Interacting with the filesystem
ls -> listing
cd -> change directory
cat -> concatenate
pwd -> print working directory

On the Linux machine that you deploy, how many folders are there?
- 4

Which directory contains a file? 
- folder4

What is the contents of this file?
- Hello World!

Use the cd command to navigate to this file and find out the new current working directory. What is the path?
- /home/tryhackme/folder4

Using find
- find -name passwords.txt

- wildcard * to search for anything that has .txt in the end
- find -name *.txt

Using grep
- allows us to search the contents of files for specific values we are looking for
- 'wc' count the number of entries in file
- using grep to find any entries with the IP addr 81.143.211.90 in access.log
- grep "81.143.211.90" access.log

Use grep on "access.log" to find the flag that has a prefix of "THM". What is the flag? Note: The "access.log" file is located in the "/home/tryhackme/" directory.
- THM{ACCESS}

Introduction to shell operators
& -> operator allows you to run commands in the background of your terminal
&& -> allows you to combine multiple commands together in one line
`>` -> redirector - meaning we can take the output from a command (such as using cat to output a file) and direct it elsewhere
`>>` -> does the same function of > but appends the output rather than replaceing (meaning nothing is overwritten)

&
- allows us to execute commands in the background
- e.g. say we want to copy a large file -> will take a loing time and leave us unable to do anything until the file successfully copies
- & allows us to execute the command and have it run in the background allowing us to do other things

&&
- bit misealding in the sense of how familiar it is to &
- can use && to make a list of commands to run e.g. command1 && command2 
- however worth nothing command2 will only run if command1 was successful

`>`
- we take the ouput from a command we run and output it to somewhere else
- e.g. redirecting the echo command 
- lets say we wanted to create a file named "welcome" with the message "hey" we can run echo hey > welcome where we want the file created with the contents hey
- echo hey > welcome
- cat welcome (shows hey)
- if the file "welcome" already exists the contents will be overwritten

`>>`
- rather than overwriting any contents it just puts the output at the end
- e.g. if we now did echo hello >> welcome
- cat welcome (shows hey hello)

If we wanted to run a command in the background, what operator would we want to use?
- &

If I wanted to replace the contents of a file named "passwords" with the word "password123", what would my command be?
- echo password123 > passwords

Now if I wanted to add "tryhackme" to this file named "passwords" but also keep "passwords123", what would my command be?
- echo tryhackme >> passwords

