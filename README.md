# Week 06

### Question 1

You're working on your Tunr app and you encounter this error. What does it mean and where would you go first to address it?  

![Rails error](http://i.imgur.com/9NR7XNT.png)  

```text

This error means that there is no `index` view defined for the Artist model, so the Artists controller cannot find the appropriate view based on the routes defined in the `config` folder. In order to address this error, I would create an `index.html.erb` file in the `/app/views/artists` directory and then populate that file with the html and embedded ruby code necessary to display all artists in the Tunr app.

```

### Question 2

Consider this file name:

```
20150726145027_create_artists.rb
```

What is the purpose of this file, and what is the purpose of the numbers at the beginning of its name?

```text

This file is a migration, and it exists in the `db/migrate/` directory. Migrations allow us to alter the database schema for our application, as the `schema.rb` file should never be altered directly. Migrations tell Active Record how to modify the schema for the database (and the database itself) by adding or removing tables, columns, and entries in the database. The numbers at the beginning of the filename are a timestamp, because each migration is unique and should only be run once—this is important for prevention of data loss in the application.

```

### Question 3

In a Rails application, how is the router related to controller actions?  

```text

The routes in a given Rails application specify the route name (prefix), the HTTP verb used, the path (URL), and the controller action associated with that exact route (e.g., in Tunr, "POST   /artists(.:format)   artists#create"). The route tells us exactly which controller action will be activated by that route.

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
- ...model method.
- ...controller method.
- ...helper method.

```text
Your answer...
```

### Question 7

You clone yet another Tunr repo. Put the following commands in the correct order necessary to make the app run. Delete the one command that will not be used.

```
$ rake db:drop
$ rake db:create
$ rails new . -d postgresql
$ bundle install
$ git clone git@github.com:ga-wdi-exercises/moar-tunr.git
$ rake db:migrate
$ rails s
$ rake db:seed
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
Your answer...
```

### Question 9

What are two differences between the two following commands?

```
$ rails new tunr
$ rails new . -d postgresql
```

```
Your answer...
```

### Question 10

Which **one** of the following is the most correct way to display an error message to the user?

```rb
[] @error = "Wrong password!"
[] puts "Wrong password!"
[] flash[:alert] = "Wrong password!"
[] session[:error] = "Wrong password!"
[] render error: "Wrong password!"
[] flash[:notice] = "Wrong password!"
```
