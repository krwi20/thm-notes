Windows Editions

- windows os has a long history dating back to 1985
- it is the dominant os system in both home use and corporate networks
- because of this windows has always been targeted by hackers and malware writers

- windows xp was a popular version of windows and had a long-running 
- ms annouced windows vista which was a complete overhaul of the windows os
- there were many issues with vista -> wasnt received well by windows users and it was quickly phased out

- when ms announced the end-of-life data for windows xp, many customers panicked
- coprs, hospitals etc scrambled and tested the next viable windows version -> windows 7 against many other hardware and devices
- vendors had to work against the clock to ensure their products worked with win 7 for their customers
- if they couldnt, their customers had to break their agreement and find another vendor that upgraded their products to work with win 7
- it was a nightmare for many and ms took note of it

- win 7 as quickly as it was released soon after was marked with end of support date
- windows 8.x came and left and it was short-lived like vista

- then arrived windows 10 followed by windows 11 which is the current windows os version for desktop computers
- windows 11 came in 2 flavours, home and pro
- even tho we didnt mention servers, the current version of the windows os for servers is windows server 2025

- many critics like to bash ms but they have made long strides to improve the usability and security with each new version of windows

What encryption can you enable on Pro that you can't enable in Home?
- BitLocker

The Desktop (GUI)
- the windows destop, is the screen that welcomes you once you log into a windows 10 machine
- traditionally you need to pass the login screen first
- the login screen is where you need to enter valid account credentials - usually a username & password of a pre-existing windows acc on that particular system or in the active direcotry environment (if its a domain-joined machine)

- the desktop is where you willl have shortcuts to programs, folders, files
- these icons will be either well organised in folders and sorted alphabetically or scattered randomly with no specific organisation on the desktop
- the look and feel of the desktop can be changed to suit your liking
- right clicking anywhere on the desktop -> context menu will appear
- menu allows you to change the size of the desktop icons
- specify how you want to arrange tem
- copy/paste items to the desktop
- create new items - folder, shortcut, txt doc

- under display settings you can make changes to the screens resolution and orientation
- in case you have multiple computer screens you can make configs to the multi-screen setup here
- in a remote desktop session some of the display settings will be disabled

- you can also change the wallpaper by selecting personalise
- under personalise you can change the background image to Desktop, change fonts, themes, color scheme ...

- the start menu
- in previous versions the word start was visible at the bottom left corner of the gui
- in modern version of windows the word start doesnt appear just a logo
- even though style has changed -> purpose remains the same

- start menu provides access to all the apps/programs, files, utility tyools etc that are most useful
- clicking on the windows logo the start menu will open
- its broken up into secions
- quick shortcuts
- recently added apps/programs
- icons for specific app/programs known as tiles -> some by default some added

- the taskar
- some of the components are enabled and visible by default
- you can right click to bring up context menu to make changes
- any apps/programs,folders,files etc you open/start will appear in the taskbar
- hovering over the icon will provide a preview thumbnail and a tooltip

- notifcation area
- typically located bottom right
- where date and time is displayed
- other icons possibly visible in this area are the volume, network/wirless icon

Which selection will hide/disable the Search box?
- Hidden

Which selection will hide/disable the Task View button?
- Show Task View button

Besides Clock and Network, what other icon is visible in the Notification Area?
- Action Center

Introduction to Windows
- the windows os is a complex product with many system files, utilities, settings, features ...

The File System
- the file system used in modern versions of windows is the New Technology File System or simply NTFS
- before NTFS there was FAT16/FAT32 (File Allocation Table) and HPFS (High Performance File System)
- you still see FAT partitions in use today
- e.g. you typically see FAT parititions in USB devices, MicroSD cards, etc 
- but traditionally not on personal windows computers/laptops or windows servers

- NTFS is known as journalling file system
- in case of failure the file system can automatically repair the folders/files on disk using info stored in a log file
- this function is not possible with FAT

- NTFS addresses many of the limitations of the previous file systems such as 
- supports files larger than 4gb
- set specific permissions on folders and files
- folder and file compression
- encryption (Encryption File System or EFS)

- if you are running on windows what is the file system your windows installation is using?
- you can check the properties (right click) of the drive your os is installed on (typically C:\)

- on NTFS volumes you can set permissions permissions that grant or deny access to files and folders
- the permissions are:
- full control
- modify
- read & execute
- list folder contents
- read
- write

- the below image lists the meaning of each permissions on how it applies to a file and a folder

![ntfs perms](images/ntfs_permissions.png "ntfs perms")

- how can you view the permissions for a file or folder?
- right click the file or folder you want to check for permissions
- from the context menu select properties
- within properties click the security tab
- in the group or user names list select the user, computer or group whose permissions you want to view

- refer to ms documentation to get a better understanding of the NTFS permissions for Special Permissions

- Alternate Data Streams (ADS) is a file attribute specific to  Windows NTFS (New Technology File System)
- every file has at least one data stream ($DATA) and ADS allows files to contain more than one stream of data
- natively windows explorer doesnt display ADS to the user
- there are 3rd party executables that can used to view this data
- PowerShell also gives you the ability to view ADS for files
- from a security perspective malware writers have used ADS to hide data
- not all its uses are malicious:
- e.g. when you downloaded a file from the internet there are identifiers written to ADS to identify that the file was downloaded from the internet

What is the meaning of NTFS?
- New Technology File System

The Windows\System32 Folders
- the windows folder C:\Windows is traditionally known as the folder which contains the windows os
- the folder doesnt have to reside in the C drive necessarily 
- it can reside in any other drive and technically can reside in a different folder

- this is where environment variables, more specifically, system environment variables, come into ply
- the system environment variable for the windows directory is %windir%

- per Microsoft: " Environment variables store information about the operating system environment. This information includes details such as the operating system path, the number of processors used by the operating system, and the location of temporary folders"

- there are many folders within the 'Windows' folder
- one of the many folders is System32

- the System32 folder holds the important files that are critical for the os
- you should proceeed with extreme caution when interacting with this folder
- accidently deleting any files or folders within System32 can render the windows os inoperational

- many of the tools covered in Windows Fundamentals series reside within the System32 folder

What is the system variable for the Windows folder?
- %windir%

User Accounts, Profiles & Permissions
- user accounts can be one of two types on a typical local windows system
- Administrator & Standard User

- Administrator -> can make changes to the system: add users, delete users, modify groups, modify settings on the system ...
- Standard User -> can only make changes to folders/files attributed to the user & cant perform system-level changes, such as install programs

- to check which user accounts exist on the system
- click start menu -> type other user -> shortcut to system settings > other users should appear
- if you click on it a settings window should appear
- as an admin you will see an option to add someone else to this pc
- click on the local user acc -> more options appear -> change acc type and remove

- when a user acc is created a profile for the user is created for the user
- the location for each user profile folder will fall under C:\Users

- the creation of the user's profile is done upon initial login
- when a new user account logs in to a local system for the first time theyll see several messages on the login screen
- one of the messages -> user profile service sits on the login screen for a while, which is at work creating the user profile

- once logged in the user will see a small dialog box indicating the the profile is in creation

- each user profile witll have the same folders. a few of them are
- desktop
- documents
- downloads
- music
- pictures

- another way to access this information and then some, is using Local user and Group management
- right click on the start menu -> click run -> lusrmgr.msc
- should see 2 folders Users and Groups

- if you click groups you see all the names of the local groups along with a brief description for each one
- each group has permissions set to it, and users are assigned/added to groups by the admin
- when a user is assigned a group the user inherits the permissions of that group
- a user can be assigned to multiple groups

** note ** if you click on add someone else to this PC from other users, it will open Local Users and Management

What is the name of the other user account?
- tryhackmebilly

What groups is this user a member of?
- Remote Desktop Users,Users

What built-in account is for guest access to the computer?
- Guest

What is the account description?
- window$Fun1!

User Account Control
- the large majority of home users are logged into their windows systems as local admins
- remember from the prev task that any user with admin as the acc type can make changes to the system

- a user doesnt need to run with high (elevated) priviliges on the system to run tasks that dont require such priviliges such as surfing the internet, working on a word document ...
- this elevated privilige increases the risk of system compromise because it makes it easier for malware to infect the system
- consequently since the user acc can make changes to the system, the malware would run in the context of the logged-in user

- to protect the local user with such priviliges microsoft introduced User Account Control (UAC)
- this concept was first introducted with the short-lived windows vista and continued with versions of windows that followed

** note ** UAC (by default) doesnt apply for the built in local admin account

- How does UAC work?
- when a user with an acc type of admin logs into a systemn, the current session doesnt run with elevated permissions
- when an operation requiring higher level priviiges needs to execute, the user will be prompted to confirm if they permit the operation to run
- this feature reduces the likelihood of malware successfully compromising your system

What does UAC mean?
- User Account Control

Settings & Control Panel
- on a windows system the primary locations to make changes are the settings menu and the control panel
- for a long time the control panel has been the go-to location to make system changes such as adding a printer, uninstalling a progrm etc
- the settings menu was introduced in windows 8, the first os system catered to touch screen tablets, and is still available on win 10
- as a matter of fact the settings menu is now the primary location a user goes if they are looking to change the system
- if you want to see which applications are installed on the system click programs in the control panel
- then select programs and features
- this will list all installed applications along with their names, publishers and version
- in this way you can verify any software that has been added to the system
- both can be accessed from the start menu
- control panel is the menu where you will access more complex settings and perform more complex actions
- in some cases you can start in settings and end up in the control panel

In the Control Panel, change the view to Small icons. What is the last setting in the Control Panel view?
- Windows Defender Firewall

Task Manager
- provides information about the applications and processes running on the system
- other info is also available such as how much CPU and RAM are being utilised which falls under Performance
- you can access the task manager by right clicking the taskbar
- task manager will open in simple view and wont show much info
- click on more details the view changes

What is the keyboard shortcut to open Task Manager?
- Ctrl+Shift+Esc