Evaluation of Search Results
- on the internet everyone can publish their writings
- it can be in the form of blog posts, articles or social media posts
- it can be even in more subtle ways such as by editing a public wiki page
- this ability makes it possible for anyone to voice their unfounded claims
- everyone can express their opinion about the best cyber security practices, future programming trends, and how to best prepare for a DevSecOps interview

- it is our job as readers to evaluate the info
- we will mention a few things to consider when evaluating info
- source: identify the author or org publishing the information. consider whether they are reputable and authoritative on the subject matter. publishing a blog does not make one an authority on the subject
- evidence and reasoning: check whether the claims are backed by credible evidence and logical reasoning. we are seeking hard facts and solid arguments
- objectivity and bias: evaluate whether the information is presented impartially and rationally, reflecting multiple perspectives. we are not interested in authors pushing shady agendas, whether to promote a product or attack a rival
- corroboration and consistency: validate the presented information by corroboration from mulitple independent sources. check whether multiple reliable and reputable sources agree on the central claims

What do you call a cryptographic method or product considered bogus or fraudulent?
- snake oil

What is the name of the command replacing netstat in Linux systems?
- ss (socket statistics)

Search Engines
- every one of us has used an internet search engine
- however not everyone has tried to harness the full power of an internet search engine
- almost every internet search engine allows you to carry out advanced searches
- consider the following example
- google
- bing
- duckduckgo

- lets consider the search operators supported by google
- "exact phrase": double quotes indicates that you are looking for pages with the exact word or phrase. e.g. one might search for "passive reconnaissance" to get pages with this exact phrase.
- site: this operator lets you specify the domain name to which you want to limit your search e.g. we can search for success stories on TryHackMe using site:tryhackme.com success stories
- - : the minus sign allows you to omit search results that contain a particular word or phrase. e.g. you might be interested in learning about the pyramids but you dont want to view tourism websites; one approach is to search for pyramids -tourism or -tourism pyramids
- filetype: this search operator is indispensable for finding files instead of web pages. some of the file types you can search for using google are portable document format (pdf), microsoft word document (doc) windows excel spreadsheet (xls) and microsoft powerpoint presentation (ppt) e.g. to find cyber security presentations try searching for filetype:ppt cyber security.

- you can check more advanced controls in various search engines in the link below.
- https://github.com/cipher387/Advanced-search-operators-list
- however the above provides a good starting point

- How would you limit your Google search to PDF files containing the terms cyber warfare report?
- filetype:pdf cyber warfare report

- What phrase does the Linux command ss stand for?
- socket statistics

Specialised Search Engines
- you are familiar with internet search engines however how much are you familiar with specialised search engine?
- by this we refer to search engines used to find specific types of results...

Shodan
- a search engine for devices connected to the internet
- allows you to search for specific types and versions of servers, networking equipment, industrial control systems and IoT devices
- you may want to see how many servers are still running Apache 2.4.1 and the distribution across coutries.
- to find the answers we can search for apache 2.4.1 which will return the list of servers with the string "apache 2.4.1" in their headers
- https://www.shodan.io/search/examples for more examples

Censys
- at first glance appears similar to Shodan
- Shodan focuses on internet-connected devices and systems, such as server, routers, webcams and IoT devices
- Censys on the other hand focuses on internet-connected hosts, websites, certificates, and other internet assets
- some of its use cases include enumerating domains in use, auditing open ports and services, and discovering rogue assets within a network
- check out https://docs.censys.com/docs/ls-introductory-use-cases#/

VirusTotal
- an online website that provides a virus-scanning service for files using multiple antivirus engines
- allows users to upload files or provide URLs to scan them against numerous antivirus engines and website scanners in a single operation
- they can even input file hashes to check the results of previously uploaded files
- can check the community's comments for more insights
- occasionally a file might be flagged as a virus or a trojan
- however this might not be accurate for various reasons, and thats when the community members can provide a more in-depth explanation

Have I Been Pwned
- does one thing! tells you if an email address has appeared in a leaked data breach
- finding ones email within leaked data indicates leaked private information, more importantly, passwords
- many users use the same password across multiple platforms
- if one platform is breached their password on other platforms is also exposed
- indeed passwords are usually stored in encrypted format, however, many passwords are not that the complex and can be recovered using a variety of attacks

What is the top country with lighttpd servers?
- united states (used shodan)

What does BitDefenderFalx detect the file with the hash 2de70ca737c1f4602517c555ddd54165432cf231ffc0e21fb2e23b9dd14e7fb4 as?
- Android.Riskware.Agent.LHH

Vulnerabilities & Exploits

CVE
- we can think of Common Vulnerabilites and Exposures (CVE) program as as dictionary of vulnerabilites
- it provides a standardised identifier for vulnerabilites and security issues in software and hardware products
- each vuln is assigned a CVE ID with a standardised format like CVE-2024-29988 (heartbleed)
- this unique identifier (CVE ID) ensures that everyone from security researchers to vendors and IT professionals is referring to the same vuln, CVE-2024-29988 in this case

- the MITRE Corporation maintains the CVE system
- for more info and to search for existing CVEs visit https://www.cve.org/
- alternatively visit National Vulnerability Database (NVD) https://nvd.nist.gov/

Exploit Database
- there are many reasons why you would want to exploit a vulnerable application
- e.g. one would be assessing company's security as part of its red team
- needless to say we should not try to exploit a vulnerable system unless we are given permission, usually via a legally binding agreement
- now that we have permission to exploit a vulnerable system, we might need to find a working exploit code
- one resource is the exploit database https://www.exploit-db.com/
- the exploit database lists exploit codes from various authors, some of these exploit codes are tested and marked as verified

GitHub
- web based platform for software development
- can contain many tools related to CVEs along with proof-of-concept (PoC) and exploit codes

What utility does CVE-2024-3094 refer to?
- xz

Technical Documentation
- one vital skill to acquire is to look up official documentation

Linux Manual Pages
- long before the internet was everywhere, how would you get help using a command in a Linux or Unix-like system?
- by checking the manual page! man for short
- on Linux and every Unix-like system each command is expected to have a man page
- in fact man pages also exist for system calls, library functions, and even configuration files

- let's say we want to check the manual page for the command ip
- we issue the command man ip
- you get a manual entry for the command ip!
- if you prefer to read man page of ip in your web browser just type man ip into your search engine

- the attackbox is a Linux system accessible from your browser 
- clicking on the start attackbox wbutton will display the attackbox in a split screen making it convenient to read the task text and apply instructions within the same browser window
- if you hide the attackbox window you can show it again by clicking the blue show split view button at the top

Microsoft Windows
- microsoft provides and official Technical Documentation page for its products
- https://learn.microsoft.com/en-gb/

Product Documentation
- every popular product is expected to have well-organised documentation
- this documentation provides an official and reliable source of info about the product features and functions
- e.g. SNORT Official Documentation, Apache Server Doc, PHP Doc, Node.js Doc
- https://www.snort.org/documents
- https://httpd.apache.org/docs/
- https://www.php.net/manual/en/index.php
- https://nodejs.org/docs/latest/api/

What does the Linux command cat stand for?
- concatenate

What is the netstat parameter in MS Windows that displays the executable associated with each active connection and listening port?
- -b (https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/netstat)

Social Media
- there are billions of users registered on social media platforms such as Facebook, Twitter and LinkedIn
- expected to be familiar with popular platforms
- the power of social media is that it allows you to connect with companies and people you are interested in
- social media offers a wealth of information for cyber security professionals, whether they are searching for people or technical information
- why is searching for people important you ask?
- when protecting a company, you should ensure that the people you protect are not oversharing on social meida
- e.g. their social media might give away the answer to their secret questions!
- such as "which school did you go to as a child?" 
- such information might allow adversaries to reset their passwords and take over their accounts effortlessly

- furthermore as a cyber security professional you want to stay updated with new cyber security trends, technologies, and products
- following the proper channels can provide a suitable environment for growing your technical expertise

- besides staying updated via social media channels and groups, we should mention news outlets!
- hundreds of news websites offer valuable cyber-security related news

You are hired to evaluate the security of a particular company. What is a popular social media website you would use to learn about the technical background of one of their employees?
- LinkedIn

Continuing with the previous scenario, you are trying to find the answer to the secret question, “Which school did you go to as a child?”. What social media website would you consider checking to find the answer to such secret questions?
- facebook
