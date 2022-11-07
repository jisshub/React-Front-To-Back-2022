# React-Front-To-Back-2022

## Why choose React ?

- Organization
- Reusable
- Flexibility
- Popularity & Support
- Performance

## Declarative Code

- Components
- Props
- State
- Events

These are the building bflocks of React.

## Environment SetUp

- Install nodejs and npm.
- vs code
- react snippets extension
- postman

## Links & Resources

Feedback App Repo: <https://github.com/bradtraversy/feedback-app>

Github Finder App Repo: <https://github.com/bradtraversy/github-finder-app>

House Marketplace Repo: <https://github.com/bradtraversy/house-marketplace>

Brad's Gists - <https://gist.github.com/bradtraversy>

# Feedback App React

## Dynamic Values & Lists in JSX


```jsx
import React, { useState } from 'react'

export default function App() {
    const title = 'Blog Post'
    const body = 'This is my blog post'
    const comments = [
        {id: 1, text: 'comment 1'},
        {id: 2, text: 'comment 2'},
        {id: 3, text: 'comment 3'},
        {id: 4, text: 'comment 4'}
    ]
  return (
    <div className='container'>
        <h1>
            {title}
        </h1>
        <p>{body}</p>
        
        <div className='comments'>
            <h3>Comments ({comments.length})</h3>
            <ul>
            {
                comments && comments.map((comment, index) => (
                    <li key={index}>{comment.text}</li>
                ))
            }
            </ul>
        </div>
    </div>
  )
}
```

# Conditionals in JSX

```jsx
const showComments = true
{showComments && (
    <div className='comments'>
        <h3>Comments ({comments.length})</h3>
        <ul>
            {
                comments.map((comment, index) => (
                    <li key={index}>{comment.text}</li>
                ))
            }
        </ul>
    </div>
)}
```

