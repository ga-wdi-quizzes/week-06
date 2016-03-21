# Week 06

### Question 1

You're working on your Tunr app and you encounter this error. What does it mean and where would you go first to address it?  

![Rails error](http://i.imgur.com/9NR7XNT.png)  

```text
It looks like index html pages have not been created for the artist class and the application.  The controller has a "find" function that does not seem to link up to the view.  Therefore, I would go to views/artists and create an index.html.erb file and views/layout and create an index.html.erb file.
```

### Question 2

Consider this file name:

```
20150726145027_create_artists.rb
```

What is the purpose of this file, and what is the purpose of the numbers at the beginning of its name?

```text
This is a migration file.  Migrations are used to import data that create tables and classes and define columns in the database schema.  The above file name begins with a timestamp and includes a description with underscores on what action it is undertaking.
```

### Question 3

In a Rails application, how is the router related to controller actions?  

```text
The router establishes routes that govern how the client input it sent through the controller to access the model and database.  Each route consists of a verb (e.g. "get") and a path (/artists/index).  These routes match the methods defined in the controllers pertaining to a particular class.  
```

### Question 4

Assuming our Tunr Rails app (1) has a Song model that belongs to an Artist model and (2) uses nested resources, which of the following helpers would create a URL that routes to `songs#new`? (Select one answer)  

```
[x] artist_song_path( @artist, @song )
[] new_artist_song_path( @artist )
[] create_artist_song_path( @artist )
[] new_artist_song_path( @artist, Song.all )
[] new_song_path( @song )
```

### Question 5

Where are (a) cookies and (b) session variables stored? (Select one answer)  

```
[] (a) Server, (b) Browser  
[] (a) Browser, (b) Database  
[] (a) Database, (b) Server  
[x] (a) Browser, (b) Server  
```

### Question 6

Assume each Song in Tunr has an `avg_rating` attribute. It is an integer from 1 to 10, and is the average rating of all of Tunr's millions of enthusiastic users.

You would like the title of each song to be displayed in a different color depending on the song's rating.

A great song like "Livin' on a Prayer" would have a rating of 10 and appear green, and a bad song like "Blurred Lines" would have a rating of 1 and appear red.

Without getting into specifics of how you would write the code itself, pick one and defend your answer:

This code would make most sense as a...
- ...model method.
- ...controller method.
- ...helper method.

```text
In this scenario, the source of the action is coming from the client input side in the MVC model.  In order to change the color of the song title, some sort of link needs to be placed in the view html.erb file.  Since the controller bridges the gap between the user/router and the views, a controller method makes the most sense.
```

### Question 7

You clone yet another Tunr repo. Put the following commands in the correct order necessary to make the app run. Delete the one command that will not be used.

```
$ git clone git@github.com:ga-wdi-exercises/moar-tunr.git
$ bundle install
$ rake db:drop
$ rake db:create
$ rake db:migrate
$ rake db:seed
$ rails s
```

### Question 8

You're a good person and decide to validate your HTML. You copy and paste the contents of `app/views/artists/index.html.erb` into the validator:

```erb
<h2>Artists</h2>

<% @artists.each do |artist| %>
  <div><%= link_to artist.name, artist %></div>
<% end %>
```

The validator throws errors at you! Why? Assuming you haven't made any mistakes in your code, how could you go about accurately validating your HTML?

```
You will receive error messages because the above code does not contain the proper HTML document format structure.  Additionally, you may also receive an error because the erb tags seem to set off errors in HTML validators and the atom linter plug-in.  As long as all the errors are related to HTML document type and the erb tags having "unescaped <", you should be okay.
```

### Question 9

What are two differences between the two following commands?

```
$ rails new tunr
$ rails new . -d postgresql
```

```
"rails new . -d postgresql" creates a new database.  "rails new tunr" creates a new rails application called "tunr" and its file directory.
```

### Question 10

Which **one** of the following is the most correct way to display an error message to the user?

```rb
[] @error = "Wrong password!"
[] puts "Wrong password!"
[] flash[:alert] = "Wrong password!"
[] session[:error] = "Wrong password!"
[] render error: "Wrong password!"
[x] flash[:notice] = "Wrong password!"
```
