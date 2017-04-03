## Week Three Recap

### Instructions
Fork this repository. Be sure to pull the latest changes to your local repo. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

1. What is the entry at the command line to create a new rails app? rails new name_of_new_app
2. What do Models generally inherit from in rails? ActiveRecord::Base
3. What do Controllers generally inherit from in a rails project? ApplicationController
4. How would I create a route if I wanted to see a specific horse in my routes fitle assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality? resources :horses, only: [:show]
5. What rake task is useful when looking at routes, and what information does it give you? rake routes. Gives us a route helper, the http verb, URI, and controller#action (method in the controller)
6. What is an example of a route helper? When would you use them? otters_path. in place of the URI (e.g. capybara visit otters_path, should reference the index page where all the otters are. 
7. What's the difference between what `_url` and `_path` return when combined with a routes prefix? one is relative and one is absolute path 
8. What are strong params and why are the necessary? They allow for having a private method assign what is allowed by the user 
9. What role does `form_for` play in helping us create our forms? It's a rails helper method (I think).  
10. How does `form_for` know where to submit the user's input?  model specified (e.g. form_for @otter )
11. Create a form using a `form_for` helper to create a new `Horse`. 
<h1> Create a new horsey here! </h1>
<%= form_for @horse do |f| %>
<%= f.label :name %>
<%= f.text_field :name %>

<%= f.label :description %>
<%= f.text_area :description %>

<%= f.label :price %>
<%= f.text_area :price %>
<%= f.submit %>
<% end %>

12. Why do we want to validate our models? to make sure those fields are filled out
