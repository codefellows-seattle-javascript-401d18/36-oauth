![cf](https://i.imgur.com/7v5ASc8.png) 36: OAuth
======

## Submission Instructions
* fork this repository & create a new branch for your work
* write all of your code in a directory named `lab-` + `<your name>` **e.g.** `lab-susan`
* push to your repository
* submit a pull request to this repository
* submit a link to your PR in canvas
* write a question and observation on canvas

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