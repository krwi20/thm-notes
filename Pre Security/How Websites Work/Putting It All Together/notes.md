To summarise 
- when you req a website -> your computer needs to know the servers IP addr it needs to talk to -> for this it uses DNS
- your computer then talks to the web server using a special set of commands called the HTTP Protocol
- the webserver then returns HTML, js, CSS, images etc
- which your browser then uses to correctly format and siaply the website to you
- there are also a few other components that help the web run more efficiently and provide extra features.

Load Balancers
- when a websites traffic starts getting quite large or is running an application that needs to have high availability
- one web server might no longer do the job
- load balancers provide two main features
- ensuring high traffic websites can handle the load providing a failover if a server becomes unresponsive
- when you request a website with a load balancer -> load balancer recevives request -> forwards it to one of the multiple servers behind it
- load balancer uses different algorithms to help it decide which server is best to deal with the req
- couple examples of these algorithms are round-robin, which sends it to each server in turn
- or weighted, which checks how many reqs a server is currently dealing with and sends it to the least busy server

- load balancers also perform periodic checks with each server to ensure they are running correctly -> known as health check
- if a server does not respond appropriately or doesnt respond, the load balancer will stop sending traffic until it responds appropriately again

![load_balancer_example](images/load_balancer_example.png "load_balancer_example")

CND (Content Delivery Networks)
- can be an excellent resource for cutting down traffic to a busy website
- allows you to host static files from your website such as JS, CSS, Images and host them across thousands of servers all over the world
- when a user reqs one of the hosted files, the CDN works out where the nearest server is physically located and sends the req there instead of potentially the other side of the world

Databases
- often websites will need a way of storing info for their users
- webservers can communicate with databases to store and recall data from them
- databases can range from just a simple plain text file up to complex clusters of multiple servers providing speed and resilience
- youll come across some common databases: MySQL, MSSQL, MongoDB, Postgres and more

WAF (Web Application Firewall)
- a WAF sits between your web req and the web server
- primary purpose -> protect the webserver from hacking or denial of service attacks
- analyses the web reqs for common attack techniques
- wether its from a real browser rather than a bot
- also cehcks if an excessive amount of web reqs are being sent by utilising something called limit rating
- limit rating -> only allow a certain amount of reqs from an IP per second
- if a req is deemed a potential attack, it will be dropped and never sent to the webserver

![waf_example](images/waf_example.png "waf_example")

What can be used to host static files and speed up a clients visit to a website?
- CDN

What does a load balancer perform to make sure a host is still alive?
- health check

What can be used to help against the hacking of a website?
- WAF

How Web Server work
- web server -> software that listens for incoming connections -> utilises HTTP protocol to deliver web content to its clients
- most common web server software youll come across is Apache, Nginx, IIS, and NodeJs
- web server delivers files from whats called its root directory, defined in the software settings
- e.g. Nginx and Apache share the same default location of /var/www/html in Linux os and IIS uses C:\inetpub\wwwroot for the windows os
- e.g. if you req the file http://example.com/picture.jpg  it would send the file /var/www/html/picture.jpg from its local hard drive

Virtual Hosts
- web servers can host multiple websites with different domain names, to achieve this they use virtual hosts
- the web server software checks the hostname being requested from the HTTP headers and matches that against ist virtual hosts
- virtual hosts are just text-based config files
- if it finds a match, correct website will be provided
- no match -> default website will be provided instead

- virtual hosts can have their root directory mapped to different locations on the hard drive
- e.g. one.com being mapped to /var/www/website_one and two.com being mapped to /var/www/website_two

Static vs Dyanmic Content
- static content -> content that never changes
- common examples are pictures, js, css
- can include HTML that never changes
- these are files that are directly served from the webserver with no changes made to them

- dyanmic content -> content that could change with different reqs
- e.g. a blog, on the homepage of the blog it will show you the latest entries
- if a new entry is created the home page is then updated with the last entry

- these changes to what you end up seeing are done in whats called the backend with the use of programming and scripting languages
- called the backend because whats being does is behind the scenes
- you cant view the HTML src and see what is happening in the backend, while the HTML is the result of the processing from the backend
- everything you see in the browser is called the frontend

Scripting and Backend Languages
- not much of a limit to what a backend lang can achieve
- these are what make a website interactive to the user 
- e.g. languages - PHP, Python, Ruby, NodeJS, Perl etc
- these langs can interact with databases, call external services, process data from the user and more
- basic php example of this would be if you requested http://example.com/index.php?name=adam
- if index.php was built like this:
- `<html><body>Hello <?php echo $_GET["name"]; ?></body></html>`
- it would output the following to the client:
- `<html><body>Hello adam</body></html>`
- youll notice the client doesnt see any php code because its on the backend
- this interactivity opens up a lot more security issues for web applications that havent been created securely

What does web server software use to host multiple sites?
- Virtual Hosts

What is the name for the type of content that can change?
- Dynamic

Does the client see the backend code? Yay/Nay
- Nay

Quiz

![quiz_part_1](images/quiz_part_1.png "quiz_part_1")

![quiz_part_2](images/quiz_part_2.png "quiz_part_2")

Flag
- THM{YOU_GOT_THE_ORDER}