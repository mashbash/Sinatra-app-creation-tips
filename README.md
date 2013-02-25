Sinatra-app-creation-tips
=========================

Sinatra, ActiveRecord

--------------------------
Understand the 2 routes that you will be using in the Sinatra app:

1. Get - when you want to show something
 
2. Post - when you want to create something

..there are 2 other routes, puts and deletes but be sure to include rack middleware when you want to use these. 

Plan
- Think about what tables you might need, their relationships
- What models will you then need?

Decide how many tables you will need in your database
- create their respective migration files
- table names are always plural
- set all the fields you want included for each table
- consider adding a default number to fields where you plan to use as a counter
- always good to use timestamp
- can add requirements e.g. null => false as a form of validation that can start at the database level

Decide what models you will need
- Class names must be singular
- put validations in the model 
- define relationship of tables in database in model files
- for behaviours specific to the class, put them as methods in its respective class

Views folder 
- it is easier to create the files we need as we go along
- View files are .erb, which means embedded ruby
- if you want to use ruby in the file, open with <% ..ruby code here...%>
- if you want to print out the result, open with <%= ...ruby code here...%>
- keep any sort of data manipulation in this file to a minimum

Controllers folder
- this is where all the routing happens
- if any one route gets too bloated with logic and code, then time to consider putting it as a method in it's respective class
- if there is repetitive code, refactor and put into its respective model file

What are helper files?
- As the name suggests, it helps in the sense that you can store behaviors in these files that don't belong to any particular model
or it can be used across many different models
- the methods in this file are called upon by other files in the app just by their method name (it's like magic)

What are _partial files?
- Partial files always start with _, it is a rails convention
- saved with the rest of the view files
- This is where you store html code that you find being repeated everywhere and you just plug it in where it needs to be displayed

CSS 
- Important to set up html tags in a manner that makes it easy for you later on to refer to when improving the look through CSS

============================================================================

Possible errors to look out for:

If you do rackup and it says the port is in use, in the command line, type this:
ps auxwww | grep ruby
then kill the ruby process that is running to stop it

*Important to name your routes properly or risk the problem of being sent to the wrong URL 

*When getting fancy with AJAX, don't forget you have to update all the things you are messing around with on that page through its file too

*Use sessions to keep track of a user being logged in or out, and checking if the user is authorized to view a page

*When unsure of what's going wrong, rake console and puts statements in your routes are your best friends
