# Week 06

### Question 1

You're working on your Tunr app and you encounter this error. What does it mean and where would you go first to address it?  

![Rails error](http://i.imgur.com/9NR7XNT.png)  

```The error is telling us that we are missing a file for the view. Go to the app/views folder within tunr.
```

### Question 2

Consider this file name:

```20150726145027_create_artists.rb
```

What is the purpose of this file, and what is the purpose of the numbers at the beginning of its name?

```This is a migration. They are a feature of Active Record that allow the user to make changes and update their database over time. Migrations allow us to avoid hardcoding schema modifications in pure SQL by using Ruby Domain Specific Language to describe changes to table. The numbers in the file represent the timestamp, which is called for as an attribute in the database table. It order, it stands for Year, Month, Day, Hour, Minute, Second....or UTC YYYYMMDDHHMMSS. For this file, the year is Year 2015, Month is July or 07, Day is 26, Hour is 1400 (2pm), Minute is 50, Second is 27.  
Your answer...
```

### Question 3

In a Rails application, how is the router related to controller actions?  

```The router comes before the controller (it is the gateway to the MVC). The role of the router is to receive an HTTP request and match it to a controller that will carry out the requested action.  
```

### Question 4

Assuming our Tunr Rails app (1) has a Song model that belongs to an Artist model and (2) uses nested resources, which of the following helpers would create a URL that routes to `songs#new`? (Select one answer)  

```
[] artist_song_path( @artist, @song )
[] new_artist_song_path( @artist )
[] create_artist_song_path( @artist )
[] new_artist_song_path( @artist, Song.all )
[x] new_song_path( @song )
```

### Question 5

Where are (a) cookies and (b) session variables stored? (Select one answer)  

```
[] (a) Server, (b) Browser  
[] (a) Browser, (b) Database  
[x] (a) Database, (b) Server  
[] (a) Browser, (b) Server  
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
$ git clone git@github.com:ga-wdi-exercises/moar-tunr.git
$ rails new . -d postgresql
$ bundle install
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

```1. Declare document type <!DOCTYPE html>

```

### Question 9

What are two differences between the two following commands?

```
$ rails new tunr
$ rails new . -d postgresql
```

```'rails new tunr' creates a directory called 'tunr' and will install the gem dependencies that are already mentioned in Gemfile using bundle install. 'rails new . -d postgresql' tells 'tunr' to use postgres as its default database. Otherwise, Rails uses SQLite as a database by default.
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
