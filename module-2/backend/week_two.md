## Week Two - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON - YOU are a web developer!!!). 

Note: When you're done, submit a PR.

- At a high level, what is ActiveRecord? What does it do/allow you to do? It's an ORM that allows you to interact with a database using Ruby. AR is a gem that deals with the database, and does that through the 'M', model in MVC.
- Assume you have the following model:

class Team << ActiveRecord::Base
end

What are some methods you can call on Team? If these methods aren't defined in the class, how do you have access to them?

-You have access to AR methods, as Team inherits from AR::Base (in rails 5 I think it inherits from ApplicationController). 

Examples: All, create, new, save, find, find_by, where, new_record are a few examples of AR methods

- Assume that in your database, a team has the following attributes: "id", "name", owner_id". How would you find the name of a team with an id of 4? Assuming your class only included the code from question 2, how could you find the owner of the same team?
- team = Team.find(4) ; team.name
- owner = Team.find_by(id: 4).owner_id

- Assume that you added a line to your Team class as follows:

class Team << ActiveRecord::Base
  belongs_to :owner
end

Now how would you find the owner of the team with an id of 4?
owner.team.find(4)

- In a database that's holding students and teachers, what will be the relationship between students and teachers? Draw the schema diagram. many to many
- Define foreign key, primary key, and schema. pkey: unique identifier for a row (in a table). fkey: a primary key that belongs to a different table (row). schema: a blueprint to the structure of a database.
- Describe the relationship between a foreign key on one table and a primary key on another table. primary key on another table will be 'ID' and the foreign key will reference that primary key with syntax othertablename_id (singular of that table name_id)
- What are the parts of an HTTP response? A response will have a status code, head, message


### Optional Questions

1. Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.
class methods: find-will select by ID. find_by: will return an instance (behind scenes: where(condition).limit(1). where: like find_by, will return condition specified. create: will make a new instance & save it. instance method: update_attributes-will update a name, for example
2. Name your three favorite ActiveRecord rake tasks and describe what they do. rake db:create will initiate a database.
  rake db:migrate will add structure to the database as specified (and confirmed via the schema). rake db:rollback will go back one migration (reset to the last successful migration)
3. What two columns does `t.timestamps null: false` create in our database? created_at ; updated_at
4. In a database that's holding schools and teachers, what will be the relationship between schools and teachers? many to many
5. In the same database, what will you need to do to create this relationship (draw a schema diagram)?
6. Give an example of when you might want to store information besides ids on a join table. When an event doesn't occur until there is a need for a join table (e.g. a gpa will be on a join table 'evaluations' between students and courses) 
7. Describe and diagram the relationship between patients and doctors.
8. Describe and diagram the relationship between museums and original_paintings.
9. What could you see in your code that would make you think you might want to create a partial? lots of repetition/wanting to see the same structure amongst pages in an app
