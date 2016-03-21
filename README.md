![Rails error](http://i.imgur.com/9NR7XNT.png)  

  ```text
 -Your answer...
 index files and search for an artists index file. The error is saying there is a missing artists/index file. It would be an .html.erb file.
  ```

  ### Question 2

@@ -21,7 21,7 @@ Consider this file name:
  What is the purpose of this file, and what is the purpose of the numbers at the beginning of its name?

  ```text
 -Your answer...
 The file is a migrate file- it appears when you command rails migration and adds a new table to the database. The numbers are timestamps for the computer to know when the tables were created and prevent doubles from occurring and deleting information from the database.
  ```

  ### Question 3

@@ -29,7 29,7 @@ Your answer...
  In a Rails application, how is the router related to controller actions?  

  ```text
 -Your answer...
 The controller file are dictated by the routes file. Each controller action has a specific route from the router.
  ```

  ### Question 4

@@ -37,11 37,11 @@ Your answer...
  Assuming our Tunr Rails app (1) has a Song model that belongs to an Artist model and (2) uses nested resources, which of the following helpers would create a URL that routes to `songs#new`? (Select one answer)  

  ```
 [] artist_song_path( @artist, @song )
 [] new_artist_song_path( @artist )
 [] artist_song_path( @artist, @song )
 [X] new_artist_song_path( @artist )
  [] create_artist_song_path( @artist )
  [] new_artist_song_path( @artist, Song.all )
 [] new_song_path( @song )
 [] new_song_path( @song )
  ```

  ### Question 5

@@ -52,7 52,7 @@ Where are (a) cookies and (b) session variables stored? (Select one answer)
  [] (a) Server, (b) Browser  
  [] (a) Browser, (b) Database  
  [] (a) Database, (b) Server  
 [] (a) Browser, (b) Server  
 [X] (a) Browser, (b) Server  
  ```

  ### Question 6

@@ -71,7 71,9 @@ This code would make most sense as a...
  - ...helper method.

  ```text
 -Your answer...
helper methods are used when you need to alter some complicated HTML, such as the average rating of a particular song changing colors depending upon the rating. Also, because when you want to change the presentation (color) of data that is not stated in the database, as in this case where the color of the rating is not specified in the database and relates to the data but does not directly impact the data.  

  answer...
  ```

  ### Question 7

@@ -79,14 81,13 @@ Your answer...
  You clone yet another Tunr repo. Put the following commands in the correct order necessary to make the app run. Delete the one command that will not be used.

  ```
 $ git clone git@github.com:ga-wdi-exercises/moar-tunr.git
 $ bundle install
  $ rake db:drop
  $ rake db:create
  $ rails new . -d postgresql
  $ bundle install
  $ rake db:migrate
  $ rails s
  $ rake db:seed
 $ rails s
  ```

  ### Question 8

@@ -104,7 105,7 @@ You're a good person and decide to validate your HTML. You copy and paste the co
  The validator throws errors at you! Why? Assuming you haven't made any mistakes in your code, how could you go about accurately validating your HTML?

  ```
 -Your answer...
 The clown hat tags that are seen in erb files are not recognized by HTML and would show up as errors.  You could remove the clown hat tags in the HTML validator so the errors don't appear.
  ```

  ### Question 9

@@ -117,8 118,7 @@ $ rails new . -d postgresql
  ```

  ```
 -Your answer...
 -```
 The first command just created a new rails folder named tunr, whereas the second command creates a rails file called tunr and installs all necessary files for the application to run in postgresql. The second command also connects to using the postgresql database and includes the code that the postgresql database requires to run. The " . " in the second command also means that it will be created within an existing directory, preventing a file to be created within another file. ```

  ### Question 10


@@ -127,9 127,8 @@ Which **one** of the following is the most correct way to display an error messa
  ```rb
  [] @error = "Wrong password!"
  [] puts "Wrong password!"
 -[] flash[:alert] = "Wrong password!"
 [X] flash[:alert] = "Wrong password!"
  [] session[:error] = "Wrong password!"
  [] render error: "Wrong password!"
  [] flash[:notice] = "Wrong password!"
  ```
 -
