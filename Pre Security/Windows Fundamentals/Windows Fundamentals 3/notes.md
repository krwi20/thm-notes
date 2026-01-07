Windows Updates
- a service providede by ms to provide security updates, feature enhancements and patches for the windows os and other ms products like ms defender
- updates are typicall released on the 2nd tuesday of each month
- this day is called patch tuesday
- doesnt always mean that a critical update/patch has to wait for the next patch tuesday to be released
- if the update is urgent then ms will push the update vie the windows update service to windows devices

- located in settings
- another way to access windows update it from the run dialog or cmd by running command
- control /name Microsoft.WindowsUpdate

- throughout the years windows users have grown accustomed to pushing windows updates off to a later date or not installing updates at all
- various reasons caused this actions, one being the fact that a reboot is typically required after a windows update
- ms notably addressed this issue with win 10
- the updates can no longer be ignored or pushed to the side until forgotten
- windows updates can only be postponed but eventually the update will happen and your computer will reboot
- ms provides these to keep the devices safe and secure

There were two definition updates installed in the attached VM. On what date were these updates installed?
- 5/3/2021

Windows Security
- Per Microsoft, "Windows Security is your home to manage the tools that protect your device and your data".
- also available in settings
- protection areas:
- virus & threat protection
- firewall & network protection
- app & browser control
- device security

- status icons:
- green -> means your device is sufficiently protected and there arent any recommended actions
- yellow -> means there is a safety recommendation for you to review
- red -> is a warning that something needs your immediate attention

Virus & Threat Protection
- divided into 2 parts
- Current threats 
- Virus & threat protection settings

Current Threats
- scan options:
- quick scan: checks folders in your system where threats are commonly found
- full scan: checks all files and running programs on your hard disk. this scan could take longer than one hour
- custom scan: choose which files and locations you want to check

Threat History
- last scan: windows defender antivirus automatically scans your device for viruses and other threats to help keep it safe
- quarantined threats: quarantined threats have been isolated and prevented from running on your device. they will be periodically removed
- allowed threats: allowed threats are items identified as threats which you allowed to run on your device

** warning ** allow an item to run that has been identified as a threat only if you are 100% sure of what you are doing

Checking the Security section on your VM, which area needs immediate attention?
- Virus & threat protection

Virus & Threat Proection Settings
- manage settings:
- real-time protection: locates and stops malware from installing or running on your device
- cloud-delivered protection: provides increased and faster protection with access to the latest protection data in the cloud
- automatic sample submission: send sample files to ms to help protect you and others from potential threats
- controlled folder access: this feature, if enabled, protects  files, folders and memory areas on your device from unauthorised changes by malicious or unknown applications. if it is enabled only approved and trusted apps would be allowed to modify these files in the protected folders. to enable this feature click on the Manage Controlled folder access button under Controlled Folder Access and turn it on
- exclusions:  windows defender antivirus allows you to exclude any files or folders from the antivirus scanning. this is done to reduce the number of false positives. admins might not want the antivirus to scan specific files or folders. by adding them to the exclusions list, the antivirus would ignore them and scan all other files and folfders. to add any file or folder to the Windows Defender exclusion list click on the Add or remove exclusions button under Exclusions and add as many exclusions as you want
- notifcations: windows defender antivirus will send notifications with critical information about the health and security of your device

** warning ** excluded items could contain threats that make your device vulnerable. only use this option if you are 100% sure of what you are doing

Virus & threat protection updates
- check for updates: manually check for updates to update windows defender antivirus definitions

Ransomwware Protection
- controlled folder access - ransomware protection requires this feature to be enabled, which in turn requires real-time protection to be enabled

** note ** real time protection is turned off in the attached VM to decrease the chances of performance issues. since the VM cant reach the internet there arent any threats in the VM this is safe to do. Real time protection should definitely be enabled in your personal windows devices unless you have a 3rd part product that provides the same protection. ensure it is  always up to date and enabled.

- tip: you can perform on-demand scans on any file/folder by right clicking the item and selecting scan with ms defender

Specifically, what is turned off that Windows is notifying you to turn on?
- Real-time protection

Firewall & Network Protection
- what is a firewall?
- Per Microsoft, "Traffic flows into and out of devices via what we call ports. A firewall is what controls what is - and more importantly isn't - allowed to pass through those ports. You can think of it like a security guard standing at the door, checking the ID of everything that tries to enter or exit".

- what is the difference between the 3 (Domain, Private, Public)
- domain: the domain profile applies to networks where the host system can authenticate to a domain controller
- private: the private profile is a user-assigned profile and is used to designate private or home networks
- public: the default profile is the public path, used to designate public networks such as WiFi hotspots at coffee shops, airpots ...

- if you click on any firewall profile another screen will appear with two options
- turn the firewall on/off
- block all incoming connections

** Warning ** unless you are 100% confident in what you are doing, it is recommended that you leave your Windows Defender Firewall enabled. 

- you can view what the current settings for any firewall profile are
- several apps have access in the private and/or public firewall profile
- some of the apps will provide additional info if its available via the Details button

Advanced settings
- confuring the windows defender firewall is for advanced windows users read documentation

- tip: command to open the windows defender firewall is WF.msc

If you were connected to airport Wi-Fi, what most likely will be the active firewall profile?
- Public network

App & Browser Control
- in this section you can change the settings for the Microsoft Defender SmartScreen
- Per Microsoft, "Microsoft Defender SmartScreen protects against phishing or malware websites and applications, and the downloading of potentially malicious files".
- refer to documentation

- you can see the status of the smart screen set to Warn below
- you can also change it to either Block or completely Off

Check apps and files
- windows defender smartscreen helps protect your devices by checking for unrecognised apps and files from the web

Exploit protection
- built into windows 10 to help protect your device against attacks

** Warning ** Unless you are 100% confident in what you are doing, it is recommended that you leave the default settings. 

Device Security
- even though these will probably never be changed we will cover it

Core Isolation
- memory integrity: prevents attacks from inserting malicious code into high-security processes

** Warning ** Unless you are 100% confident in what you are doing, it is recommended that you leave the default settings. 

Security Processor
- called the Trusted Platform Module (TPM) is providing additional encryption for your device
- security processor details

- what is the TPM?
- Per Microsoft, "Trusted Platform Module (TPM) technology is designed to provide hardware-based, security-related functions. A TPM chip is a secure crypto-processor that is designed to carry out cryptographic operations. The chip includes multiple physical security mechanisms to make it tamper-resistant, and malicious software is unable to tamper with the security functions of the TPM".

What is the TPM?
- Trusted Platform Module

BitLocker
- what is bitlocker?
- Per Microsoft, "BitLocker Drive Encryption is a data protection feature that integrates with the operating system and addresses the threats of data theft or exposure from lost, stolen, or inappropriately decommissioned computers".

- on devices with TPM installed BitLocker offers the best protection

- Per Microsoft, "BitLocker provides the most protection when used with a Trusted Platform Module (TPM) version 1.2 or later. The TPM is a hardware component installed in many newer computers by the computer manufacturers. It works with BitLocker to help protect user data and to ensure that a computer has not been tampered with while the system was offline".

- refer to more documentation
- https://docs.microsoft.com/en-us/windows/security/information-protection/bitlocker/bitlocker-overview

We should use a removable drive on systems without a TPM version 1.2 or later. What does this removable drive contain?
- startup key

Volume Shadow Copy Service
- per Microsoft "the Volume Shadow Copy Service (VSS) coordinates the required actions to create a consistent shadow copy (also known as a snapshot or a point-in-time copy) of the data that is to be backed up. "

- volume shadow copies are stored on the systems volume information folde ron each drive that has protection enabled
- if VSS is enabled (System Protection turned on) you can perform the following tasks from within advanced system settings
- creates a restore point
- perform system restore
- configure restore settings
- delete restore points

- from a security perspective, malware writers know of this windows feature and write code in their malware to look for these files and delete them
- doing so makes it impossible to recover from a ransomware atack unless you have an offline/off-site backup

What is VSS?
- Volume Shadow Copy Service

- https://learn.microsoft.com/en-us/windows/win32/amsi/antimalware-scan-interface-portal
- https://learn.microsoft.com/en-us/windows/security/identity-protection/credential-guard/configure?tabs=intune
- https://support.microsoft.com/en-us/windows/configure-windows-hello-dae28983-8242-bb2a-d3d1-87c9d265a5f0#:~:text=Windows%2010,in%20with%20just%20your%20PIN.
- https://www.csoonline.com/article/564531/the-best-new-windows-10-security-features.html