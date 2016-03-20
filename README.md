# Week 06 

### Question 1

You're working on your Tunr app and you encounter this error. What does it mean and where would you go first to address it?  

![Rails error](http://i.imgur.com/9NR7XNT.png)  

```text
I am missing an artists view. I need to create an index.html.erb file in the views directory for the "artists" model
```

### Question 2

Consider this file name:

```
20150726145027_create_artists.rb
```

What is the purpose of this file, and what is the purpose of the numbers at the beginning of its name?

```text
This is a "migration" file. It is used to create a new table in the db. Rails keeps track of these migrations with an encrypted date and time code - a "timestamp" so that it can keep track of which migrations it has already run so that it does not duplicate or overwrite data.
```

### Question 3

In a Rails application, how is the router related to controller actions?  

```text
The router gets info from the user who initiates the URL (or clicks on an internal link to a URL) and take that info to the correct controller who will get the relative info and send it to the right view.
```

### Question 4

Assuming our Tunr Rails app (1) has a Song model that belongs to an Artist model and (2) uses nested resources, which of the following helpers would create a URL that routes to `songs#new`? (Select one answer)  

```
[] artist_song_path( @artist, @song )
[x] new_artist_song_path( @artist )
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
I think I'd have to use a helper method. They make some or all of the controller's methods available for use in the view so that would be understanding. Also, this question's examples are hilarious.
```

### Question 7

You clone yet another Tunr repo. Put the following commands in the correct order necessary to make the app run. Delete the one command that will not be used.

```
1. $ git clone git@github.com:ga-wdi-exercises/moar-tunr.git
2. $ bundle install
3. $ rake db:drop
4. $ rake db:create
5. $ rake db:migrate
6. $ rake db:seed
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
ruby "clown hats" will always throw you an error. You have to inspect your html in your browser and validate that because it will render as the code that ruby on rails is subbing out.
```

### Question 9

What are two differences between the two following commands?

```
$ rails new tunr
$ rails new . -d postgresql
```

```
the first one, "rails new tunr" will create a separate nested directory inside the folder you are in. It will also default to using Sqlite3 rather than postgres which could be an issue as we don't work with it in this course. The second example will create all your rails folders inside whatever directory you are currently in which eliminates the whole "tunr within a tunr folder" issue. Writing "-d postgresql" will set the db to use postgres.
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
