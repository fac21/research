# Browser Storage

Nafisa, Jo, Chun & Saki 

---

Three main ways to store data inside of our browser: localStorage, sessionStorage, and cookies.

![](https://i.imgur.com/Ev2GAaU.png)


---

## Cookies

![](https://media.giphy.com/media/mXrDi0oEBNvUI/giphy.gif)


---


Cookies are quite different from Session Storage and Local Storage :cookie: :cookie: :cookie:
- Been around for longer, since 1994
- Expiration: You have control to set it
- Stored in browser but the cookie is sent back and forth to the server with every HTTP request (it can slow it down)
- Small: They hold only a very small amount of data, with a max capacity of 4KB
- Type of data: Strings


---


### What to use Cookies for?

- To validate users’ identities after they’ve logged in to prevent them from having to re-enter their credentials on every page. 

- To customize or adjust user experience based on limited browsing history on the site.

- Record stateful elements like shopping cart items or options changed by a user. 

- Remember user browsing habits 


---
 


---

### Expiration: You choose
 
 - Session cookies: no expiration date.  They're stored only as long as the browser/tab is open. 

 - Persistent cookies. Stored until the expiration date and then deleted. 

<img src="https://media.giphy.com/media/3orif6HDXFrRY49dra/giphy-downsized.gif" style="height: 200px; margin: 0 auto;">



---

### Security

 - Cookies can be trivially tampered with by the user, and data can also be read from them in plain text

- Offers a degree of protection: 
1. HTTP only flag
2. The Same-Site option
3. The Secure Option


---

## Local Storage

LocalStorage introduced after HTML5.

Lightweight solution for data storage that doesn’t involve databases or even the server.

Replaced many uses of cookies - does not require data to be sent back and forth with every HTTP request, reducing traffic between client and server, no wasted bandwidth). 

---

Instead, data stored on local disk, not affected by loss of internet connection.

Data not automatically destroyed unless cleared through Javascript code. 

Can store objects, as well as strings.

Can hold larger amounts of data than cookies.

---

## Good uses of LocalStorage

Data that would be convenient for the user to see even if the browser was refreshed:
* Forms save a user's input in LocalStorage until it is submitted.
* Static websites commonly use LocalStorage to store user preferences, like a UI theme.

Also: apps used in areas without a persistent internet connection. 

---

## Security

Local storage shares many of the same characteristics as a cookie, including the same security risks. 

Storing a password in a local storage file actually simplifies the process for a hacker, because they won’t need to load the cookie into their own browser.

Should not store sensitive user or app data in LocalStorage.

---

## Where local storage is stored

Information is saved as key value pairs in the `localStorage` property in the Web Storage API object.

In Google Chrome, web storage data is saved in an SQLite file in a subfolder in the user’s profile. 

---

Windows
`\AppData\Local\Google\Chrome\User Data\Default\Local Storage`  

macOS
`~/Library/Application Support/Google/Chrome/Default/Local Storage`

---

## Session Storage
Session storage is a lot like local storage, with one exception. Instead of saving the data on your local hard drive it is saved in your browser and cleared when a tab/window is closed.

---

Both storage objects are domain and protocol specific.

Session storage is more limited than local storage but some advantages it has over cookies are:

- Storage limit is large (at most 5MB).

- the server can’t manipulate storage objects via HTTP headers. Everything’s done in JavaScript.

- Faster page loads


---

### Security

It isn’t something that you should use for any sensitive data because it can be vulnerable to XSS attacks (injects malicious scripts into web applications)


---


### What can it be used for?

- Things you only want the user to see once per login, like a news popup. You could store that they've seen it already in sessionStorage.

- User settings that are needed on every page, like a special layout, could be loaded once and put into sessionStorage for easy access.

- Maintaining the same volume across tabs


---


![](https://i.imgur.com/Ev2GAaU.png)


---


## Where can we see what a web page has stored in our browser?


---

### Chrome: 

![](https://i.imgur.com/RFqodQW.png)

---

### Firefox:

![](https://i.imgur.com/xgQSNA3.png)


---

### In-depth look at what's in the storage inspector: 
 
 ![](https://i.imgur.com/T69HfX2.jpg)

http://www.devdoc.net/web/developer.mozilla.org/en-US/docs/Tools/Storage_Inspector.html

---

![](https://i.imgur.com/oFPy9LF.png)


---

![](https://i.imgur.com/PrR0Gnv.png)


---

![](https://i.imgur.com/jc2JcXi.png)


---

Most modern browsers support **'Incognito' or 'Private' browsing** which doesn't store data like history and cookies.

![](https://i.imgur.com/DaS6hLj.png)

Most browsers allow storage APIs to still be available and functional, except **all stored data is wiped after the browser is closed**. 

---

## Local storage demo:

https://mdn.github.io/dom-examples/web-storage/


---

Useful Resources 
- http://diveintohtml5.info/storage.html
- https://blog.logrocket.com/localstorage-javascript-complete-guide/