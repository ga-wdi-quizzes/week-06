# Week 06

### Question 1

You're working on your Tunr app and you encounter this error. What does it mean and where would you go first to address it?  

![Rails error](http://i.imgur.com/9NR7XNT.png)  

```text
Rails is looking for an HTML template .  The solution is to create a file named `index.html.erb` in the application's `app/views/artists` folder and put the necessary HTML code in it.
```

### Question 2

Consider this file name:

```
20150726145027_create_artists.rb
```

What is the purpose of this file, and what is the purpose of the numbers at the beginning of its name?

```text
It is a migration file to be processed by the rake command.  When run, it will modify something in the artists table of the database.  The numbers at the beginning of the file are a date stamp; the `rake db:migrate` command runs the migration files in chronological order based on the date stamp, oldest to newest.  This is done to make sure that database modifications can be rerun or rolled back as needed.    
```

### Question 3

In a Rails application, how is the router related to controller actions?  

```text
The router matches an HTTP request to a controller and action.  When the controller receives a request from the application, it uses the routes defined in the router to determine which folders to go to to perform which actions.  
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
Probably a helper, since it would only be called when the page is being rendered.  If it were in the model or controller it would be called more often, but not executed, which still burns cycles.  
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

Deleted:
$ rails new . -d postgresql

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
The ERB file is a template used by Rails to generate HTML.  The tags ('<%' and '%>') are used to insert data from a database when Rails generates the final HTML, and the HTML validator is rejecting them.  In order to verify the HTML you'd have to run the website, connect to the page with Chrome, view the source code in Chrome, then copy and paste the the source code from Chrome to the validator.   
```

### Question 9

What are two differences between the two following commands?

```
$ rails new tunr
$ rails new . -d postgresql
```

```
`rails new tunr` will create a new folder named `tunr` and build a new Rails appliction structure in that folder using the default settiings.  

`rails new . -d postgresql` will create a new Rails application structure in the existing folder and configure it to use postgresql rather than the default database engine (sqlite3).
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
