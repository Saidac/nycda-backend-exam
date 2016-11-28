## NYCDA Backend Exam - Part 3

### 1 - What is the difference between git pull and git merge?

git pull fetches data from remote repo and merges it to the current position of the HEAD locally.  

Git merge merges you branch with your base.

### 2 - Why do we use a pull request on github instead of merging our branch directly to master and then pushing it to github?

Because we may wanna wait with publishing stuff the the branch for production. For example we have completed feauture A, but need feuature be done in order for A to make sense, so we pull the a branch into a new b branch and start working on it, and then push it when its to complete and later to a pull request to be merged with master.

### 3 - Why do we use database migrations?

Because its way easier to alter the model this way with an ORM than doing SQL quires.

### 4 - What is the difference between up and down functions of sequelize migration files?

It flips through our migrations back or forth chronologically?

### 5 - Name 3 reasons why Sass/SCSS is better than CSS?

1) We extend on CSS with SASS which enables us to write more maintainable code faster. It somewhat avoid the un-maintable code with CSS code.

2) it has logic, it can do math, we have variables, we can to extension and includes, mix ins.

3) We can use SASS for compressin/minify in GULP

### 6 - What is the right way to include bootstrap to your project?

Using gulp to only include the css classes we are actually using, then bouncing all our scss files into one css file to be deployed in production.


### 7 - Why _variables.scss file is important?

In this file we customize the bootstrap standard style by comiting out all code, then un comment the part we want to style and alter.

### 8 - Lets say you want to change the alert component of bootstrap, what are steps/strategy would you use to make that change?

set up gulp, create assests folder with vendor dir for bootstrap scss dir that has a bootstrap foler with two folders: _variables.scss and _alert.scss. In our component scss file make the changes we want to bootstrap by adding a class. In the _variables file we alter the values of existing bootstrap classes. We tell gulp to concat our scss file sin to one css to be loaded in the browser.
