# Deep Dive Into Cookies &#127850;

----

## What is a Cookie?

cookies are small files that websites sent to your browser, and with every of your interactions with that website, the browser will send that file with your requests

 ### Use Cases

- **Session Management**: keep your data in server and remember who you were, keeps you logged-in and personalize the content and data of web application base on your **Session**.
- **Web Personalization**: keep your preferences data like *dark mode*, *language*, *etc*.
- **Tracking**: track your interactions like last page you visited, what you click on, and things like that, used for advertisers to advertise more efficiently.

### Types

- **First-Party Cookies**: set by the domain you are in, like **example.com** set a cookie for you when you are in **example.com**.
- **Third-Party Cookies**: set by other domains, like **tracker.com** set a cookie for you when you are in **example.com**. but under the **tracker.com** domain. so when you visit another site like **another.com** and loads a resource from **tracker.com** the cookies will be sent.

## Cookies Format

cookies are small text files that stored in your browser, they are simple but they have a structure at their heart.

### Core Components

- **CookieName = Value**: the heart of the cookies
    - **CookieName**: A unique, case-sensitive name assigned by the server to identify the specific piece of data being stored.
    - **Value**: The actual data associated with the cookie. there is a size limit for the cookies so keep them short and small.

### Optional Attributes

- **Expires**: expiry date for our cookie, if a cookie has this attribute, it called *persistent cookie*, the browser will delete it on the date time that we set for it.
- **Max-Age**: defines the cookie's lifespan, it's a integer that contain the seconds from the moment we set the cookie to the moment we want the cookie to be deleted.
- **Domain**: the domain that the cookie is set and needed the browser to be sent to.
    - This attribute specifies the domain, or subdomains, where the cookie is permitted to be sent.
    - A domain must match or be a subdomain of the domain of the page setting the cookie for it to be included.
    - For instance, a cookie with `Domain=example.com` can be used on `example.com` itself, along with any subdomains like `blog.example.com`. A cookie domain can have a leading dot (`.`), ensuring it is sent to all the subdomains.
- **Path**: The path that we want the browser send the request only when the path matches, if we set a cookie with *path=/shop* the cookies only sent to server when the path is matches the path in the cookie. the cookie will be sent in */shop*, */shop/anything* and will not sent to */info*.

### Security Attributes

- **Secure**: sent cookies only in *HTTPS* requests.
- **HttpOnly**: the browser blocks the JavaScript to access the cookies

### Example:

```http
Set-Cookie: sessionId=123456789; Expires=Wed, 15 Mar 2024 22:00:00 GMT; Path=/; Domain=.example.com; HttpOnly; Secure
```

**This cookie:**

- Is named “sessionId”
- Has a value of “123456789”
- Will expire on March 15, 2024
- Is valid for all pages within the example.com domain and its subdomains
- Is only accessible by the web server, not client-side JavaScript
- Will only be transmitted over HTTPS connections

