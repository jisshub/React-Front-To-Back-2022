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

# Creating First Component & Props


## Props

Props are properties which passed from parent component to child component. Here App is the parent component, Header is child component.

**App.js**

```jsx
export default function App() {
  return (
    <>
        <Header text="Hello World" />
        <div className='container'> 
            <h2>Hello Jissmon</h2>
        </div>
    </>
    
  )
}
```

**Header.js**

```js
function Header({text}) {
  return (
    <div>
        <h1>{text}</h1>
    </div>
  )
}
```

Here we destructure the prop text.


# Adding Styles to Component


**App.js**

```js
import PropTypes from 'prop-types';

export default function App() {
  return (
    <>
        <Header text="Hello World" />
        <div className='container'> 
            <h2>Hello Jissmon</h2>
        </div>
    </>
  )
}

Header.defaultProps = {
  bgColor: 'rgba(0,0,0,0.5)',
  textColor: '#ff6a95'
}

Header.propTypes={
  bgColor: PropTypes.string,
  textColor: PropTypes.string,
}
```


Here we pass props *bgColor* and *textColor* props to Header element from App component(child) to Header component(child). we use defaultProps property to set the props


**Header.js**

```js
function Header({text, bgColor, textColor}) {
  const headerStyles = {
    backgroundColor: bgColor,
    color: textColor
  }
  return (
    <header style={headerStyles}
      >
      <div className='container'>
        <h1>{text}</h1>
      </div>
    </header>
  ) 
}
```


# State and useState Hook

1. Component Level State
2. Global or App Level State


**FeedbackItem.js**

```js
function FeedbackItem() {
    const [rating, setRating] = useState(7)
    const [text, setText] = useState('This is an example of feedback item.')

    return (
        <div className='card'>
            <div className='num-display'>{rating}</div>
            <div className='text-display'>{text}</div>
            <button onClick={handleClick}>Click</button>
        </div>
    )
}
```

**App.js**

```js
export default function App() {
  return (
    <>
        <Header/>
        <div className='container'> 
            <h2>Hello World</h2>
        </div>
        <FeedbackItem />
    </>
  )
}
```

# Managing Global State


