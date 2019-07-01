# Intro to the Internet

What are the underlying things that happen when you make a request.

## How it works

Alan Turing - Turing tape... Binary zeros and ones

`Client` - Requests information  
`Server` - Responds with information

### IP Address
Every device has IP address

remoteip.me - get your ip address... might be same if many computers on same wifi?

127.0.0.1 - Locally on computer - `Localhost` - a server on your machine that serves it up just to you.

### DNS

Domain Name Server - Takes url and finds the IP address.

Name servers - Type a url, will ask the name server that you have setup on your computer and (will find the server to connect to it?)

```bash
nslookup google.com
```

### Port

Each device (server and client) has many ports (63k something)

Default port for http 80; https (443)?

3000, 8000, 9000

databases commonly run on 4532 redis 4567

## HTTP

Postman - App for making HTTP requests.

API - Application Programming Interface - way for programs to communicate with each other.

Headers - Metadata about the request
Body - Payload of the request - Contains the html document

-1 means it never expires

Caching - save copy of websites to the browser so it will load faster the next time. Store version of page in the browser, the website can deside how long to cache. As a server you would rather load from cache then load from the server.

### HTTP status codes


developer.mozilla.org/en-US/docs/Web/HTTP/Status

All status codes have a specific meaning.Some common status codes:


200 OK - means everything worked acording to plan  
201 Created -   
202 Accepted - Got the message working on it  
204 No Content - got an error?  
301 Moved Permanently  
304 Not Modified  
307 Temperary Redirected  
401  
403  
404 Not found  
405  
409 Conflict
500
502
503



> Any code in a 500 is bad. Generally the higher the code the worse it is.

### HTTP Response Types

There are different types of http requests. 

html - normal html
json - json formater extension for chrome.

```json

```

xml - less popular


### HTTP METHODS

#### GET
Ask server for information or a page (this is how curl requests a page)

> Item Potent - If you can do the same thing and get the same result every time.

get requests should be the same every time you ask for information it should return information.

#### POST

Request to create something new. Sign up, make new post.

#### DELETE

Request to delete something. Undo, remove. Logout, remove a post.

#### HEAD

Mini GET. Only returns the HEAD no body of the request. Get teh status code. 

> Most services request the head and then if status is 200 it will then make a get request.


#### PUT

Replace something

Swap one thing for another ... trading a player on a team

#### PATCH

Update information on a record.  
Change one thing about that thing ... player changes last name / change position they play

## REST

A set of rules to follow a convention for using HTTP Methods.

Verb and url. Where did you make the get or post to?

```
http://yourdomain.com/things/17
```

GET - Get the 17th thing
PUT - update the 17th thing
POST - create the 17th thing
DELETE - delete the 17th thing

## Cookies
Server puts information on us when we visit a page. Place a thing to track you that websites can reference later. Its a way of the website to identify who we are when we visit a page.

Each cookie is only for a specific site individually.

They have keys and values. when they expire. the path. the domain.

key=value;

## URLS

scheme://domain:port/path?foo=bar#fragment_id

http://google.com:80/search?q=howtocode#sponsored

### Protocals or Scheme

http
https
ws - websocket

### Query Perameters 
Ways to communicate additional information about a request.

These are on the end of url after `?`. they are in key values.

```
https://www.google.com/search?q=food
```

seperate each one by `&`

```
https://www.google.com/search?q=food&myname=aaron
```

> Usually ones that are not needed are just ignored.

### URL Fragments

Specific Portions of the page. Will bring the page to that spot. These are just ids on the div.

The id will be at the end of the url with a `#`. Called the Fragment id.
```
http://example.com/test#id_in_the_page
```