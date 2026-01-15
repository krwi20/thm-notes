System Configuration & Advanced System Settings

System Configuration
- the system configuration utility (MSConfig) is for advanced troubleshooting and its main purpose is to help diagnose startup issues
- several methods to launch system configurations, one method is from the start menu
** note ** you need local admin rights to open this utility

- the utility has 5 tabs across the top
- general
- boot
- services
- statup
- tools

- in the general tab we can select what devices and services for windows to load upon boot
- the options are: normal, diagnostic, or selective

- in the boot tab we can define various boot options for hte os

- the services tab lists all services configured for the system regardless of their state (running or stopped) 
- a service is a special type of application that runs in the background

- in the startup tab you wont see anything interesting in the attached vm
- ms advises using Task Manager (taskmgr) to manage (enable/disable) startup items
- the system configuration utility is NOT a startup management program
- on windows server machines the only reliable way to view-user level startup items is through the startup folder itself
- you can access it by opening run dialog typing shell:startup and pressing enter
- this will display all startup programs as shortcuts or execs that are configured to run automatically the next time a user logs in
- this is where you can verify applications that are configured to launch at startup

- coming back to the msconfig
- there is a list of various utilities (tools) in the tools tab 
- here we can run to configure the os further
- there is a selected command section
- the info in the textbox will change per tool
- to run a tool we can use the command to launch the tool via run prompt, cmd prompt or by clicking the launch button

Advanced System Settings
- windows gives you some additional configuration settings as well
- which you can control the performance behaviour and system recovery
- to access this option you can search for View advanced system settings in your search bar and open it
- this will open a System Properties panel

- windows uses a page file as an extra virtual memory space when the physical RAM becomes full
- this helps to prevent slowdowns or application crashes when the system runs out of memory
- you can view or modify the page file by navigating to the Advanced option at the top and clicking Settings under the Performance tab
- after clicking settings you will get the Performance Options Window

- in this performance tab the advanced option can also tell you about the page file size configured for the drives
- the other settings here can give you the following info
- the drive where the page file is stored
- the initial size (MB)
- the maximum size
- whether windows manages the size automatically

- there is another cool config you can find in the Advanced SYstem Settings
- Startup & Recovery !
- windows can create a crash dump file whenver it encounters a critical error such as a Blue Screen of Death
- this crash dump helps the admin or analysts understand what went wrong during the crash
- you can view or modify the crash dump settings by navigating to the Advanced option at the top and then clicking Settings under Startup & Recovery section

- here you will find different settings for the startup and revcoery
- the Write debugging information dropdown tells you the type of crash dump configured for the system
- windows supports different dump types such as
- automatic memory dump
- kernel memory dump
- small memory dump (256KB)
- complete memory dump
-none

- this setting shows how much information windows will save in the crash dump when a system crash occurs

What is the name of the service that lists Systems Internals as the manufacturer?
- PsShutdown

Whom is the Windows license registered to?
- Windows User

What is the command for Windows Troubleshooting?
- C:\Windows\System32\control.exe /name Microsoft.Troubleshooting

What command will open the Control Panel? (The answer is  the name of .exe, not the full path)
- control.exe

Changing UAC Settings
- continuing with tools that are available through the System Configuration panel
- User Account Control (UAC) was covered in great detail in part 1
- the UAC settings can be changed or even turned off entirely (not recommended) 
- you can move the slider to see how the setting will change the UAC settings and ms's stance on the setting

- the slider has 4 security levels each of which controls how windows alerts you when apps or users try to make changes at the system level
- they fall into 4 standard categories

- always notify: this is the highest security. windows notifies you whenever apps or you yourself try to make changes and the desktop dims (secure desktop)
- notify for apps: windows notifies only when apps try to make changes, but not when you change windows settings. option is enabled by default
- notify without dimming: same as above (noti for apps) but this time screen does not dim
- never notify: notifications are turned off. windows wont warn you about changes made by you or any apps

- you can find the current level by looking at the position of the slider in the User Account Control Settings window

What is the command to open User Account Control Settings? (The answer is the name of the .exe file, not the full path)
- UserAccountControlSettings.exe

Computer Management
- continuing with tools that are available through the System Configuration Panel
- the Computer Management (compmgmt) utility has 3 primary sections
- System Tools, Storage, Services & Applications

System Tools
- lets start  with Task Scehduler
- per ms with task scheduler we can create and manage common tasks that our computer will carry out automatically at the times we specifiy
- a task can run an application, a script etc
- tasks can be configured to run at any point
- a task can run at log in or log off
- tasks can also be configured to run on a specific schedule e.g. every 5 min

- to view the scheduled tasks that are present on the system, click Task Scheduler Library
- this will display all the scheduled tasks of the system
- you can click on any of them to view their details
- it is important to note that some scheduled tasks are not recurring and are made just to run once at a specific time
- in this case we would see something like At 2:50 PM on 6/15/2025 as the trigger

- to create a basic tasks click on Create Basic Task under Actions (right pane)

Event Viewer
- allows us to view ervents that have occured on the computer
- these records of events can be seen as an audit trail that can be used to understand the activity of the computer system
- this info is often used to diagnose problems and investigate actions executed on the system
- event viewer has 3 panes
- the pane on the left provides a hierarchical tree listing of the event log providers
- the pane in the middle will display a general overview and summary of the events specified to a selected provider
- the pane on the right is the actions pane

- there are 5 types of events that can be logged

![event logging types](images/event_logging_types.png "event logging types")

- the standard logs are visible under Windows Logs

![standard logs](images/standard_logs.png "standard logs")

Shared Folders
- where you will see a complete list of shares and folders that others can connect to
- C$ the default share of windows
- ADMIN$ default remote admin shares created by windows
- as with any object in windows you can right click a folder to view its properties such as permissiosn

- under sessions you will see a list of users who are currently connected to the shares
- all the folders and/or files that the connected user access will list under Open Files

- The Local Users and Groups sections should be familiar from part 1 because its lusrmgr.msc

- in Performance youll see a utility called Performance Monitor (perfmon)
= perfmon is used to view performance data either in real-time or from a log file
- this util is useful for troubleshooting performance issues on a computer system whether local or rmote

Device Manager
- allows us to view and configure the hardware such as disabling any hardware attached to the computer

Storage
- under storage is Windows Server Backup & Disk Management 
- only cover Disk Management here for now

Disk Management
- a system utility in windows that enables you to perform advanced storage tasks
- some tasks are:
- set up a new drive
- extend a partition
- shrink a partition
- assign or change a drive letter e.g. E:

Services & Applications
- recall from the prev task a service is a special type of application that runs in the background
- you can see all the services and their statuses by clicking the Services button given under the Services & Application section

- the servies shown have their display names, status and other values
- if you want to get more info about any service right click on the service and click properties
- here you will see additional details such as the service name (which differs from the display name) the path to its exec, its startup type, and other relevamt info

- there is a field known as Startup type in a service's Properties window 
- it determines how and when the service is configured to start
- we can set a service to Automatic which means it starts every time the system boots
- or Manual which means it only starts when another process or user triggers this service
- or Disabled which means it should not run at all

- WMI Control configures and controls Windows Management Instrumentation service
- Per Wikipedia, "WMI allows scripting languages (such as VBScript or Windows PowerShell) to manage Microsoft Windows personal computers and servers, both locally and remotely. Microsoft also provides a command-line interface to WMI called Windows Management Instrumentation Command-line (WMIC)."

** note ** the WMIC tool is deprecated in win 10 version 21H1 - powersehll supersedes this tool for WMI

What is the command to open Computer Management?
- compmgmt.msc

When is the npcapwatchdog scheduled task set to run at?
- At system startup

What is the name of the hidden folder that is shared?
- sh4r3dF0Ld3r

System Information
- continuing with tools that are available through the System Configuration panel
- what is the SYstem Information (msinfo32) tool?
-Per Microsoft, "Windows includes a tool called Microsoft System Information (Msinfo32.exe).  This tool gathers information about your computer and displays a comprehensive view of your hardware, system components, and software environment, which you can use to diagnose computer issues."
- the information in System Summary is divided into 3 sections
- hardware resources
- components
- software environment

- the information displayed in hardware resources is not for the average computer user refer to ms official pages

- under components you can see specific information about the hardware devices installed on the computer
- some sections dont show any information but some sections do such as display and input

- in the software environment section you can see information about the software baked into the os and software you have installed
- other details are visible in this section as well suich as the Envinronemnt Variables and Network Connections

- recall from part 1 the Windows\System32 task where Environment Variables was briefly touched on

- Per Microsoft, "Environment variables store information about the operating system environment. This information includes details such as the operating system path, the number of processors used by the operating system, and the location of temporary folders.
The environment variables store data that is used by the operating system and other programs. For example, the WINDIR environment variable contains the location of the Windows installation directory. Programs can query the value of this variable to determine where Windows operating system files are located".

- click on Environment Variables to see the assigned values for the VM

- another method to view environment variables is 
- Control Panel > System and Security > System > Advanced system settings > environement variables
- or
- settings > system > about > system info > advanced system settings > environment variables

- lets redirect our attention back to msinfo32
- towards the very bottom of this utility there is a search bar
- try select componenets and search for IP address

What is the command to open System Information? (The answer is the name of the .exe file, not the full path)
- msinfo32.exe

What is listed under System Name?
- THM-WINFUN2

Under Environment Variables, what is the value for ComSpec?
- %SystemRoot%\system32\cmd.exe

Resource Monitor
- continuing with tools that are available through the System Configuration panel

- what is Resource Monitor (resmon)?
- Per Microsoft, "Resource Monitor displays per-process and aggregate CPU, memory, disk, and network usage information, in addition to providing details about which processes are using individual file handles and modules. Advanced filtering allows users to isolate the data related to one or more processes (either applications or services), start, stop, pause, and resume services, and close unresponsive applications from the user interface. It also includes a process analysis feature that can help identify deadlocked processes and file locking conflicts so that the user can attempt to resolve the conflict instead of closing an application and potentially losing data."

- as some other tools mentioned in this room, this utility is primarily geared to advanced users who need to perform advanced troubleshooting on the conputer system
- in the overview tab Resmon has 4 sections
- CPU
- Disk
- Network
- Memory

- the same 4 sections have corresponding tabs across the top
** note ** each tab has additional info for each
- has a pane on the right to show a graphical view in real time for each section

What is the command to open Resource Monitor? (The answer is the name of the .exe file, not the full path)
- resmon.exe

Command Prompt
- continuing with tools that are available through the System Configuration panel

- the command prompt (cmd) can seem daunting at first but its really not that bad
- in early os the command line was the sole way to interact with the os
- when the GUI was introduced it allowed users to perform complex tasks with a few clicks of a button instead of entering commands in the cmd prompt

- even though the GUI is the primary way to interact with the os a computer user can still interact via the cmd prompt
- in this task we will only cover a few commands that a computer user can run in the cmd prompt to obtain info about the computer system

- the command hostname will output the computer name
- C:\Users\Administrator>hostname
- THM-WINFUN2

- the command whoami will output the name of the logged-in user
- C:\Users\Administrator>whoami
- thm-winfun2\administrator

- lets look at some cmds that are useful when troubleshooting
- command often used is ipconfig
- this command will show the network address settings for the computer

- each command will have a help manual to explain the expected syntax to execute the cmd properly
- along with any additional params that can be added to the cmd to expand its execution

- e.g. to see the help manual for ipconfig
- you can use the following command 
- ipconfig /?

** note ** to clear the cmd prompt screen the command is cls

- the next command is netstat
- per the manual this command will display protocol statistics and current TCP/IP network connections

- the structure of the syntax for the command tells us the netsta command can be
- run on its own or with params such as -a, -b, -c ...
- when any of the params are appended to the root command
- netstat in this case
- the output changes

- the net command is primarily used to manage network resources
- this command supports sub-commands
- if you type net without a sub-command the output will show the syntax for the root command showing a few of the sub-commands you can use

- for the net command to display the help manual /? will not work
- in this case you need to use different syntax which is net help

- so if you wish to see the help information for net user
- the command is net help user

- you can use the same command to view the help for other useful net sub-commands such as localgroup, use, share, and session

In System Configuration, what is the full command for Internet Protocol Configuration?
- C:\Windows\System32\cmd.exe /k %windir%\system32\ipconfig.exe

For the ipconfig command, how do you show detailed information?
- ipconfig /all

Registry Editor
- continuing with tools that are available through the System Configuration panel

- the Windows Registry (per microsoft) is a central hierarchical database used to store info necessary to configure the system for one or more users, applications and hardware devices

- the registry contains information that windows continually references during operations such as
- profiles for each user
- applications installed on the computer and the types of documents that each can create
- property sheet settings for folders and application icons
- what hardware exists on the system
- the ports that are being used

** warning ** the registry is for advanced computer users making changes to the registry can affect normal computer operations

- ther are various wasys to view/edit the registry
- one way is to use the Registry Editor (regedit)

What is the command to open the Registry Editor? (The answer is the name of  the .exe file, not the full path)
- regedt32.exe