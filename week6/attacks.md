### Attacks
![](https://media.giphy.com/media/kclLv81HWVncxFGsdR/giphy.gif)
Evgeny, Mariya, Neville & Safia

---

How might our websites be vulnerable to hacking?

- Cross Site Scripting (XSS)

- Cross Site Request Forgery (CSRF)


---

### Cross Site Scripting (XSS)
<!-- Safia -->
**DANGER** - The attacker sneaks some malicious JavaScript (usually via a `<script>` tag) into your html which is then executed.

...bascially a HTML Injection Attack.

---

### How does this HTML Injection Attack work in practice?

We’re fetching the `name` url param and injecting it into the index.ejs template.

![](https://i.imgur.com/OjtMjLD.png)
Route handler for the `/` route

---

![](https://i.imgur.com/F5yuVE4.png)

![](https://i.imgur.com/LtRkW4C.png)

---

So far so good. Nothing fishy going on here. Now let’s try to insert a `<script>` tag into the url:

---

![](https://i.imgur.com/PCfrvHq.png)

XSS attack shown in Firefox. :shocked_face_with_exploding_head: 

---

### How can this attack hurt me? :worried: 

Get access to your bank account.
1. You’d receive an email with instructions to log into your bank.
2. After login, you’re instructed to click on this link `https://yourBankWebsite.com/account?id=<script>[maliciousCodeHere]</script>`
<!-- There is a cookie stored in your computer that has the bank's website servers session information (token) which the  -->
3. The `maliciousCodeHere` will run, and could send your session token to the hacker.

---

4. In theory hacker could create a cookie on their computer and store your session information in it.


- If that session is still active, they can visit your banks website, and they’ll be logged in as you, and can browse around, look at bank account information, and possibly even initiate a transfer or change your password.

![](https://media.giphy.com/media/damUMYvgrroqw2hxSu/giphy.gif)

---

### Types of XSS Attacks

- Reflected (non-persistent)
- Stored (persistent)
- DOM
- Mutation 

![](https://i.imgur.com/GUZ8cZn.png)


---

### Summary

Cross site scripting (XSS) attacks are usually about injecting unsafe JS into the HTML (often via the URL) in order to get a victim to run that malicious JS in their browser to steal info they have access to because they’ve logged in.

---

***How can you defend against XSS attacks??***

![](https://media.giphy.com/media/YQitE4YNQNahy/giphy.gif)

---

***Treat any user input as unsafe***

* We need to sanitize any user-provided values 
* There are a number of libraries that do that for you
* In general you should sanitize on the server

![](https://media.giphy.com/media/o0vwzuFwCGAFO/giphy.gif)

---

***Sanitizing at the templating layer***

Most templating languages have built in support for this. 

In Embedded Javascript, you use `<%= name %> `by default because it sanitizes by encoding any html tags, so any `<script>` tag will show up as `&lt;script&gt;` in the html and `<script>` tag on the webpage. 

---

This means it’ll be rendered and not executed.

If you have your own templating solution or use es6 template strings, you should sanitize your user values via some XSS library. 

---

***Sanitizing at the storage layer***

If you are saving any values to a database (URL names, or user names, or emails) that will be displayed to the user, this is a prime location for an HTML injection attack. 

---

If I can store `<script>[maliciousCode]</script>` as my display name for a social site, then anybody else who sees my name could potentially run my code in their browser and I can steal their credentials. 

Sanitizing before you save any values from user input is a must.

---

***Sanitizing at the url param layer***

You could add some middleware that sanitizes all the route parameters.


---

<!-- Neville -->
### Cross Site Request Forgery (CSRF)
AKA 'one-click attack' / 'session-riding'

<iframe src="https://giphy.com/embed/3orif7rKeCocZnqWl2" width="480" height="362" frameBorder="0" class="giphy-embed" allowFullScreen></iframe>


---

### What is Cross Site Request Forgery (CSRF)

A technique that allows hackers to carry out an unwanted actions on a victims behalf.

Unlike cross-site scripting (XSS), which exploits the trust a user has for a particular site, CSRF exploits the trust that a site has in a user's browser.

---

There are many ways in which a malicious website can transmit such commands, e.g :
- specially-crafted image tags, 
- hidden forms 
- JavaScript XMLHttpRequests

:warning: All can all work without the user's interaction or even knowledge. 

---

### RECAP: How does a website know it's me?

Browser that you are using stores session cookies when you log into a website

The session cookies are sent every time you communicate with the site

This allows you to access your confidential information and perform actions specific to you

---

### SIMPLIFIED EXAMPLE: Submitting a form ...

```HTML 
<form method='POST' action='https://twitter.com/send_tweet'>
    <input type="text" name='tweet_content'
    value='@founderscoders rocks!'>
    <input type='submit' value='Send Tweet'>
<form>

```

**_Disclaimer :wink:: Twitter is not actually vulnerable in this way (I think!)_**

---

### How can this hurt me? :worried: 

- A rouge site, not just twitter, could host the same simple HTML form 

- This could be used to POST requests to twitter, including content of the rogue sites choosing


```HTML 
<form method='POST' action='https://twitter.com/send_tweet'>
    <input type="text" name='tweet_content'
    value='Follow @bootcampEvil on Twitter!'>
    <input type='submit' value='Submit'>
<form>

```

---

### Why would I send such a thing!?! :astonished:

When hosting a similar form, an attacker could make the form **_hidden_** & **_autosubmitted_**



```html
<iframe style='display:none" name="csrf-frame"></iframe>

<form method='POST' action='https://twitter.com/send_tweet' target="csrf-frame" id="csrf-form">
    <input type="text" name='tweet_content'
    value='Follow @bootcampEvil on Twitter!'>
    <input type='submit' value='Submit'>
<form>

<script>document.getElementById("csrf-form").submit()</script>
```

- iframe tag added to target and style the form element 
- script tag added to auto submit the form

---

## How to protect yourself against CSRF attacks?


<iframe src="https://giphy.com/embed/xThtan59KDMX1lPTMI" width="480" height="360" frameBorder="0" class="giphy-embed" allowFullScreen></iframe>

---

### What the users can do to minimise the risk of CSRF? :muscle:


- Log out of sites after using them: leaving no session or valid cookie to exploit

- Use a different browser for sensitive sites (e.g. banking) and casual browsing: If you casually browse to a CSRF site, it won't have access to credentials held on another browser.

- Use a Javascript blocker: By disabling JS you prevent the auto submit functionality on the form from running

---

### What the developers can do to protect their websites?
<!-- Mariya -->
---

```html
<form action="https://my.site.com/me/something-destructive" method="POST">
  <button type="submit">Click here for free money!</button>
</form>
```
<!--As Neville said  -->
On their own (phishing site), an attacker could create a form that creates a request against your site.

---

### Use only JSON APIs
AJAX calls use JavaScript and are CORS-restricted. There is no way for a simple ```<form>``` to send JSON, so by accepting only JSON, you eliminate the possibility of the above form.

---

### Disable CORS
The first way to mitigate CSRF attacks is to disable cross-origin requests. If you're going to allow CORS, only allow it on OPTIONS, HEAD, GET as they are not supposed to have side-effects.

Unfortunately, this does not block the above request as it does not use JavaScript (so CORS is not applicable).

---

### Check the referrer header
Unfortunately, checking the referrer header is a pain in the ass, but you could always block requests whose referrer headers are not from your site. This really isn't worth the trouble.

For example, you could not load sessions if the referrer header is not your server.

---

### GET should not have side effects
Make sure that none of your GET requests change any relevant data in your database. This is a very novice mistake to make and makes your app susceptible to more than just CSRF attacks.

---

### Avoid using POST
Because ```<form>```s can only GET and POST, by using other methods like PUT, PATCH, and DELETE, an attacker has fewer methods to attack your site.

---

### Don't use method override!
Many applications use method-override to use PUT, PATCH, and DELETE requests over a regular form. This, however, converts requests that were previously invulnerable vulnerable!

Don't use method-override in your apps - just use AJAX!

---

### Don't support old browsers
Old browsers do not support CORS or security policies. By disabling support for older browsers (which more technologically-illiterate people use, who are more (easily) attacked), you minimize CSRF attack vectors.

---

### CSRF Tokens
The final solution is using CSRF tokens. How do CSRF tokens work?

1. Server sends the client a token.
2. Client submits a form with the token.
3. The server rejects the request if the token is invalid.

---

##### An attacker would have to somehow get the CSRF token from your site, and they would have to use JavaScript to do so. But, if your site does not support CORS, then there's no way for the attacker to get the CSRF token, eliminating the threat.

##### Make sure CSRF tokens can not be accessed with AJAX! Don't create a /csrf route just to grab a token, and especially don't support CORS on that route!

##### The token just needs to be "unguessable", making it difficult for an attacker to successfully guess within a couple of tries. It does not have to be cryptographically secure. An attack is one or two clicks by an unbeknownst user, not a brute force attack by a server.

---

### BREACH attack
If the server sends the same or very similar response over HTTPS+gzip multiple times, an attacker could guess the contents of response body (making HTTPS utterly useless). 
The solution is Make each response a tiny bit different.
CSRF tokens are generated on a per-request basis and different every time.

---

As the web moves towards JSON APIs and browsers become more secure with more security policies, CSRF is becoming less of a concern. Block older browsers from accessing your site and change as many of your APIs to be JSON APIs, and you basically no longer need CSRF tokens. But to be safe, you should still enable them whenever possible and especially when it's non-trivial to implement.

---

![](https://media.giphy.com/media/wdlnHV4gMyG7S/giphy.gif)

---

### Useful resources 
[XSS aka HTML Injection Attack explained](https://medium.com/@jamischarles/xss-aka-html-injection-attack-explained-538f46475f6c)
[Intro to CSRF](https://medium.com/swlh/intro-to-csrf-cross-site-request-forgery-9de669df03de)
[Understanding CSRF](https://github.com/pillarjs/understanding-csrf)
[Cross-Site Scripting (XSS) Explained](https://www.youtube.com/watch?v=EoaDgUgS6QA&ab_channel=PwnFunction)

---



