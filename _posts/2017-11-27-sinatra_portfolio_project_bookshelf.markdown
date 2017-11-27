---
layout: post
title:      "Sinatra Portfolio Project: bookshelf "
date:       2017-11-27 17:26:37 +0000
permalink:  sinatra_portfolio_project_bookshelf
---


With this project, I wanted to make an app that can be used to keep track of a user’s books. To do this I first need to be able to create a book class that would belong to an author class as well as a genre class. Then I made a database to store the values for these classes in. The author class will have many books as well has many genres through books. While the genre class will have many books as well as many authors through books. After this was set up the user class had to be added. The user will have many books but a book can also have many users. To account for this a join table was made or the two classes. After the models and database was set up it was time to start on the controllers and views.
	On the views and controllers, I like to start where the user will start (the homepage). From the homepage, the first part that we completed we the sign in and sign up function. After they were completed links we added to the home page so that someone for easy navigation. Error messages were also added so that someone can know what went wrong with their login or sign up attempt. 
	Once the sign in function was properly working the next part was to allow the user to add a book to their list. Separate pages were added for a new book, to edit a book, a list of all books in the database, and to remove a book from the user’s list. Each of these files presented their own challenge. For creating a new I had to make sure the user had to fill out each field. On the edit page, I had to make sure the user could only edit a book object they created. For the remove page, I had to make sure someone couldn’t delete a book that they didn’t create. For the list of all books I had to make sure the user didn’t already have that book in their list before giving them the option of adding it to their list.
	After the book views and controller, I had to make a smaller one for an authors and genres. These were made so the user can look a book by genre or ay author.
	This project ended up be much longer than I had originally though it would be. There were a lot of small details that needed to be add so that it would work correctly. I didn’t put much time into making the web pages look neat. I am a little rusty on HTML and CSS so I might want to come back to this project in the future and use it to practice. But for now, it works so I can wait on making it look better.

https://github.com/jstooley/bookshelf.git

