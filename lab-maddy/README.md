![cf](https://i.imgur.com/7v5ASc8.png) 36: OAuth
======
#### Project description:

This is practice using Google OAuth by creating a simple index.html front end that includes an href anchor tag with all the attributes necessary to produce browser cookies.

#### Checklist for this lab:

1. Enable the google plus API for this project in the dashboard, big blue button.
2. After consent I am redirected back to my frontpage app
3. I am able to call document.cookie and I get a slugchat cookie
4. I am able to search my mongo shell database for me as a user object

#### Terminal scripts:

- Backend:
Two windows, one for nodemon and one for mongodb.
```
mongod --dbpath ./db
```
- Frontend:
Right click- live-server index.html

1. From: https://developers.google.com/identity/protocols/OAuth2UserAgent

```
https://accounts.google.com/o/oauth2/v2/auth?
 scope=https%3A%2F%2Fwww.googleapis.com%2Fauth%2Fdrive.metadata.readonly&
 include_granted_scopes=true&
 state=state_parameter_passthrough_value&
 redirect_uri=http%3A%2F%2Foauth2.example.com%2Fcallback&
 response_type=token&
 client_id=client_id
After you create the request U
```

2. In one terminal window, navigate to the backend, start node by typing:
```
nodemon
```
Should see:
```
^C17:37 ~/codefellows/401/week9/36-oauth/lab-maddy/slugchat-backend [maddy-mon !?] nodemon
[nodemon] 1.12.1
[nodemon] to restart at any time, enter `rs`
[nodemon] watching: *.*
[nodemon] starting `node index.js`
__MONGO_CONNECTED__ mongodb://localhost/slugchat-dev
__SERVER_UP__ 3000
```
3. In a second terminal window, navigate to the backend, start mongodb by typing:
```
mongod --dbpath ./db

```

4. After all goals have been met, double check your work. In the mongo shell I am able to see that I have a user in my database with the following scripts:
```
> show dbs
admin         0.000GB
local         0.000GB
slugchat-dev  0.000GB
> use slugchat-dev
switched to db slugchat-dev
> show collections
users
> show users
> db.users.find()
> show users
> db.users.find()
{ "_id" : ObjectId("59e6537c1cd1ce33c34b4b8c"), "username" : "Madeline_Stevens", "email" : "stevensm1987@gmail.com", "tokenSeed" : "qZT4HUJ9OsDWs28mosKG/aG/e5zF2aEqmK6Btnx9DBc=", "__v" : 0 }
```



## Learning Objectives
* students will be able to add Google OAuth to a MERN stack application

## Requirements

#### Configuration  
* create a copy of the slugchat-backend-starter-code to `/lab-<yourname>/slugchat-backend`
* create a `/lab-<yourname>`/slugchat-fontend directory

#### Feature Tasks
* following along with today's lecture and create:
  * a simple `index.html` file that builds a dynamic google signin url
  * a `handleOAuth` static `User` method that checks the profile data provided by Google Open ID
  * a `get` route to your custom redirect URI (ex: /google/oauth/code) that contains all subsequent "handshake" requests
    * this should provide a token that can be used to get profile details from Google Open ID
    * if a profile does not exist through Google, your final request should create a guest user

#### Optional - React Frontend
* create a token reducer for managing a token
* create an auth action's file for:
  * making signup and login requests
  * storing and clearing the token in the app state
  * **remember:** remove the cookie when the token is removed from the app state
* create the following frontend route/component:
  * `/landing` - display a "login with google" anchor
  * this google anchor should work as described above in the "Feature Tasks" section
  * after the auth handshake is completed, the user should be redirected to another part of the app (since a token is now saved to their browser cookies)

#### Collaborators:
Michelle, Said, Isaac, Gavin.
