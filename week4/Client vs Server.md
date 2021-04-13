# Client vs Server

Maryam, Amy, Neville & Saki

---

### What is a client and what is a server? 
- The client is the customer who orders the food and the waiter is the server who checks if they have the food that you ordered.

![](https://media.giphy.com/media/yoJC2j5XUYNuDo51XW/giphy.gif)

---

### What is a web server?

- HARDWARE A web server is a computer that stores web server software and all the website's files.

- SOFTWARE A web server includes several parts that control how web users access hosted files. At a minimum, this is an HTTP server. 

---

### What happens? (part1)

![](https://i.imgur.com/TJa9oHE.png)

1. Client makes a HTTP request to a server, clients must provide the file's URL.
2. A HTTP server first checks if the requested URL matches an existing file

---

### What happens? (part2)

![](https://i.imgur.com/TJa9oHE.png)

3. If so, the web server sends the file content back to the browser.
4. Else it returns an error message. (The server must respond to every HTTP request)


---

### Static V Dynamic

<iframe src="https://giphy.com/embed/kfpJmjbkmIKQicpjAv" width="280" frameBorder="0" class="giphy-embed" allowFullScreen></iframe>

- A static web server (or stack) consists of a computer (hardware) with an HTTP server (software). 
- It is 'static' because the server sends its hosted files as-is to your browser.

---

### Static V Dynamic

<iframe src="https://giphy.com/embed/e3FaCx7T425qg" width="280" frameBorder="0" class="giphy-embed" allowFullScreen></iframe>

- A dynamic web server consists of a static web server PLUS extra software (e.g. application server & a database). 
- It is 'dynamic' because the server updates hosted file templates to generate and return content based on the specific request URL and encoded data.

---

### Dynamic Web Servers

![](https://i.imgur.com/nDX5oyB.png)

---

1. The Browser sends an HTTP GET Request

![](https://i.imgur.com/nDX5oyB.png =550x)
 
- Uses the base URL (e.g /best), encoding additional detail as part of the URL pattern or as parameters:
e.g.    /best/my_team_name/11/
e.g.    /best?team=my_team_name&show=11

---

2. The Web Server forwards 'dynamic' Request to the Web Application for processing. 

![](https://i.imgur.com/nDX5oyB.png =550x)

- The web server determines how to handle different URLs based on pattern matching rules in it's configuration

---

3. The Web Application then gets the required information from the database 

![](https://i.imgur.com/nDX5oyB.png =550x)

- The Web Application first identifies that the request is to get the "best team list" based on the URL (/best/).
- It finds out the required team name and number of players from the URL.

---

4. The Web Application dynamically creates an HTML page by putting the data into placeholders inside an HTML template from the File System.

![](https://i.imgur.com/nDX5oyB.png =550x)

5. The Web Application returns the generated HTML to the web browser (via the Web Server), along with an HTTP status code.

---

6. The Web Browser starts to process the returned HTML, sending separate requests to get any other CSS or JavaScript files referenced.

![](https://i.imgur.com/nDX5oyB.png =550x)

7. The Web Server loads static files from the File System and returns them to the browser directly 
(Again, correct file handling is based on configuration rules and URL pattern matching).

---


### Can something be both a client and a server?

In short, yes. 

![](https://i.imgur.com/8SMPdp0.gif)


---

### The longer answer:

Most people think of clients and servers as two separate things, hosted on separate hardware, as this is easier to imagine and is often the case! **But** it is possible for the two to reside in the same machine, rather than communicating via a computer network.

---

This can be the case if acting as the server for one app and client for another totally separate app. For example, while we are working on our servers on our laptops, we are googling a lot of questions as the client (...or maybe that's just me). 

![](https://i.imgur.com/WrPwidO.gif)


---


It can also apply when the two are related, or even the same. An example is proxy servers:

![](https://i.imgur.com/2XTZddG.png)


---

### What kind of code should be run on a server instead of a browser?

---

### server side programming languages
![](https://i.imgur.com/8bgZ8fg.jpg)

---

### popularity towards Node.js
![](https://i.imgur.com/RyUbt2l.gif)

---

![](https://i.imgur.com/EHbqEhh.jpg)


---

### common uses and benefits of server-side programming
![](https://i.imgur.com/ANVbZ5F.jpg)

---

### Efficient storage and delivery of information

![](https://i.imgur.com/Hm4vdY6.gif)

---
### Customised user experience
![](https://i.imgur.com/vJZmSc5.png)

---
### Controlled access to content
![](https://i.imgur.com/UA37Lva.jpg)


---
### Store session/state information
![](https://i.imgur.com/pTDWV6L.jpg)


---
### Notifications and communication

![](https://i.imgur.com/xnqGA4O.jpg)

---
### Data analysis

![](https://i.imgur.com/5m9kRLF.gif)



