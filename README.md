# Week 06

### Question 1

You're working on your Tunr app and you encounter this error. What does it mean and where would you go first to address it?  

![Rails error](http://i.imgur.com/9NR7XNT.png)  

```text
it means you are missing an a view template . this one would be the view index file. you would created an a directory and and file in the terminal.
$ mkdir app/views/artists
$ touch app/views/artists/index.html.erb
```

### Question 2

Consider this file name:

```
20150726145027_create_artists.rb
```

What is the purpose of this file, and what is the purpose of the numbers at the beginning of its name?

```text
This a migration file it is used to modify the scheme file It can adding and deleting data  from schema. The numbers in the beginning are a timestamp they are use to know which migration runs first.
```

### Question 3

In a Rails application, how is the router related to controller actions?  

```text
The router matches an HTTP request to a controller and action.
Returns an error if the HTTP request is unrecognizable and/or does not match a controller action.
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
I would code as a model method because it dealing with song model . you would use controller methods only for logic not function you want to keep controller skinny.
```

### Question 7

You clone yet another Tunr repo. Put the following commands in the correct order necessary to make the app run. Delete the one command that will not be used.

```
3.$ rake db:drop
4.$ rake db:create
$ rails new . -d postgresql (you do not need this because you are not starting app from scratch)
2.$ bundle install
1.$ git clone git@github.com:ga-wdi-exercises/moar-tunr.git
5.$ rake db:migrate
7.$ rails s
6.$ rake db:seed
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
You also have ruby syntax in the html code . you could use a form validator for ruby.
```

### Question 9

What are two differences between the two following commands?

```
1.$ rails new tunr
2.$ rails new . -d postgresql
```

```
Number 1 you are just making a new rails file and number 2 you are saying you import all the file needed to make a rails file also you are telling your computer you will be using postgresql
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
