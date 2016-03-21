# Week 06

### Question 1

You're working on your Tunr app and you encounter this error. What does it mean and where would you go first to address it?  

![Rails error](http://i.imgur.com/9NR7XNT.png)

```text
andrewkim does not have an `index.html.erb` file where one should reside in `app/views`.  This error is likely to have happened by something like trying to browse to localhost:3000/artists after manually setting up routes and a controller method `index` found in `app/controllers/artists_controler.rb` (don't think it wouldn't have gone that far otherwise).

I'm a bit fuzzy on where the source file might be coming from when the error was raised, and why find is being called in such a way.  I'm guessing it's some sort of rails wrapper of ActiveRecord.
```

### Question 2

Consider this file name:

```
20150726145027_create_artists.rb
```

What is the purpose of this file, and what is the purpose of the numbers at the beginning of its name?

```text
This is a rails migration file.  It is used to auto define the schema of the SQL database for ActiveRecord in `db/schema.rb`.  It can be used to create or update the schema of the database.  The numbers at the beginning are a timestamp, which is used to determine which migrations should be run first.  The migrations are run in oldest-to-newest order.
```

### Question 3

In a Rails application, how is the router related to controller actions?  

```text
The rails router fires off methods defined in the controller based on the http request and type received.

The Rails router's actions are defined in `config/routes.rb`, where it contains a list of request type -> path -> corresponding method to be called.
```

### Question 4

Assuming our Tunr Rails app (1) has a Song model that belongs to an Artist model and (2) uses nested resources, which of the following helpers would create a URL that routes to `songs#new`? (Select one answer)  

```
[] artist_song_path( @artist, @song ) 
[X] new_artist_song_path( @artist )
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
[X] (a) Browser, (b) Server
```

### Question 6

Assume each Song in Tunr has an `avg_rating` attribute. It is an integer from 1 to 10, and is the average rating of all of Tunr's millions of enthusiastic users.

You would like the title of each song to be displayed in a different color depending on the song's rating.

A great song like "Livin' on a Prayer" would have a rating of 10 and appear green, and a bad song like "Blurred Lines" would have a rating of 1 and appear red.

Without getting into specifics of how you would write the code itself, pick one and defend your answer:

This code would make most sense as a...
X ...model method.
- ...controller method.
- ...helper method.

```text
Because `avg_rating` is an attribute stored in the database, the songs color can be determined without ever having to know anything the controller knows.  Separation of concerns.
```

### Question 7

You clone yet another Tunr repo. Put the following commands in the correct order necessary to make the app run. Delete the one command that will not be used.

```
$ git clone git@github.com:ga-wdi-exercises/moar-tunr.git
$ cd moar-tunr # I added this (we must be in the project directory for the next commands to work)
$ bundle install
$ rails new . -d postgresql
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
The HTML validator doesn't know what ERB is, silly.  Why would it? ERB is for templating, using the ruby programming language.  To validate HTML, first navigate to the proper route in your browser that renders the view you want to validate, and view the source with your browser.  Then, copy paste the source into the validator.
```

### Question 9

What are two differences between the two following commands?

```
$ rails new tunr
$ rails new . -d postgresql
```

```
The former creates a new Rails project named `tunr` using the default database for new Rails projects, which I think is SQLite, and places its contents in a new directory called `tunr`.

The latter creates a new rails project inside the current working directory (`.`) using PostgreSQL as the database.
```

### Question 10

Which **one** of the following is the most correct way to display an error message to the user?

```rb
[] @error = "Wrong password!"
[] puts "Wrong password!"
[X] flash[:alert] = "Wrong password!"
[] session[:error] = "Wrong password!"
[] render error: "Wrong password!"
[] flash[:notice] = "Wrong password!"
```

