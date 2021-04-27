## Authentication

---

<img src="https://media.giphy.com/media/wKKnvfqzNOzo3Q3TwY/giphy.gif" height=250>  

Authentication is a process that exists in almost every application to distinguish between users while the client and server communicate.

---

<img src="https://media.giphy.com/media/3og0IuymsB9sy0C2Vq/giphy.gif" height=250>

The application needs to ensure credentials are correct in order to generate or access the relevant data for this user.

---

<img src="https://media.giphy.com/media/Qbt9STC0qpSuc/giphy.gif" height=250>

To access the application as an identified client, you will generally be using either Stateless (token) or Stateful (session) authentication.

---

# HTTP

- HTTP is what enables communication between a client and a server. 

- HTTP is stateless so each request made is totally unaware of any action taken previously. 

---

<img src="https://media.giphy.com/media/U4YEoSRgz5JtebnYqH/giphy.gif" height=250>

When navigating between pages we would need to re-enter any information, because the server would have no idea that we were already logged in. 

BUT, with session and token authentication we can tell the server that we are already logged in and we should still be granted access to that page.

---

# But why do we still use both?

---

<img src="https://media.giphy.com/media/OeQjrN7ef3KBFZieQu/giphy.gif" height="250">

- Security (session info could be stolen or compromised)
- Storage (resource consumption and token size)
- Difficulty (ease of implementation and scaling)
- Management (ability to revoke a session or modify session data)

---

# MARYAM <3
What is session-based (stateful) authentication?

---

#### This type of authentication is called stateful because sessions are stored on the server-side
![](https://i.imgur.com/5WsEgIW.gif)


---

![](https://i.imgur.com/YmEclCE.png)


---

User make a POST request to send his login and password.
Server verifies the credentials from the database.
Server stores session data in the memory, cache, or DB.
Sever issues a cookie with a session ID.
User sends the cookie along with each request.
Server verifies the user identity using session id.
When the user logs out the session will be destroyed and the server clears the cookie.

---

 #### During the opened session the hackers may find a leak on system and get a lot of data
![](https://i.imgur.com/0K71nL9.gif)

---

Session based authentication is still used in a lot of websites, which do not hold important data for the users instead others use token based authentication for a better security which will be described 
![](https://i.imgur.com/TTGxPqQ.png)

---

##### useful links
https://roadmap.sh/guides/session-authentication
https://www.mohamed-elhamra.me/posts/session-vs-token-based-authentication/
https://www.researchgate.net/publication/320068250_Token-Based_vs_Session-Based_Authentication_A_survey


---

# SEVDA <3
## What is token-based (stateless) authentication?

---

Token-based authentication is just one of many web authentication methods used to create a more secure verification process.

That means even if an attacker successfully implements a brute force attack to take out any password in place, they’ll have to also bypass the token authentication layer. 

---

## Nice try :smiley: 

<img src="https://i.imgur.com/TA6ad2g.png" alt="ninja" width="500px">

---

The core responsibility of the token is to store and communicate credentials. It is a 'string' that server generates for the client and can be passed along inside an HTTP request.

![](https://i.imgur.com/KdyOpt1.png)

---

### A typical example of how the token is sent with the header to the server

<img src="https://i.imgur.com/NxAhn6E.png" alt="ninja" width="500px">

The main difference here is that nothing is stored in the server. The server doesn't store the user, nothing actually happens on the server.

---

![](https://i.imgur.com/r20LBHR.png)

---

The JWT token has all the information about the user build into it. 
It is send back to the browser and the browser can choose to store it however it wants. For example, it can do cookie storage and would work as same as session-based. Then the client is going to send a request to the server by ensuring JWT is included. So it knows what the user was authenticated with. 
The server then signs that JWT token with its own secret key which varifies that this JWT has not been changed since the time assigned it. 

---

Plenty of websites use access tokens. For example, if you've ever used credentials from one website (like Facebook) to gain entry to another website (like Salesforce), you've used an access token.

---

Tokens are usually given out with an expiration time after which they become invalid and a new token needs to be obtained. 

<img src="https://i.imgur.com/sNj4qwd.png" alt="Exporation tokens" width="500px">

---

# CHISHA :thinking_face: 

![](https://media1.giphy.com/media/xU6wa2sHzhse00w4hr/giphy.gif)

---

In a **Stateless application**, ==different servers can be used to process different information==.

In a **Stateful application**, ==only one server is used to process all requests that are linked to the same state information==.


---

### Other differences between Stateless and Stateful applications include:

- **State of working**: Stateful Applications react by the current state, while Stateless applications act independently when taking into consideration previous or next requests.

- **Stored Data**: Stateful webserver stores data in a backend and uses it to identify the user as an always-connected client. In Stateless, the server stores data in a database to verify user/client whenever it needs to connect.

--- 

- **Reaction toward Clients**: In Stateful, the server thinks a client is just a dumb machine, while in Stateless, server thinks the client is an intelligent machine that doesn’t need to depend on any state on the server-side.

- **Requests**: In Stateless, everything is contained within the request, and handled in two distinct phases, a “request” and “response.” While in Stateful, requests are always dependant on the server-side state.

---

- **Generated State**: The state is generated and stored somewhere in internet browsing in both types however the state stored on the server is a Stateful application.

- **State Stored**: State stored by the client generates some data used for further requests which is Stateful, but the state stored by the client is Stateless.

---

- **Cookie Stores**: On the client-side, cookie stores authentication data. On the server-side, cookies create temporary client data or stores on a database. 

- **User Base**: Stateful is considerd past when there were no dynamic user base. Stateless is considered future, having Microservices floating around and mostly communicating through REST interfaces.


---


### What are the Advantages vs Disadvantages of Stateful and Stateless

---


![](https://i.imgur.com/G9VdB9y.png)

---


![](https://i.imgur.com/PVPCUug.png)

---

![](https://i.imgur.com/4Oc6IY1.png)

--- 

**Conclusion**: Both approaches have advantages and disadvantages. **Stateless** authentication ==easier to implement and scale==, but **Stateful** authentication is ==more secure and easier to manage==.

---

![](https://i.pinimg.com/originals/a7/7a/ea/a77aeada41b9c4064e2f6c17fd2bd211.gif)
