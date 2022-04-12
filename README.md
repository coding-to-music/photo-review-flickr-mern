# photo-review-flickr-mern

This is API's only, there is no working frontend.

Test the API's in Postman.

# 🚀 Javascript full-stack 🚀

## MERN Stack

### React / Express / MongoDB / Redux

https://github.com/coding-to-music/photo-review-flickr-mern

https://photo-review-flickr-mern.herokuapp.com

by amrilazhar https://github.com/amrilazhar

https://github.com/amrilazhar/photo_review

# AZH Browse & Photo Review

This is a simple backend API for browsing and giving review (locally) about photos, from flickr and unplash.

## Feature

1. Basic Authentication (using JWT)
2. Browse and Searc Photo from Flickr and Unsplash
3. Giving Review to Photo
4. Update Our Profile
5. Add Photo to Our Favorite Collection

## Instalation

To Install the API there is some requirement that we need to meet,

1. Mongo DB database (local / atlas)
2. NodeJS Server
3. Flickr API Key (it can be access here [Flicker](https://www.flickr.com/services/api/), but need register first)
4. Unsplash API Key (it can be access here [Unsplash](https://unsplash.com/developers), but need register first)

To install the App just clone it, and run `npm install` inside the project folder, then we need to create file `.env.development` with format like this :

```
UNSPLASH_ACCESS_KEY = <key>
UNSPLASH_SECRET_KEY = <key>
JWT_SECRET = <jwt secret>
PUBLIC_URL = https://localhost (you can change it)
MONGO_URI = <uri>
FLICKR_API_KEY = <key>
FLICKR_SECRET_KEY = <key>
```

To run the code just type `npm run dev`

# DB Diagram

Here the database design, which consist of 3 tables :

![databae](./public/data_diagram.PNG)

# Unit Test

For ensure code stability when there are change in the code, we conduct a unit test,
this is the result :

![unit_test](./public/unit_test.PNG)

- **note : full report of the test can be seen in `./coverage/Icov-report/index.html`**

# Full Documentation

Full documentation and how to use can be seen here : https://documenter.getpostman.com/view/15024355/TzeTJUbG

## GitHub

```java
git init
git add .
git remote remove origin
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:coding-to-music/photo-review-flickr-mern.git
git push -u origin main
```

## Heroku

```java
heroku create photo-review-flickr-mern
```

## Heroku MongoDB Environment Variables

```java
heroku config:set

heroku config:set MONGODB_URI="mongodb+srv://<userid>:<password>@cluster0.zadqe.mongodb.net/photo-review-flickr-mern?retryWrites=true&w=majority"
heroku config:set SECRET_JWT="something-secret"

heroku config:set PUBLIC_URL="https://photo-review-flickr-mern.herokuapp.com"
```

## Push to Heroku

```java
git push heroku

# or

npm run deploy
```

### Heroku Buildpack

See this repo for more info about setting up a node/react app on heroku:

https://github.com/mars/heroku-cra-node

```java
heroku buildpacks

heroku buildpacks --help

heroku buildpacks:clear

```

```java
heroku buildpacks
```

Output:

```java
=== photo-review-flickr-mern Buildpack URL
heroku/nodejs
```

### Notice we are doing a SET and then and ADD

```java
heroku buildpacks:set heroku/nodejs

heroku buildpacks:add mars/create-react-app
```

Output:

```java
Buildpack added. Next release on photo-review-flickr-mern will use:
  1. heroku/nodejs
  2. mars/create-react-app
Run git push heroku main to create a new release using these buildpacks.
```

### Lets try reversing the order

```java
heroku buildpacks:set mars/create-react-app

heroku buildpacks:add heroku/nodejs
```

```java
heroku buildpacks
```

Output:

```java
=== photo-review-flickr-mern Buildpack URL
heroku/nodejs
```

### Push to Heroku

```
git push heroku
```

## Error:

```java
2022-04-09T03:12:56.076028+00:00 app[web.1]: ls: cannot access '/app/build/static/js/*.js': No such file or directory
2022-04-09T03:12:56.076252+00:00 app[web.1]: Error injecting runtime env: bundle not found '/app/build/static/js/*.js'. See: https://github.com/mars/create-react-app-buildpack/blob/master/README.md#user-content-custom-bundle-location
2022-04-09T03:12:56.253505+00:00 app[web.1]: Starting log redirection...
2022-04-09T03:12:56.253698+00:00 app[web.1]: Starting nginx...
```

Attempted this:

```java
heroku config:set JS_RUNTIME_TARGET_BUNDLE=./client/build/static/js/*.js

heroku config:set JS_RUNTIME_TARGET_BUNDLE=/build/static/js/*.js

# and to remote it:

heroku config:unset JS_RUNTIME_TARGET_BUNDLE

```

## update npm packages

```java
npm install -g npm-check-updates
```

Output:

```java
removed 3 packages, changed 263 packages, and audited 264 packages in 10s

29 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
```

```java
ncu -u
```

Output:

```java
Upgrading /mnt/volume_nyc1_01/photo-review-flickr-mern/package.json
[====================] 15/15 100%

 axios                ^0.21.0  →  ^0.26.1
 bcrypt                ^5.0.0  →   ^5.0.1
 body-parser          ^1.19.0  →  ^1.20.0
 cookie-parser         ^1.4.5  →   ^1.4.6
 dotenv                ^8.2.0  →  ^16.0.0
 express              ^4.17.1  →  ^4.17.3
 express-fileupload    ^1.2.0  →   ^1.3.1
 js-cookie             ^2.2.1  →   ^3.0.1
 mongoose            ^5.10.13  →  ^6.2.10
 nodemon               ^2.0.6  →  ^2.0.15
 reactjs-popup         ^2.0.4  →   ^2.0.5
 validator           ^13.1.17  →  ^13.7.0

Run npm install to install new versions.
```

```java
npm install
```

Output:

```java
added 58 packages, removed 42 packages, changed 89 packages, and audited 299 packages in 7s

32 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
```

## Client directory

```java
cd client

ncu -u
```

```java
Upgrading /mnt/volume_nyc1_01/photo-review-flickr-mern/client/package.json
[====================] 18/18 100%

 @testing-library/jest-dom     ^5.11.4  →  ^5.16.4
 @testing-library/react        ^11.1.0  →  ^13.0.0
 @testing-library/user-event  ^12.1.10  →  ^14.0.4
 axios                         ^0.21.0  →  ^0.26.1
 dotenv                         ^8.2.0  →  ^16.0.0
 js-cookie                      ^2.2.1  →   ^3.0.1
 node-sass                     ^4.14.1  →   ^7.0.1
 react                         ^17.0.1  →  ^18.0.0
 react-dom                     ^17.0.1  →  ^18.0.0
 react-redux                    ^7.2.2  →   ^7.2.8
 react-router-dom               ^5.2.0  →   ^6.3.0
 react-scripts                   4.0.0  →    5.0.0
 reactjs-popup                  ^2.0.4  →   ^2.0.5
 redux                          ^4.0.5  →   ^4.1.2
 redux-thunk                    ^2.3.0  →   ^2.4.1
 web-vitals                     ^0.2.4  →   ^2.1.4

Run npm install to install new versions.
```
