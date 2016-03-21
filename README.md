# Week 06

### Question 1

You're working on your Tunr app and you encounter this error. What does it mean and where would you go first to address it?  

![Rails error](http://i.imgur.com/9NR7XNT.png)  

```text
This error means a template is likely missing.

The first place I would check to correct this error is the views/artists folder and see if there is an index.html.erb file. I would likely need to create one to fix this error.
```

### Question 2

Consider this file name:

```
20150726145027_create_artists.rb
```

What is the purpose of this file, and what is the purpose of the numbers at the beginning of its name?

```text
The purpose of this file is to create a table of artists for the rails app. It will be used in migration to edit the schema file.

The numbers at the beginning of its name is a timestamp. The timestamp is used to determine which migration files should be run and in what order.
```

### Question 3

In a Rails application, how is the router related to controller actions?  

```text
The router sends the user's request to the controller actions. In a rails app, the router provides a RESTful routes approach, which includes GET, PUT (PATCH), POST, and DELETE commands to relay the request.
```

### Question 4

Assuming our Tunr Rails app (1) has a Song model that belongs to an Artist model and (2) uses nested resources, which of the following helpers would create a URL that routes to `songs#new`? (Select one answer)  

```
[x] artist_song_path( @artist, @song )
[x] new_artist_song_path( @artist )
[x] create_artist_song_path( @artist )
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
This code would most make sense as a model method. This is to practice separation of concerns and follow the rails pattern "Fat Model, Skinny Controller". Since changing a color doesn't require directly accessing the database, it's not needed in the controller. As a model method, it can be accessed in the view, passing it the data the controller provided the view.
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
The validator is angry because the code is filled with clown hats of ruby code. The best way to validate this code is to run the server and load the page in your browser. From there you can inspect the page, copy the html generated, and paste that into the validator.
```

### Question 9

What are two differences between the two following commands?

```
$ rails new tunr
$ rails new . -d postgresql
```

```
The first command creates a basic rails app named tunr with the default database. The second command creates a basic rails app in the current directory with a postgres database.
```

### Question 10

Which **one** of the following is the most correct way to display an error message to the user?

```rb
[] @error = "Wrong password!"
[] puts "Wrong password!"
[x] flash[:alert] = "Wrong password!"
[] session[:error] = "Wrong password!"
[] render error: "Wrong password!"
[] flash[:notice] = "Wrong password!"
```
