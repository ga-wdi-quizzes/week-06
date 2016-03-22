# Week 06

### Question 1

You're working on your Tunr app and you encounter this error. What does it mean and where would you go first to address it?  

![Rails error](http://i.imgur.com/9NR7XNT.png)  

```text
you need to create an index.html.erb file in your views/artists folder
```

### Question 2

Consider this file name:

```
20150726145027_create_artists.rb
```

What is the purpose of this file, and what is the purpose of the numbers at the beginning of its name?

```text
that is the migration file to create a table titled "artists"
the numbers represent the migration id. This allows you to refer to that migration at any time and tracks the progress of our table
```

### Question 3

In a Rails application, how is the router related to controller actions?  

```text
the router defines the CRUD within our app. It allows us to create, read, update, and delete. This CRUD creates six verbs that correlates to our controller.

Get => #index
Get => #new
Post => #creates
Get => #show
Get => #edit
Patch/Put => #update
Delete => #destroy

each of these "verbs" must defined in our controller so requests brought in by the router knows what to do for each.
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
[x] (a) Browser, (b) Database  
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
I believe the code would have to be placed into the model. I say this because your controller should by as DRY as possible, only with the necessary RESTful attributes. A helper method is written for the view but from my understanding, any method that will be long and deals with the behavior of an object should go in the model. You would right a method title ratings and define how you want that method to behave in the inside. You can call this method anywhere within the application without making the controller or view cluttered. Keeping the controller and view files clean and easier for the router to read.
```

### Question 7

You clone yet another Tunr repo. Put the following commands in the correct order necessary to make the app run. Delete the one command that will not be used.

```

rails new . -d postgresql
bundle install
rake db:drop
rake db:create
rake db:migrate
rake db:seed
rails s

It said it was already cloned so I'm assuming that part was done. Also, because there were other versions, since this isn't the first Tunr, you would have to drop the previous tables.

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
validates :name :presence => true
```

### Question 9

What are two differences between the two following commands?

```
$ rails new tunr
$ rails new . -d postgresql
```

```
rails new tunr will create a new rails app within a directory named tunr without postgresql

rails new . -d postgresql will create a new rails app within the current directory with postgresql
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
