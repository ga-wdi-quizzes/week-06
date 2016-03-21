# Week 06

### Question 1

You're working on your Tunr app and you encounter this error. What does it mean and where would you go first to address it?  

![Rails error](http://i.imgur.com/9NR7XNT.png)  

```text
When this "template missing" error occurs, it means that the controller did not render a view and did not successfully redirect to the index.html.erb. To fix the problem I would add a create.erb path or might need to define some method or action within the existing index file.
```

### Question 2

Consider this file name:

```
20150726145027_create_artists.rb
```

What is the purpose of this file, and what is the purpose of the numbers at the beginning of its name?

```text
This file creates a migration that creates the table for artists to the schema in the rails application. The numbers are a timestamp that represent the time that the migration file for artists was created, and specifies the order that the files should run.
```

### Question 3

In a Rails application, how is the router related to controller actions?  

```text
The router takes a request from a user and determines where the controller directs to.
```

### Question 4

Assuming our Tunr Rails app (1) has a Song model that belongs to an Artist model and (2) uses nested resources, which of the following helpers would create a URL that routes to `songs#new`? (Select one answer)  

```
[] artist_song_path( @artist, @song )
[x] new_artist_song_path( @artist )
[] create_artist_song_path( @artist )
[] new_artist_song_path( @artist, Song.all )
[x] new_song_path( @song )
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
This code would make most sense as a helper method because it makes all methods available in the controller to views. In this case ,the average rating attribute would change as users continue to rate the songs, so extracting logic from the views allows for easier conditional formatting (i.e. change colors).
```

### Question 7

You clone yet another Tunr repo. Put the following commands in the correct order necessary to make the app run. Delete the one command that will not be used.

```
$ git clone git@github.com:ga-wdi-exercises/moar-tunr.git
$ bundle install
$ rails new . -d postgresql
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
The "clown hats" wrapping the content are ruby symbols, not HTML, which is why the validator throws the error. To accurately validate, I would either remove the clown hat symbols or paste the code into a ruby validator online.
```

### Question 9

What are two differences between the two following commands?

```
$ rails new tunr
$ rails new . -d postgresql
```

```
"$ rails new tunr" creates a rails directory called tunr and connects the tunr application to mysql. On the other hand, "$ rails new . -d postgresql" creates a rails file within a directory so that the app can run in psql. That is, it connects to the psql database.
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
