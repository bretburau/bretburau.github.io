---
layout: post
title:      "JSON Web Tokens"
date:       2018-10-28 12:16:15 +0000
permalink:  json_web_tokens
---


JSON web tokens are a relatively recent addition to the web. JWT is an open standard that was introduced as an alternative to the more traditional server-side login using cookies and sessions. There are several ways they can be more efficient than session logins, and we'll explore that here.

### What is a JWT?

A JSON web token, at its base is a pretty simple structure. It consists of three parts: a header, the payload, and the signature. The header is just a JSON object containing information about the JWT.
```
{
  "alg": "HS256",
  "typ": "JWT"
}
```
In this example, "alg" is telling us what type of encoding algorithm the token is using( in this case HS256), and "typ" is just defining it's type as a JSON  web token. 

The second part of a JWT is the payload. This is where the actual information is passed along. While there are many possible applications of this, user authentication is a pretty common one, and we could send along some user info.
```
{
  "name": "Admin McAdminson",
  "admin": true
}
```

We then have the signiture part of the token. Here the header and the payload are simply encoded with a secret key:
```HMACSHA256(
  base64UrlEncode(header) + "." +
  base64UrlEncode(payload),
  secret)
	```
	These three chunks are then base64 encoded, seperated by dots, and you have your token! Here's what a finished JWT looks like, from https://jwt.io:
	```eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c
	```
	Notice the two periods splitting the header, payload, and signiture.
	The point of the signiture is to verify that the payload hasn't been tampered with. While the data isn't actually encrypted in this process, if anything is intercepted and changed, the digital signiture would change, and the server would know that the JWT is no longer valid.
	
	### What's it for?
	When a user logs in, they send their credentials down to the server. The server than checks that the user exists, password is correct, etc. If everything checks out, the server then creates the JWT and sends it back to the user. Armed with this, they can access all the routes and services the server requires authentication for. The JWT is just sent along with any requests to the server as a indication that the user is logged in, without having to store anything on the server. This can reduce the amount of http requests made by quite a lot. Since the state of being logged in is stored on the client, the server doesn't have to be asked about login status for every request. In stead of "Hey can I have this data, I'm logged in, right?" its more like "here's proof that I'm logged in, can I have that data now?" A potential downside to all this is the size of the token. If a developer adds a lot of info to the payload, the JWT gets bigger, and at some point it mitigates the efficiency gained by reducing the amount of requests. By keeping the tokens light, solid speed gains can be made vs. using cookies and server-side authentication.
