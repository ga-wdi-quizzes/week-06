# Week 06

### Question 1

You're working on your Tunr app and you encounter this error. What does it mean and where would you go first to address it?  

![Rails error](http://i.imgur.com/9NR7XNT.png)  

```text
I would go to the index files and search for an artists index file. The error is saying there is a missing artists/index file. It would be an .html.erb file.
```

### Question 2

Consider this file name:

```
20150726145027_create_artists.rb
```

What is the purpose of this file, and what is the purpose of the numbers at the beginning of its name?

```text
The file is a migrate file- it appears when you command rails migration and adds a new table to the database. The numbers are timestamps for the computer to know when the tables were created and prevent doubles from occurring and deleting information from the database.
```

### Question 3

In a Rails application, how is the router related to controller actions?  

```text
The actions or steps in the controller file are dictated by the routes file. Each controller action has a specific route from the router.
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
I would use a helper method because typically helper methods are used when you need to alter some complicated HTML, such as the average rating of a particular song changing colors depending upon the rating. Also, because when you want to change the presentation (color) of data that is not stated in the database, as in this case where the color of the rating is not specified in the database and relates to the data but does not directly impact the data.  

 answer...
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
The clown hat tags that are seen in erb files are not recognized by HTML and would show up as errors.  You could remove the clown hat tags in the HTML validator so the errors don't appear.
```

### Question 9

What are two differences between the two following commands?

```
$ rails new tunr
$ rails new . -d postgresql
```

```
The first command just created a new rails folder named tunr, whereas the second command creates a rails file called tunr and installs all necessary files for the application to run in postgresql. The second command also connects to using the postgresql database and includes the code that the postgresql database requires to run. The " . " in the second command also means that it will be created within an existing directory, preventing a file to be created within another file. ```

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
