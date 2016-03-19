# Week 06

### Question 1

You're working on your Tunr app and you encounter this error. What does it mean and where would you go first to address it?  

![Rails error](http://i.imgur.com/9NR7XNT.png)  

```text
This error means that no view has been created for artists#index. I would go to app/views/artists and create an index.html.erb file to fix this error.
```

### Question 2

Consider this file name:

```
20150726145027_create_artists.rb
```

What is the purpose of this file, and what is the purpose of the numbers at the beginning of its name?

```text
This is a migration file that specifies the properties of the attribute columns of the artist table in the database. For example, this file would contain columns such as name:string and nationality: string. Upon running, rake db:migrate, the file would input those columns into the artist table. The numbers at the beginning are a timestamp of when this migration file was created, so the all the files will be listed out chronologically in your repo.
```

### Question 3

In a Rails application, how is the router related to controller actions?  

```text
The router determines which controller the request should be directed to. For example, if the user wants to go to /artists, the router would guide the request to the ArtistsController. If the user wants to go to songs/1, the router would guide the request to the SongsController.
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
The code would make most sense as a MODEL method, as it would be a proper separation of concerns. The controller is the coordinator that takes parameters and returns HTML, but it should not be making business logic decisions such as determining the average rating of a song. We would create an avq_rating method in the song model that can then be called in the SongsController and display the HTML/CSS for the appropriate color.
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
Delete ($ rails new . -d postgresql) because since we cloned down the app, we do not need to create a new app.
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
The HTML validator cannot properly read embedded Ruby html files (i.e. index.html.erb). Instead, load the page in your web browser, right click, select `View Page Source`, and copy the HTML from that into your generator.
```

### Question 9

What are two differences between the two following commands?

```
$ rails new tunr
$ rails new . -d postgresql
```

```
The first command makes a directory called tunr and includes all of the rails folders/files in it. It also uses a SQLite database by default. The second command creates all the rails folders/files within whatever directory you are presently in. It also connects this app to a postgresql database.
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
