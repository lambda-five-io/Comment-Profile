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

Intention | Request Type | Request URL | Example Input | Resonse Body
--------- | ------------ | ------------ | ------------ | ----------- |
Get info for a song| GET | /songs/:songId | none | {plays: 302, likes: 43, reposts: 69, comments: 123}
Get all comments for a song| GET | /songs/:songId/comments | none | [1 : {username: grant420, time: 0:42, postedAt: 03:21:04, text: "comment1"}, 2 : {username: grant710, time: 2:52, postedAt: 21:54:04, text: "comment2"}]
Post a new comment for a song| POST | /songs/:songId/comments | Data type: JSON {username: grant420, time: 0:42, postedAt: 03:21:04, text: "comment"} | Returns a status code based on success
Reply to a comment | POST | /songs/:songId/comments/:commentId/replies | Data type: JSON {username: user123, time: 1:45, postedAt: 17:54:32, text: "comment"} | Returns a status code based on success
Delete a comment| DELETE | /songs/:songId/comments/:commentId | none | Returns a status code based on success
Delete a reply | DELETE | /songs/:songId/comments/:commentId/replies/:replyId | none | Returns a status code based on success
