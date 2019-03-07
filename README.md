# Understanding Model-View-Controller

![MVC](https://i.ytimg.com/vi/QvR0ghfbQwU/maxresdefault.jpg)

1. Models (back-end)

The models write Ruby objects to the database and read them out again later. they are responsible for retrieving and storing data from the users of the app, they know how to read data from the database

once you store the data in the database you can call various methods to retrieve those records in the database

2. Controllers (back-end)

Controllers respond to requests from users, usually by coordinating the model and the view. they are responsible for handling the browser's request

> controller methods that responds to requests
> are sometimes called actions

3. Views (front-end)

Views show data its users most, often in the form of HTML web pages.


## Decomposing a route

```
http://localhost:3000/courses
```

`http://` http stand hypertext transfer protocol it is a set of rules web browsers and computers used to communicate with each other

`localhost` or `www.generassemb.ly` is the address of the host the computer running if it is localhost then your app send a request from your computer to your computer

`3000` to prevent conflict

`courses` the path of the resource you want to retrieve

![url](https://cloud.githubusercontent.com/assets/25366/8561247/75b73966-24d7-11e5-896a-06506648c4fe.png)

## common http method

- GET
- POST
- PUT / PATCH
- DELETE

it's not like ruby method , http method indicates the type of the req while ruby methods executes code

# ERB TEMPLTE

<p> Time <%= Time.now %> </p>

You store some static text `HTML code` Then, using special ERB tags, you embed Ruby code that displays changing, dynamic data into the static text.

### the diffrent between <%= %> output embedding tag and <% %> regular embedding tag

```erb
<% x = 2 * 3 %> # wont print
<%= x = 2 * 3 %> # print 6
```

`<% %>` regular embedding tag works with loops and conditions

```erb
<% if x > 6 %>
<p> render something if the condition is true <p>
<% end %>

<% 4.times do %>
<p> repeat <p>
<% end %>

```

# URL Parameters and Route Priority

To create a single route that will match any page users might attempt to visit.

- route

```
get("/:name") do
  @name =  params[:name]
end
```

# Instance Variables Vs Local Variables.

When using variables inside classes, only instance variables, which are prefixed with the `@` character, will be visible to all of the methods in the class. A variable that only exists inside a code block or method is called a local variable.

> using global variable are not recommended but if you have to do it use the `$` character as a prefix

# About Rails

Rails helps power popular websites like Airbnb. what makes Rails so awesome is that it favors convention over configuration.

Usually in the web development world you had to decide what to name your database tables. You had to decide where to store your HTML templates. You had to decide what to name the classes that controlled everything and much more.

And then you had to configure your application so It could take weeks before you served your first web page.

in Rails `Database tables` have standardized names. `HTML templates` are stored in standardized folders and the code that controls all this is set up in a standardized architecture.

> if you stick to these conventions Rails will automatically know where to look for everything you set up.

## How Rails process the request

1. Rails look at the request to figure it out which code should handle it

2. The request get routed to action method on a controller

3. Controller loads the resource in from the database using a model class

4. Controller render the view using the model data to generate response content

## Creating Rails app

new app

```
rails new app-name --database=postgresql
```

## Starting a server

start the server

```
rails s
rails server
```

## Create a resource

A "resource" is a thing that you want users to be able to perform "CRUD" operations on: to create instances of it, read data for it, update data for it, and delete it when they don't want it any more.

A Rails "scaffold" creates a model, view, and controller for a resource, all at once.

```
rails generate scaffold ModelName attribute1:type attribute2:type ...
```

## Updating the model

```
rails generate migration AddSomethingToModel attribute1:type attribute2:type
```

Reference:

[https://gist.github.com/mdang/95b4f54cadf12e7e0415](https://gist.github.com/mdang/95b4f54cadf12e7e0415)
[http://www.pragtob.info/rails-beginner-cheatsheet/](http://www.pragtob.info/rails-beginner-cheatsheet/)
[http://staff.um.edu.mt/alexiei.dingli/IntroductionToWS/Lectures/ruby-on-rails-cheat-sheet-v1.pdf](http://staff.um.edu.mt/alexiei.dingli/IntroductionToWS/Lectures/ruby-on-rails-cheat-sheet-v1.pdf)
