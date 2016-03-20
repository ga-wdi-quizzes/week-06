# Week 06

### Question 1

You're working on your Tunr app and you encounter this error. What does it mean and where would you go first to address it?  

![Rails error](http://i.imgur.com/9NR7XNT.png)  

```text
Rails errors are great! This one right off the bat is showing me in the big red header that a template is missing, which means I probably don't have a view set up. In this instance, more text shows me that artists/index is missing. I would navigate over the the views folder in rails and create an index.html.erb file in the artists subfolder. After that, refresh the page and see if I get a new error.
```

### Question 2

Consider this file name:

```
20150726145027_create_artists.rb
```

What is the purpose of this file, and what is the purpose of the numbers at the beginning of its name?

```text
This is a migration file with a timestamp stating when the file was created. A migration file allows you to manipulate tables in the database - it looks like in this file is creating the table for artists. In the file we can specify what columns are in the table and what SQL data types can go into those columns.
```

### Question 3

In a Rails application, how is the router related to controller actions?  

```text
A router takes the request from the client (i.e. get, post, etc) and sends it to the controller. The controller should then have a specific method related to that route and would fire off that method if valid.
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
I think the answer here is a helper method. Model methods would be related to the database, and we don't want to change any data - just how it's displayed in the browser. I think you could probably achieve the text color manipulation via a controller method, but based on some of our classes I think we want to keep the controller 'skinny'. By the process of elimination, I think helper methods are the way to go - so there would be some methods in the erb file to handle the color based on rating.

> is that where the helper method(s) would be in this case: in the html views?
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
We are attempting to validate embedded ruby tags for something that is expecting html only. Once the page is loaded in the browser, we could then inspect the source and see what html the embedded ruby generated and run that through a validator.
```

### Question 9

What are two differences between the two following commands?

```
$ rails new tunr
$ rails new . -d postgresql
```

```
rails new tunr will created a new folder 'tunr' in whatever directory we are currently in and add all the skeleton rails application files in 'tunr'.
rails new . will add the rails files in the current directory we are in.

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
