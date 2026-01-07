What is HTTP (HyperText Transfer Protocol)
- what is used whenever you view a website, developed by Tim Berners-Lee and his team between 1989-1991
- HTTP is the set of rules used for communicating with web servers for the transmitting of webpage data, whether that is HTML, images, videos etc.

What is HTTPS (HyperText Transfer Protocol Secure)
- the secure version of HTTP
- HTTPS data is encrypted so it not only stops people from seeing the data you are sending and receiving but also gives you assurance that you are talking to the correct web server and not something impersonating it

What does HTTP stand for?
- HyperText Transfer Protocol

What does the S in HTTPS stand for?
- secure

On the mock webpage on the right there is an issue, once you've found it, click on it. What is the challenge flag?
- THM{INVALID_HTTP_CERT}

Requests & Responses
- when accessing a website -> browser needs to make requests to a web server for assets such as HTML, images and download the response
- before that you need to tell the browser specifically how and where to access these resources -> where URLs will help

What is a URL? (Uniform Resource Locator)
- predominantly an instruction on how to access a resource on the internet
http://user:password@tryhackme.com:80/view-room?id=1#task3
http - scheme
user:password - user
tryhackme.com - host/domain
:80 - port
view-room - path
?id=1 - query string
#task3 - fragment

![url_example](url_example.png "url_example")

scheme - instructs on what protocol to use for accessing the resource such as HTTP, HTTPS, FTP
user - some services require auth to login you can put a username and password into the url to log in
host - the domain name or IP addr of the server you with to access
port - the port you are going to connect to, usually 80 for HTTP and 443 for HTTPS but this can be hosted on any port between 1 - 65535
path - the file name or location of the resource you are trying to access
query string - extra bits of info that can be sent tot he requested path e.g. /blog?id=1 would tell the blog path you wish to receive the blog article with the id of 1
fragment - this is a reference to a location on the actual page requested -> commonly used for pages with long content and can have a certain part of the page directly linked to it, so it is viewable to the user as soon as they access the page

Making a request
- possible to make a reuqest to a web server with just one line GET / HTTP/1.1
- but for much richer web experience you need to send other data as well
- the other data is sent in what is called headers
- headers contain extyra info to give to the web server you are communicating with

![making_a_request_example](making_a_request_example.png "making_a_request_example")

example request
GET / HTTP/1.1
Host: tryhackme.com
User-Agent: Mozilla/5.0 Firefox/87.0
Referer: https://tryhackme.com/

Line 1 - request is sending the GET method, request the home page with / and telling the web server we are using HTTP protocol version 1.1
Line 2 - we tell the web server we want the website tryhackme.com
Line 3 - we tell the web server we are using the firefox version 87 browser
Line 4 - we are telling the web server that the web page that referrred us to this one is https://tryhackme.com
Line 5 - HTTP requests always end with a blank line to inform the web server that the request has finished

example response

![example_response](example_response.png "example_response")

Line 1 - HTTP 1.1 is the version of the HTTP protocol the server is using and then followed by the HTTP status code in this case "200 OK" which tells us the request has completed successfully
Line 2 - this tells uis the web server software and version num
Line 3 - the current date, time and timezone of the web server
Line 4 - the content-type header tells the client what sort of information is going to be sent, such as HTMl, images, videos, pdf, XML
Line 5 - content-length tells the client how long the response is, this way we can confirm no data is missing
Line 6 - HTTP response contains a blank line to confirm the end of the HTTP response
Lines 7-14 - the information that has been requested in this instance the homepage

What HTTP protocol is being used in the above example?
- HTTP/1.1

What response header tells the browser how much data to expect?
- Content-Length

HTTP Methods
- a way for the client to show their intended action when making a HTTP Request
- lots of HTTP methods
- common ones -> mostly deal with GET and POST method

GET Request
- used for getting info from a web server

POST Request
- used for submitting data to the web server and potentially creating new records

PUT Request
- used for submitting data to a web server to update information

DELETE Request
- used for deleting information/records from a web server

What method would be used to create a new user account?
- POST

What method would be used to update your email address?
- PUT

What method would be used to remove a picture you've uploaded to your account?
- DELETE

What method would be used to view a news article?
- GET

HTTP status codes

5 different ranges
100-199 Inforamtion response - these are sent to tell the client the first part of their request has been accepted and they should continue sending the rest of their request. these codes are no longer very common

200-299 success - this range of status codes is used to tell the client their request was successful

300-399 redirection - used to redirect the clients request to another resource, can be either to a different webpage or different website altogether

400-499 client errors - used to inform the client that there was an error with their request

500-599 server errors - reserved for errors happening on the server-side and usually indicate quite a major problem with the server handling the request

Common HTTP status codes

200 OK - request was completed successfully
201 Created - resource has been created (e.g. new user)
301 Moved Permanently - redirects the clients browser to a new webpage or tells search engines that the page has moved somewhere else and to look there instead
302 Found - similar to the above permanent redirect, but this is only a temporary change and it may change again in the near future
400 Bad Request - tells the browser that somwething was either wrong or missing in their request. could sometimes be used if the web server resource that is being requested expected a certain parameter that the client didnt sent
401 Not Authorised - you are not currently allowed to view this resource until you have authorised with the web application, most commonly with a username and password
403 Forbidden - you do not have permission to view this resource whether you are logged in or not
405 Method Not allowed - the resource does not allow this method request e.g. you send a GET request to the resource /create-account when it was expecting a POST request
404 Page Not Found - the page/resource requested does not exist
500 Internal Service Error - server has encountered some kind of error with your request that it doesnt know how to handle properly
503 Service Unavailable - server cannot handle your request as its either overloaded or down for maintenance

What response code might you receive if you've created a new user or blog post article?
- 201

What response code might you receive if you've tried to access a page that doesn't exist?
- 404

What response code might you receive if the web server cannot access its database and the application crashes?
- 503

What response code might you receive if you try to edit your profile without logging in first?
- 401

Headers
- addiotnal bits of data you can send to the web server when making requests
- no headers are strictly required when making a HTTP request, you will find it difficult to view a website properly

Common Request Headers
- headers that are sent from the client (usually your browser) to the server
- Host: some web servers host multiple websites so by providing the host headers you can tell it which ones you  require, otherwise you will just receive the default website for the server
- User-Agent: this is your browser software and version num, telling the web server your browser helps it format the website properly and also some elements of HTML, JavaScript and CSS are only available to certain browsers
- Content-Length: when sending data to a web server such as in a form, the content-length tells the web server how much data to expect in the web request. this way the server can ensure it isnt missing any data
- Accept-Encoding: tells the web server what types of compression methods the browser supports so the data can be made smaller for transmitting over the internet

Common Response Headers
- headers thatr are returned to the client from the server after a request
- Set-Cookie: information to store which gets sent back to the web server on each request
- Cache-Control: how long to store the content of the response in the browser's cache before it requests it again
- Content-Type: tells the client what type of data is being returned e.g. HTML, CSS, JavaScript, Images, PDF. Using the content-type header the brwoser then knows how to process the data
- Content-Encoding: what method has been used to compress the data to make it smaller when sending it over the internet

What header tells the web server what browser is being used?
- User-agent

What header tells the browser what type of data is being returned?
- Content-Type

What header tells the web server which website is being requested?
- Host

Cookies
- small piece of data that is stored on your computers
- saved when you receive a "set-cookie" header from a web server
- then every further request you make, you'll send the cookie data back to the web server
- because HTTP is stateless (doesn't keep track of your previous requests) -> cookies can be used to remind the web server who you are, some personal settings for the website or whether you've been to the website before

Example HTTP request
![htttp request](HTTP_request.png "http request")

- cookies can be used for many purposes 
- most commonly used for website auth
- cookie value wont usually be a clear-text string where you can see the password -> instead a token (unique secret code that isnt easily humanly guessable)

viewing Your Cookies

- you can easily view what cookies your browser is sending to a website by using the developer tools, in your browser. If you're not sure how to get to the developer tools in your browser, click on the "View Site" button at the top of this task for a how-to guide.

- once you have developer tools open, click on the "Network" tab. This tab will show you a list of all the resources your browser has requested. You can click on each one to receive a detailed breakdown of the request and response. If your browser sent a cookie, you will see these on the "Cookies" tab of the request.

Which header is used to save cookies to your computer?
- Set-Cookie

Making Request
- pratical task

Make a GET request to /room page
- THM{YOU'RE_IN_THE_ROOM}

Make a GET request to /blog page and set the id parameter to 1
- THM{YOU_FOUND_THE_BLOG}

Make a DELETE request to /user/1 page
- THM{USER_IS_DELETED}

Make a PUT request to /user/2 page with the username parameter set to admin
- THM{USER_HAS_UPDATED}

Make a POST request to /login page with the username of thm and a password of letmein
- THM{HTTP_REQUEST_MASTER}

![practical_example](practical_example.png "practical_example")