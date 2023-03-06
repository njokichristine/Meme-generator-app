Meme Generator App
The Meme Generator is a server-side API built using Ruby's Sinatra DSL, as part of the Moringa School Phase-3 project. The API follows the MVC design pattern, and it provides a backend for a React-based frontend. The API supports all CRUD operations, including POST, DELETE, and PATCH, as well as authentication for secure user access.

Here are the links to the repositories and the live link to the project:

Frontend repository
Backend repository
Live link
Pre-Requisites
In order to use this repository you will need the following:

Operating System (Windows 10+, Linux 3.8+, or MacOS X 10.7+)
RAM >= 4GB
Free Space >= 2GB
Built With
This application has been built with the following tools:

ruby sqlite

Ruby v2.7.+
SQlite3 v1.6
ActiveRecord v7.0.4
Rake v13.0.6
Puma v6.1
rerun v0.14
Sinatra v3.0.5
Setup
You can setup this repository by following this manual

Clone the repository
git clone git@github.com:njokichristine/meme-generator.git
Ensure the ruby gems are setup in your machine
bundle install
Perform any pending database migrations
rake db:migrate
Run the application
rake start
Open the application from your browser
http://localhost:9292
Application
This application is a simple web API that allows users to:

Register a new account.
Log in to existing account.
Create Memes.
Update individual memes.
View all memes.
Filter memes by title.
Delete individual meme.
MODELS
Database schema definitions.

TODO
COLUMN	DATA TYPE	DESCRIPTION
id	Integer	Unique identifier.
title	String	The first part of meme (intro)
message	String	second part of meme (punchline)
updated_at	Date	The date the user was updated.
createdAt	Date	The date the user was created.
USER
COLUMN	DATA TYPE	DESCRIPTION
id	Integer	Unique identifier.
username	String	User's username
email	String	User's email
password_hash	String	User's password hashed with BCrypt.
updated_at	Date	The date the user was updated.
createdAt	Date	The date the user was created.
ROUTES
/users - Create a new user account.

## REQUEST BODY
{
 "username": "John Doe",
 "email": "mail@mail.com",
 "password": "12345678"
}
login - Log in a user using username and password.

## REQUEST BODY
{
 "username": "John Doe",
 "password": "12345678"
}
/users/:user_id/memes - Add a new TODO item.

## REQUEST BODY
{
 "title": "What did the zero say to the eight?",
 "message": "That belt looks good on you."
}
/memes - List all memes.

## RESPONSE SAMPLE
{
   "memes": [
  {
   "id": 26,
   "title": "How does the moon cut his hair?",
   "message": "Eclipse it",
   "user_id": 6,
   "created_at": "2023-03-05T07:00:16.885Z",
   "updated_at": "2023-03-05T07:00:16.885Z",
   "user": {
     "username": "eva"
   }
 ]
}
/users/:id/memes/:meme_id - Update an existing and users meme.

/memes/:id/users/:user_id - Delete a TODO item.