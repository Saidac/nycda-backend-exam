## NYCDA Backend Exam - Part 2

Given that we have a "customer" resource/model in our web server,

1 - How would you design the routes of your server based on REST convention? List them with VERB and /route

+

2 - Which pages would require templates, and how would you name them? List them with /route and templateName.extension

Answers in the order of HTTP Method, Route, View, Function.

GET /customers index.pug list all customers
GET /customers/id show.pug display particular customer details.

for CRUD we need more routes, i.e:

DELETE /customers/id to remove a customer from our list of customers.
We can render a view for delete that warns and ask our user if they are sure they want to
proceed with deleting, a delete.pug

=========

3 - What is a database constraint? Name the 3 types of database constraints you have learned.

Unique - There can only be one instance of this data in state.
Nan - data cant be "nothing".
Foreign key - If we want to point a a foreign key to another tables primary key,
we need to make sure that we cant input data that brakes this connection.

4 - What is a foreign key? Given that you have a Factory that has many cars and car that belongs to a factory, What would be your foreign key column?

is like a id number so we can references a tables column in another table.
A foreign key points to another tables primary key.

FACTORY DB

          Products table
id       model            unitCostInEUR     
1        Saturn           3000
2        Mars             5000

          Orders table
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

We can also hook to validations, which has a more generic use and can be used as a sort of joker
when creating logic centered around models in our applicaitons.

6 - What is the difference between database-level validations and application-level validations?

Application level validations is global and omnious. Like a user id, we want a
applicaiton level validaiton for our users so we cant have multiple instances of one user.

DB level validation sets rules for our data in a db, like we cant have "nothing"
as a input for users or password columns with a NAN constraint.

7 - Why do we use bcrypt. Write down 3 reasons why we use it if you can.

1) Its undecryptable. We cant decrypt what bcrypt decrypts, but its functionality lets us use the decrypted keys to match with others for authentication.
2) In traffic we only match two decrypted aliases, never the encrypted orginal. If someone hacks our server, they will get usless data.

8 - What is a flash message?
This is some cookie stuff right?dont know answer by heart. 

9 - What is the difference between minifying and obfuscating JavaScript?

Mnifying is ugglifying code by removing all the space that can be removed to
minimize the amounts of lines.

obfuscating is a new concept to me, maybe I missed that day? It has to do with
encrypting enformation?

10 - What are the 3 reasons that makes Gulp a good choice as an asset build library?

1) Its agnostic, you can use it for whatever you wanna do with streams, compared to Grunt which is opionated.

2) The stream functionality implements well with node.

3) The logo. No but um the user coommunity and documentation gives you
a great choice of task runner to choose from so you save a lot of time?
Like npm?
