## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!). 

Note: When you're done, submit a PR. 

1. List the five common HTTP verbs and what the purpose is of each verb.
	GET -retrieval
	HEAD - retrieval of only header (no body)
	POST - send/submit data to server
	PUT - update
	DELETE - remove

2. What is Sinatra? A DSL using Ruby to make lightweight web apps
4. What is MVC? Model, View, Controller model--components of web apps
5. Why do we follow conventions when creating our actions/path names in our Sinatra routes? verb + path = route. Sinatra recognizes the conventions and does legwork behind the scenes. The structure of Sinatra is distinct to developers, and helps with others looking at the code.
6. What types of variables are accessible in our view templates without explicitly passing them?
	instance variables

7. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?
  
  ```ruby
  get '/horses' do
  @count = 1 #have access to @count in the  index.erb view
    erb :index
  end
  ```

8. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view?

 ```ruby
  get '/horses' do
    erb :index, locals{name: "Mr. Ed" }
  end
  ```
9. What's the purpose of ERB? Enables Ruby code to be passed into View files
10. Why do I need a development AND test database? Because those environments require different configurations. Development: may have dummy data in DB. Testing: want to keep DB clean.
11. What's responsive design? Where the view renders correctly for differing screen size/displays
12. What is CRUD and why is it important? Create, Read, Update, Delete. Forms the basis of apps using a DB and accessing data in that DB. 
13. What does HTTP stand for?  Hypertext Transfer Protocol 
14. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways? <%= var_name %> and <% var_name %>. The first renders, the second executes the code, but does not show up in the view
15. What's an ORM? Object Relational Mapping. Describes the relationship between DB and a OOP language (Ruby).
16. What's the most commonly used ORM in ruby (Sinatra & Rails)? ActiveRecord
17. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.

get '/restaurants' - displays all restaurants
get '/restaurant/:id' -shows one restaurant with that matching id primary key
get '/restaurant/new' -shows a display to enter a new restaurant
post '/restaurants/new' -sends the entered restaurant to the DB
get '/restaurants/:id/edit' -shows a display to edit a restaurant
put'/restaurant/:id/edit' -sends the updated restaurant to the DB
delete '/restaurants/:id' -removes that specific restaurant (id)

18. What's a migration? A structure for creating a table in a DB
19. When you create a migration, does it automatically modify your database? No.
20. How does a model relate to a database? with a ORM table
21. What's the difference between agile workflow and waterfall method? Agile: Break down the workflow into 'sprints' where functional features can be shipped to the client sooner/as they become finished. Waterfall: doing the whole Software Devt Life Cycle (SDLC) phases from start to finish (requiring one phase to be completed before moving onto the next) and presenting a 'finished product' at the end. 
22. What is the difference between `#new` and `#create`? New: creates an instance, and Create: creates & saves an instance to the DB
