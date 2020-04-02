# comments-profile
Creating a comments/profile section for our App

In order to initiate the application, follow these simple steps:

1) npm install to add all necessary dependencies
2) npm run build:react
3) npm run server:dev
4) check brew services and make sure mongodb is running
5) if mongodb is not running, brew services start mongodb-community
6) npm run seed 
    this will seed all data into your database
7) go to localhost:4000 to view app


# CRUD API

Intention | Request Type | Request URL | Example Input | Response Body
--------- | ------------ | ------------ | ------------ | ----------- |
Get info for a song| GET | /songs/:songId | none | {plays: 302, likes: 43, reposts: 69, follows: 12, tracks: 32}
Get all comments for a song| GET | /songs/:songId/comments | none | [1 : {user: {username: 'user420', location: 'Santa Cruz', followers: 43, image: "www.url.com"} , time: 0:42, postedAt: 'Wed Apr 01 2020 18:52:09 GMT-0700', text: "comment1"}, 2 : {user: {username: 'user123', location: 'Santa Cruz', followers: 43, image: "www.url.com"}, time: 2:52, postedAt: 'Wed Apr 01 2020 12:52:09 GMT-0700', text: "comment2"}]
Post a new comment for a song| POST | /songs/:songId/comments | Data type: JSON {user: {username: 'user421', location: 'Santa Cruz', followers: 43, image: "www.url.com"}, time: 0:42, postedAt: 'Wed Apr 01 2020 18:52:09 GMT-0700', text: "comment"} | Returns a status code based on success
Reply to a comment | POST | /songs/:songId/comments/:commentId | Data type: JSON {user: {username: 'user123', location: 'Santa Cruz', followers: 43, image: "www.url.com"}, time: 1:45, postedAt: 'Wed Apr 01 2020 18:52:09 GMT-0700', text: "comment"} | Returns a status code based on success
Update a song's stat | PATCH | /songs/:songId/trackers | Data Type: JSON   {likes: 211} | {plays: 100, likes: 212, reposts: 49} Returns a status code based on success
Delete a comment| DELETE | /songs/:songId/comments/:commentId | none | Returns a status code based on success

