# Week 06

### Question 1

You're working on your Tunr app and you encounter this error. What does it mean and where would you go first to address it?  

![Rails error](http://i.imgur.com/9NR7XNT.png)  

```text
That requires creating a file named index.html.erb in opp/views/artists. The file could presumably be empty,
but would probably contain simple text at a minimum, "vanilla" html, or HTML enhanced with Ruby. 
```

### Question 2

Consider this file name:

```
20150726145027_create_artists.rb
```

What is the purpose of this file, and what is the purpose of the numbers at the beginning of its name?

```text
The file is a database migrate file that specifies the strcuture of an artists table using Ruby syntax. 
It's called a migrate file because Ruby handles the differences between databases, so a Ruby app can 
easily migrate from one "brand" of database to another.

The numbers are a timestamp, indicating the file was "born" on 26 July 2015 at 2:50:27 PM. 
I'm not really sure why Ruby thinks that fie in particular needs a time stamp, as opposed 
to any other file.
```

### Question 3

In a Rails application, how is the router related to controller actions?  

```text
The router sends a request to the appropriate controller, with the request coming in the form of the URL requested. 
```

### Question 4

Assuming our Tunr Rails app (1) has a Song model that belongs to an Artist model and (2) uses nested resources, which of the following helpers would create a URL that routes to `songs#new`? (Select one answer)  

```
[] artist_song_path( @artist, @song ) 
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
$ bundle install
$ rails new . -d postgresql
$ rake db:create
$ rake db:migrate
$ rake db:seed
$ rails s

`rake db:drop` ia not needed, since there is no existing database to drop. It would be like the Skipper yelling, 
"Gilligan! Drop those coconuts!" when Gilligan didn't have any coconuts. Hijinks might ensue, and Ruby on Rails 
is known to have issues with hijinks. 

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

