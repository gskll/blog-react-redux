# Blog - React Redux

Live deployment: https://blog-gray-omega-43.vercel.app

## Overview

Straightforward blogging app using jsonplaceholder API to show list of blog posts

### App Goals

- Absolutely understand the purpose of reducers
- Absolutely understand making API requets with Redux
- Absolutely understand the purpose of 'redux-thunk'

### App architecture

Two main components to display list of posts

`PostList` displays post title and body as a list

`UserHeader` nested in each `PostList` item to extract post user

### State

- Posts: array of posts
- Users: array of users based on userId's from the array of posts



### Issues

Only fetch each user once instead of each time one of their posts is loaded

Refactor: action creator `fetchPostsAndUsers` that uses `fetchPosts`, extracts the unique `userId`s and then uses `fetchUser` on each unique id

`  const userIds = [...new Set(getState().posts.map((post) => post.userId))];`

