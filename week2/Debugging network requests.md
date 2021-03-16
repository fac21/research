# Debugging network requests 

---

## Mariya & Rosie worked on:

## How can we inspect any requests the browser is making on an HTML page?

---

We can Inspect Network Activity In Chrome DevTools by using the **Network panel**.

In general, we can use the Network panel when we need to make sure that resources are being downloaded or uploaded as expected. 

---

The most common use cases for the Network panel are:

- Making sure that resources are actually being uploaded or downloaded at all.
- Inspecting the properties of an individual resource, such as its HTTP headers, content, size, and so on.

---

##### Using Network Tools
1. We can open the Network panel in the **DevTools**

2. Click the **Network** tab.

![](https://media.giphy.com/media/f5LNjbDbSA0Q8Y28ev/giphy.gif)



---

![](https://i.imgur.com/H3rBUdm.png)

3. Reload the page and explore

---

![](https://i.imgur.com/ioFZ5CZ.jpg)
###### What we see on this panel is the set of all requests that were generated in order to render what we see on the screen in front of us. This is the network view, commonly referred to as a *waterfall chart*, and it's helpful for understanding how fast a website loads.

---

![](https://i.imgur.com/ioFZ5CZ.jpg)
###### We can see name, status, type, initiator, size, time and waterfall. We can also inspect other things. If you right click on the name column you will be given a list of other columns which will now be displayed. 


---

![](https://i.imgur.com/usuwS2M.jpg)
- the request’s URL, as well as the 
- request method (usually GET or POST) and 
- all the Request Headers the browser automatically sent along with the request, including cookies.

---

##### Every average website requires hundreds of HTTP requests to load not just the HTML but also all the CSS, Javascript, images, and API data it needs to render properly.

##### If you click on online in the top right, you can change the processing speed to you can how your page will function in a slower internet speed.

![](https://i.imgur.com/fqoc4WL.png)

---

##### We can filter to find all CSS requests, all Javascript requests, etc or we can use the filter search bar for look for a more specific request.
![](https://i.imgur.com/jwxTfW3.png)

---

##### We can inspect:
##### The header tab - to inspect HTTP headers
##### A preview of the request - if it's in HTML format we'll see what it looks like on the page, or if not, we'll see the code. *This tab is helpful when an API returns an error code in HTML and it's easier to read the rendered HTML than the HTML source code, or when inspecting images.*
##### The response - this shows the HTML response.
##### Timing - this shows timing of the request.

---
Issues

##### We can use these tools to find and solve issues

https://developers.google.com/web/tools/chrome-devtools/issues


![](https://i.imgur.com/OdQrV6L.jpg)


---

## Amy and Nafisa worked on:

## How can we manually send test requests outside of our browser?

- We struggled
- A lot.

---

## 2 main ways: 

 1) In terminal (cURL, httpie) - ugly UI, difficult for humans to read
 2) External apps/software - extra apps to install, much nicer UI

---

## cURL:

 - cUrl stands for client URL 
 
 - its a command line tool that developers use to transfer data to and from a server by making network requests.

---

![](https://i.imgur.com/9cIyTeE.png)


---

The previous slide is an example of a HTTP GET request, what displayed was the html code response of the google server.


Curl will use the HTTP protocol by default. So if i were to run curl http://www.google.com instead of google.com i'd get the same response in the terminal.

---

It also supports a lot of different protcols e.g. FTP, FILE and IMAP. This means it can transfer a lot of different data.

Instead of receiving a response you can also send data to a server to create or update a resource by a POST request. One example is when a user uploads a profile photo.

---

Apart from making HTTP requests curl can also be used for testing API's.

curl is generally used by developers who are more comfortable with working in the terminal. The external apps are easier to use because theyre more visual.

---

## External Apps/Software

### Most popular options for basic HTTP requests 

 - Postman
 - Insomnia
 - ARC

These have to either be installed, or added as extensions to the browser. Postman and Insomnia are open source but ARC isn't.

---

There are other options that can do other things like generate reports and run scripts, but these are the most commonly used options for simple HTTP requests. ARC has the most options out of these three.

---

### Insomnia

The Insomnia app makes interacting with and designing HTTP-based APIs easier.


![](https://i.imgur.com/7ZXiaAS.png)


---


![](https://i.imgur.com/CBTXzcD.png)


---

### Postman

![](https://i.imgur.com/6K8AbCR.png)

---

Postman has a simple UI - you can just click and select the command you want

---

![](https://i.imgur.com/BuuY8OQ.png)

Then next to it you enter the url

---

![](https://i.imgur.com/F2ZTVKp.png)

You can select the formatting style you'd like

---

## Thank you for watching!
