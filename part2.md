## NYCDA Backend Exam - Part 2

Given that we have a "customer" resource/model in our web server,

1 - How would you design the routes of your server based on REST convention? List them with VERB and /route

GET admin/customers/
GET admin/customers/new
POST admin/customers/
GET admin/customer/:id/
GET admin/customer/:id/edit
PUT admin/customer/:id
DELETE admin/customer/:id/


2 - Which pages would require templates, and how would you name them? List them with /route and templateName.extension

Answers in the order of HTTP Method, Route, View, Function.

GET admin/customers/index renders views/customers/index.pug
GET admin/customers/:id  renders views/customers/show.pug
GET admin/customer/new renders views/customers/new.pug
POST admin/customer/:id/new
GET admin/customer/:id/edit GET admin/customer/new renders views/customers/edit.pug
PUT admin/customer/:id/edit
DELETE admin/customer/:id/delete
GET admin/customer/:id/delete renders views/customers/delete.pug (for displaying alert warning)

=========

3 - What is a database constraint? Name the 3 types of database constraints you have learned.

Unique - There can only be one instance of this data in state.
NULL - data cant be "nothing".
Foreign key - If we want to point a a foreign key to another tables primary key,we need to make sure that we cant input data that DOES NOT brake this connection and confirms to the connection.

4 - What is a foreign key? Given that you have a Factory that has many cars and car that belongs to a factory, What would be your foreign key column?

A foreign key points to another tables primary key, like a id number so that we can references a tables column in another table and can be used for linking two models together.

In this examples we have two models, Products and Orders.

FACTORY Database

          PRODUCTS
id       model            unitCostInEUR     
1        Saturn           3000
2        Mars             5000

          ORDERS
id       customerName          pId    qt.
1        HassanRentals         1      5
2        HassanRentals         2      3
3        Smith Deals           2      1

In this example, orders table links to the products table via pId.
This allows us to calculate the cost of a particular order.


5 - List all the model lifecycle hooks you have learned from sequelize and explain them briefly if necessary.

Its a way to hook behaviour or logic to model life cycle events by setting listeners that executes code when triggered on these possible occasions:

Before and after...
                  ...Build
                  ...Create
                  ...Update
                  ...Destroy

We can also hook to validations, which has a more generic use and can be used as a sort of joker when creating logic centered around models in our applicaitons.

Build is establishing the design of the model, seperate from the creation of it

6 - What is the difference between database-level validations and application-level validations?

Database level validation is setting a particular data type for a column at the point of creating a table in the db.

Application level validation is letting our ORM compare the input from user to the model we have migrated, which means that the validation happens in client side, and does not require call to db.

7 - Why do we use bcrypt. Write down 3 reasons why we use it if you can.

1) Its undecryptable. We cant decrypt what bcrypt decrypts, but its functionality lets us use the decrypted keys to match with others for authentication.

2) In traffic we only match two decrypted aliases, never the encrypted orginal. If someone hacks our server, they will get usless data. ### COMMENT: We cant match encrypted keys from different sources with bcrypt?

8 - What is a flash message?

Via the use of session and hooks we can set scripts to display messages, for example when a user log out we can display a message "you have been logged out".


9 - What is the difference between minifying and obfuscating JavaScript?

Mnifying is ugglifying code by removing all the space that can be removed to minimize the amounts of lines.

obfuscating is obscuring code for security reasons, to avoid tinkering with code for example. We can automate obfuscation with a npm package for gulp.


10 - What are the 3 reasons that makes Gulp a good choice as an asset build library?

1) Its agnostic, you can use it for whatever you wanna do with streams, compared to Grunt which is opionated.

2) The stream functionality implements well with node. Easy to configure and inutive.

3) The logo. No but um the user coommunity and documentation gives you a great choice of plugins to choose from like npm.
