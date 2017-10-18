![cf](https://i.imgur.com/7v5ASc8.png) 36: OAuth
======
#### Project description:

This is practice using Google OAuth by creating a simple index.html front end that includes a script that will give out an href anchor tag with all the attributes necessary to produce browser cookies.

#### Terminal scripts:

- Backend:
Two windows, one for nodemon and one for mongodb.
```
mongod --dbpath ./db
```
- Frontend:
Right click- 'Open in Browser'

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
Maddie, Michelle, Isaac, Tim.
