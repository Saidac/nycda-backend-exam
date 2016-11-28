## NYCDA Backend Exam
=====================
Explain the questions well!!

### 1- Why do we should include script tags at the very end of an html file, before closing </body>?

Because otherwise it's going to be loaded before our content. For the user it can make our app appear slow.

### 2 - What is a middleware?

It can alter a HTTP request response cycle with some logic. We can use it for routing or authentication for example.

### 3 - Why do we use express.static() middleware?
Middleware deals with the response and request object, and can be used for routing but also exucuting code before the response is given to a request.

We can use it to serve static files in a public directory, like css files for exmaple.

### 4 - What is favicon.ico ?

Custom icon to be displayed in the adressbar of the browser.

### 5 - Why do we use a bodyParser middleware ?

It parses the body part of the HTTP request in to something that is easier to deal with for node.

### 6 - What is the difference in terms of parsing a data received from a web form with POST or an AJAX POST request?

An AJAX gets data asynchrously as a string in JS and by parsing it as JSON can be stored in a json file.

If we submit with POST we do so synchrousley via HTTP request which body we can parse with middleware and map it after a model we create with an ORM so we can store it in our DB correctly.

### 7 - Why do we use methodOverride middleware ?

To extend the HTTP POST in forms so we can delete and edit data, where the client normally dont support it.

### 8 - What are the differences between sessions and cookies ?

Session are stored server side. Cookies are stored client side. Sessions are used for caching.

We use cookies to store data about the client's user on their machine. 

### 9 - Why do we use a session middleware ?

For authentication purposes. Out app may render different views for a user resource depending on a session.

### 10 - Why do we use a build process ?

Because gulp is an awesome thing that lets you connect components by streams and build on the fly.

We can use it to make our app load faster with bouncing our js or css files into one file for faster load time. We can also use it to create sprite version of a bunch of images?

This writing feature can also be use to write a css file with only the classes from bootstrap which we are actually using to minimize load time. Also we can uglify code with it.  

Dont really grasp the power of streams yet, but I guess its a way of sending and retriving data at a lower level than for example a http request response cycle.
