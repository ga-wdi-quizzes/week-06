# Week 06

### Question 1

You're working on your Tunr app and you encounter this error. What does it mean and where would you go first to address it?  

![Rails error](http://i.imgur.com/9NR7XNT.png)  

```text
Missing template artist/index
app/views/artists/ create index.html.erb (or make sure the name is spelled right)
```

### Question 2

Consider this file name:

```
20150726145027_create_artists.rb
```

What is the purpose of this file, and what is the purpose of the numbers at the beginning of its name?

```text
The name of the migration file stored in the db/migrate directory in the form YYYYMMDDHHMMSS_create_artists.rb, a timestamp identifying the migration followed by an underscore followed by the name of the migration in this case create_artists.rg  defines class CreateArtists  The timestamp  determines which migration should be run and in what order. Migrations are a feature of Active Record that allows you to evolve your database schema over time, migrations allow you to use an easy Ruby DSL to describe changes to your tables.
```

### Question 3

In a Rails application, how is the router related to controller actions?  

```text
When an HTTP request arrives from the user's browser, it needs to know which controller action (method) should be run. Should we display the "new user" webpage? Should we edit an existing user with whatever data got sent along?

The Router is basically just a matching service. It looks at the HTTP verb (GET, POST, PUT, DELETE) and the URL that it being requested and matches it with the appropriate controller action to run. If it can't find a route that matches the request, your application will throw an error.

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
"Fat Models, Skinny Controllers"

Namely, any non-response-related logic should go in the model. The “skinny” controller is simply a nice interface between the view and model.

sorry I know you said not to but why wouldn't you just?


a<% if song.avg_rating < 5  %>
    <td class="red"><%= song %></td>
<% elsif song.avg_rating < 10 %>
    <td class="yellow"><%= song %></td>
<% else %>
    <td class="green"><%= song %></td>
<% end %>

AND this was too confusing for me to figure out

TagHelper - in theory if i could figure out how these work they would do the trick.
TagHelper may be of use when you want to create explicit XHTML markup using ERb templates, or want to create view logic that lets the data determine which markup is used. On the one hand, these methods are somewhat obscure ans difficult to figure out; on the other, they may be exactly what you need if clean XHTML is your goal:

content_tag
The content_tag method is a generic tag building method. You define the name of the tag, the attributes, and the content of the tag through the arguments.
```

### Question 7

You clone yet another Tunr repo. Put the following commands in the correct order necessary to make the app run. Delete the one command that will not be used.

```


$ git clone git@github.com:ga-wdi-exercises/moar-tunr.git
added this it wasn't there $ cd moar-tunr
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
put in your own validation:

open index.html.erb - can now embed ruby code
<%= execute this ruby code and print it in html
links to artist conroller will look for actionname.html.erb


create index.html.erb

<%= @artists.inspect %>  now know that artists is full of info = execute code and print

<% @artists.each do |artist| %> no equal so no giberish
 <li> %= artist.inspect %></li>
 change this line to
 <li> %= artist.name %></li> get it by inheriting from active record base artist.rb
<% end %>
</ul>
```

### Question 9

What are two differences between the two following commands?

```
$ rails new tunr
$ rails new . -d postgresql
```

```
The command will create a new Rails app. using sqlite3 by default
The -d postgresql tells Rails to create a new app using postgresql
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
