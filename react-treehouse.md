# React - Treehouse
> By: Alan Nguyen

Table of Contents
- [React - Treehouse](#react---treehouse)
  - [- K - Using Create React Native App](#--k---using-create-react-native-app)
  - [A - React Basics](#a---react-basics)
    - [1. First steps](#1-first-steps)
    - [2. Thinking in Components](#2-thinking-in-components)
    - [3. Introducing Props](#3-introducing-props)
    - [4. Understanding State](#4-understanding-state)
  - [B - REACT COMPONENTS](#b---react-components)
    - [1. Build modular interfaces with components](#1-build-modular-interfaces-with-components)
    - [2. Managing State and Data Flow](#2-managing-state-and-data-flow)
    - [3. Stateful Components and Lifecycle methods](#3-stateful-components-and-lifecycle-methods)
    - [4. React Component Patterns](#4-react-component-patterns)
  - [C - REACT ROUTER 4 BASICS](#c---react-router-4-basics)
    - [1. Getting Started with React Router](#1-getting-started-with-react-router)
    - [2. Navigating, Nesting and Redirecting Routes](#2-navigating-nesting-and-redirecting-routes)
    - [3. Going further with Routing](#3-going-further-with-routing)
  - [D - CREATE REACT APP](#d---create-react-app)
    - [1. What is Create React app?](#1-what-is-create-react-app)
    - [2. Installing and Using Create React App](#2-installing-and-using-create-react-app)
  - [E - REACT CONTEXT API](#e---react-context-api)
    - [1. What is the Context API](#1-what-is-the-context-api)
    - [2. How context works](#2-how-context-works)
    - [3. Create Context](#3-create-context)
    - [4. Provide and Consumer State](#4-provide-and-consumer-state)
    - [5. Provide and Consumer Actions](#5-provide-and-consumer-actions)
    - [6. Refractor the Provider](#6-refractor-the-provider)
    - [7. Refractor the Consumer](#7-refractor-the-consumer)
  - [F - REACT 16](#f---react-16)
    - [1. Introducing React 16](#1-introducing-react-16)
    - [2. Take control of errors with `componentDidCatch()`](#2-take-control-of-errors-with-componentdidcatch)
    - [3. Catching Errors with error boundaries](#3-catching-errors-with-error-boundaries)
    - [4. New Return Types](#4-new-return-types)
    - [5. Render children into other DOM nodes with portals](#5-render-children-into-other-dom-nodes-with-portals)
    - [6. Returning `null` from `setState`](#6-returning-null-from-setstate)
  - [G - DATA FETCHING IN REACT](#g---data-fetching-in-react)
    - [1. Fetching Data with the Fetch API](#1-fetching-data-with-the-fetch-api)
    - [2. Fetching Data with Axios](#2-fetching-data-with-axios)
    - [3. Displaying the Data](#3-displaying-the-data)
    - [4. Building a Search feature](#4-building-a-search-feature)
    - [5. Displaying the Search results](#5-displaying-the-search-results)
  - [H - REACT HOOKS](#h---react-hooks)
    - [1. Set and Update State with `useState`](#1-set-and-update-state-with-usestate)
    - [2. Perform Side Effects with useEffect](#2-perform-side-effects-with-useeffect)
    - [3. Createa GIF Search App with React Hooks](#3-createa-gif-search-app-with-react-hooks)
    - [4. Use React's Context API with Hooks](#4-use-reacts-context-api-with-hooks)
  - [I - DEPLOYING A REACT APP](#i---deploying-a-react-app)
    - [1. Create a Production Build](#1-create-a-production-build)
    - [2. Deploy to GitHub Pages](#2-deploy-to-github-pages)
    - [3. Deploy to Now](#3-deploy-to-now)
    - [4. Deploy to Netlify](#4-deploy-to-netlify)
  - [J - Learn more](#j---learn-more)
    - [1. React by Example](#1-react-by-example)
    - [2. React Authentication](#2-react-authentication)
    - [3. Building Applications with React and Redux](#3-building-applications-with-react-and-redux)
  - [K - Using Create React Native App](#k---using-create-react-native-app)
---

## A - React Basics
### 1. First steps
**#Add React to a Project**

_Q. React manipulates and updates the DOM directly?_
- React only manages what gets rendered to the DOM via `ReactDOM.render`. It’s the job of `render()` to interpret the element objects and create DOM nodes out of them.

**#Understanding JSX**

**#Embed JS expressions in JSX**


_Q. Elements written in JSX get transpiled to?_
- `React.createElement()` functions

### 2. Thinking in Components
**#What is a Component?**
- A piece of UI that you can reuse. 
- Just like you're able to reuse code in JavaScript with functions, a component lets you reuse code that renders a part of your UI. 
- Being able to split your UI code into independent, reusable pieces, and think about each piece in isolation is one the most embraced features of React.


**#Create a Component**

While it isn’t required, the React docs recommend wrapping multiple lines of JSX in `()` to avoid the pitfalls of automatic semicolon insertion.

**#Use a Component with JSX**
- JSX lets you define your own tags. A JSX tag can not only represent an HTML element (like `<h1>`, `<span>`, and `<header>` ), it can also represent a user-defined component.

React components are written in plain JS with the help of JSX

**#Composing Components**


**#React Developer Tools**

With React, we never touch the actual DOM directly. React only manages what gets rendered into the DOM, so it can be tricky to debug your UI in the browser. The React Developer Tools extension gives you a big productivity boost when working with React. It lets you inspect your React component hierarchy in the Chrome and Firefox Developer Tools.

_Q. Why is a capital letter necessary in the component name?_
- To differentiate custom components from native DOM elements (`div`, `span`)

### 3. Introducing Props
**#Setting and Using Props**

`Props` - a list of properties used to pass data to a component. Components are customized and made reusable with props.

Two Steps to **using props in components**

1. Define the props in a component’s JSX tag
2. Enable the use of props in a component

- `props` are read only (immutable)
- The (parent) component higher in the tree owns and controls the property values
> All React components must act like pure functions with respect to their `props`

- You can omit the value of a prop when it's explicitly true

```jsx
<Header isFun />
```
**#Use Props to Create Resuable Components**


**#Iterating and Rendering with `map()`**
- render multiple items

**#Use Keys to Keep Track of Elements**
- `Key` is a unique identifier that gives React a way to quickly and reliably identify an element in the list 

- React manages what gets rendered to the DOM. In order for this process to be fast and efficient, React needs a way to quickly know which items were changed, added, or removed. For this, React gives elements a special built-in prop named key. A key is a unique identifier that gives React a way to quickly and reliably identify an element in a list.

- React does not recommend using index for unique keys, because the index might not always uniquely identify elements. It's usually best to use a unique id.

_According to the React docs:_
> We don’t recommend using indexes for keys if the order of items may change. This can negatively impact performance and may cause issues with component state. Check out Robin Pokorny’s article for an in-depth explanation on the negative impacts of using an index as a key. If you choose not to assign an explicit key to list items then React will default to using indexes as keys.


### 4. Understanding State
**#What is State**
- `State` is the data you want to track in your app. State is what allows you to create components that are dynamic and interactive, and it's the only data that changes over time.

_Note: State is only available to class component_

**#Create a Component as a class**
- Class components offer a more powerful way to build components because they're the only type of components that let you use state.
- In class, access props by this.props
- Use class instead of function when you want to use State

**#Create a stateful component**
- create a stateful component by first defining an initial state inside the Counter class.

```jsx
class Counter extends React.Component {
  constructor() {
    super();
    this.state = {
      score: 0,
    };
  }
}
```

- a shorter way to create state (feature of JS is currently not suppoted in all browers but babel transpiler helps to convert it to constructor)

```jsx
class Counter extends React.Component {
  state = {
    score: 0,
  };
}
```

**#Handling events**

To make the Counter component interactive, we need to be able to trigger changes to the data in state. 
- We'll first create an event handler that updates state, using React's built-in `setState()` method. 
- Then we'll give the buttons an `onClick` event that calls the event handler when clicked.

**#Updating state**
- In React, state is never modified directly. The only way React allows you to update a component's state is by using its built-in `setState()` method.

```jsx
incrementScore() {
  this.setState({
    score: this.state.score + 1
  })
}
```

**#Bind event handlers to components**
- When you create a class component that extends from React.Component, any custom methods you create are not bound to the component by default. You need to bind your custom methods, so that `this` refers to the component instance. 

**Several ways of binding:**
- `onClick={this.incrementScore.bind(this)}`
- arrow function inside `render`
    - it uses a lexical this binding which automatically binds them to the scope in which they are defined
- arrow function inside class

```jsx
incrementScore = () => {
  this.setState({
    score: this.state.score + 1
  })
}

onClick={this.incrementScore}
```
- Another way to bind an event handler is in the class constructor

```jsx
constructor() {
  super();
  this.state = {
      score: 0,
  };
  this.incrementScore = this.incrementScore.bind(this);
}

onClick={this.incrementScore}
```

**#Update state based on previous state**
- Whenever you need to update state based on previous state, you shouldn't rely on `this.state` to calculate the next state. State updates may be asynchronous, so it may not always lead to the component re-rendering with new data, and could cause state inconsistency. 
- `setState()` accepts a callback function that produces state based on the previous state in a more reliable way.

- Update state using callback function

```jsx
incrementScore = () => {
  this.setState(prevState => {
    return {
      score: prevState.score + 1,
    };
  });
};
```
- More concise way
```jsx
incrementScore = () => {
  this.setState(prevState => ({
    score: prevState.score + 1,
  }));
};
```

**#Creating the application state**
- Now you're going to learn how to remove items from state. We'll initialize a players state in the App component, then create and wire up an event handler that removes a player onClick. 

**2 types of states**
- Application state (data available to the entire app) 
- Component state (state that is specific to a component and not shared outside of the component)

**#Remove items from state**
- use the `filter()` array iteration method to remove an object from the players array in state.
	
_Note: Never modify state directly (commonly use filter array) _

[**#Practice State**](https://teamtreehouse.com/library/introducing-the-practice-38 )

## B - REACT COMPONENTS

### 1. Build modular interfaces with components
**#Setting up with Create React App**
- Developers normally use Create React App for developing React applications because it lets you quickly create and run React apps with no configuration. 
- Create React App is well-suited for projects of any size, and often used for developing production-ready apps.

**Steps**
- `npx create-react-app projectName`
- `npm install` _ to install in dependencies_

**Why Create React App?**
- The CDN-based approach is not useful in a production environment as soon as you start using JSX. For instance, we used Babel directly in the browser to transpile JSX into JavaScript. The Babel script is ~800KB in size, which for most use cases, is too large of a download to be practical. Also, there's the overhead in the browser of transpiling JSX into JavaScript.
- Developers use compiling as part of a build process to avoid the overhead of downloading Babel and multiple JavaScript files to the client. Create React App sets up a modern build system for your React apps in little time, no need to install or configure tools like Webpack or Babel. The tools are already pre-configured in each new project, that way you can focus on building your app.


_Q. What's in package.json?_
- When you create a project with Create React App, it installs the latest version of React and React-DOM, as well as the latest version of react-scripts, a development dependency that manages all other dev dependencies that run, test and build your app.

**Progressive Web App Features**

- Create React App sets up a fully functional, offline-first Progressive Web App by default. However, we removed the PWA related files just for this project to focus on the React components only.

**#Separating function components into Modules**
- Each component should be a separated component

**#Separating class components into Modules**
- break the Counter class out into its own module. We'll also use named import statements to define a class without having to extend from `React.Component`.

**Import React, Component**

```jsx
import React, { Component } from 'react';
import Header from './Header';
```

**Export component**

 ```jsx 
 export default Counter;
 ```

*Another way to export a class*

```jsx
export default class Counter extends Component {
  render() { ... }
}
```
*Another way to export a function*

```jsx
export const Counter = () => {
  return ( ... );
}
```


### 2. Managing State and Data Flow
**#Unidirectional Data Flow**

In React, data naturally flows down the component tree, from the app's top-level component down to the child components, via props. This is called "unidirectional data flow".

**#Lifting State Up**

When two or more components need access to the same state, we move the state into their common parent. This is called "lifting state up".

**#Update state based on a Player’s index**
- writing the `handleScoreChange` function by updating state based on the index of a player object.


**#Building the statistics component**

We lifted the score state up to the top of the application. Now we can pass that state down to any component. We'll build a statistics component that displays the total number of players on the Scoreboard, as well as the total number of points.	

**#Controlled components**

To manage an input field's state, we need to build a "controlled component." A controlled component renders a form element whose values are controlled by React, with state.

**Creating a controlled component**
- listen for changes on the input to detect when value is updated
- create an event handler that updates the value state

```jsx
class AddPlayerForm extends Component {
  state = {
    value: '',
  };
  
  handleValueChange = (e) => {
    this.setState({ value: e.target.value});
  }

  render() {
    return (
      <form>
        <input
          type="text"
          value={this.state.value}
          onChange={this.handleValueChange}
        />
      </form>
    )
  }
}
```

**#Adding items to state**
- create an event handler that allows users to submit the form. Then we'll write a function that adds the new player to state and displays it in the UI.

- handle submit
```jsx
handleSubmit = (e) => {
    e.preventDefault();
    this.props.addPlayer(this.state.value);
    this.setState({value: ''});
  }

  render() {
    return (
      <form onSubmit={this.handleSubmit}>
```

- handle add player
```jsx
handleAddPlayer = (name) => {
    this.setState((prevState) => {
      return {
        players: [
          ...prevState.players,
          {
            name,
            score: 0,
            id: (this.prevPlayerId += 1),
          },
        ],
      };
    });
  };
```

**#Update the players state based on previous state**

_Note: should use `prevState` instead of `this.state` when we want to update the state. That way we can be sure that `this.state` always holds the correct updated state._

- Update the `players state` using the `concat()` method

```jsx
handleAddPlayer = (name) => {
    let newPlayer = {
      name,
      score: 0,
      id: this.prevPlayerId += 1
    };
    this.setState( prevState => ({
      players: prevState.players.concat(newPlayer)
    }));
  };

```

_Q. React allows us to use props that are callback functions to communicate data upstream, from a child to a parent._
- That’s how a child component can access functions and change state defined in its parent component 

### 3. Stateful Components and Lifecycle methods
**#Designing the Stopwatch**
- It will be a stateful component that counts seconds, and allows users to start, stop and reset the time.

**#Stopwatch State**

The stopwatch will have two main states visible to the user. It will be either in a running state, or a stopped state. The buttons on the interface should change based on the running state. We'll start by initializing state in the Stopwatch component.

**Conditional rendering with if...else**
```jsx
render(){
  let button;
  if (this.state.isRunning){
    button = <button>Stop</button>;
  } else {
    button = <button>Start</button>;
  }
}

return (
  { button }
)
```

**#Update the Stopwatch State with `componentDidMount()`**

Component Lifecycle - every component instance follows a cycle: 
- mounted onto the DOM
- updated with changes in data
- unmounted from the DOM

**React lifecycle methods**
- built-in methods that get called at each point in the life cycle
- hooks that run code at key times in a component's life cycle
- give the ability to control what happens when a component mounts, updates and unmounts

Use the `componentDidMount()` lifecycle method to make the stopwatch tick. React's built-in lifecycle methods get called at each point in a component's life-cycle. The methods act as hooks you can use to run code at key times in the life-cycle. This gives you the ability to control what happens when a component mounts, updates and unmounts.

**#Resetting the Stopwatch**

In order to display the stopwatch time in seconds, we'll do one final calculation that converts the elapsed time in milliseconds to seconds. Then we'll wire up the "Reset" button to a function that resets the stopwatch back to 0.

**#Prevent Memory Leaks with `componentWillUnmount()`**

Since components do not always stay in the DOM, React also provides the `componentWillUnmount` lifecycle method to help you handle unmounting of components. This can help **prevent memory leaks** in your application.



_Q. Which lifecycle method gets called by React as soon as a component is inserted into the DOM?_
- componentDidMount()

_Q. Which lifecycle method do you use to fetch data from an API?_
- componentDidMount()

### 4. React Component Patterns
**#Optimize Performance with `PureComponent`**

React provides a special type of component, called PureComponent, that helps prevent unnecessary re-renders. If your component’s `render()` method renders the same result given the same props and state, you can use PureComponent for a performance boost in some cases.

**React Component Patterns**
- Destructure props
- Validate props
- Access DOM nodes with refs
- Practice creating React components
- Use PureComponent

_Note: A `PureComponent` should only contain child components that are also PureComponents._

**#Destructuring Props**

ES2015 introduced destructuring assignment, which is a special kind of syntax you can use to "unpack" (or extract) values from arrays, or properties from objects, into distinct variables. Developers often use destructuring in React to make their components cleaner and easier to understand. It provides a more concise way to write your props.

- destructure props to players and title

```jsx
const Header = ({ players, title }) => {
  return (
    <header>
      <Stats players={players}/>
      <h1>{title}</h1>
    </header>
  );
};
```

- another way to destructure 

  `const { players, title } = props;`


**#Refs and the DOM**

Refs let you access and interact with DOM nodes created in the `render()` method. They make it possible to do the more traditional DOM manipulation, and they're commonly used to access form elements and get their values.

**When to use Control component and Ref?**
* Control component - easier to modify or validate user input, call render on every key stroke

* Ref - render is called only once, use when don’t have to keep track every key stroke, just the value from DOM 

```jsx
playerInput = React.createRef();

handleSubmit = (e) => {
            e.preventDefault();
            this.props.addPlayer(this.playerInput.current.value);
            e.currentTarget.reset();
          };

          render() {
            return (
              <form onSubmit={this.handleSubmit}>
                <input
                  type="text"
                  ref={this.playerInput}
                />
```

**#Validate Props with PropTypes**

As your app grows, it's a good practice to "type check" or validate the data a component receives from props. In this video, you'll learn how to validate props with the `PropTypes` library. `PropTypes` not only help you catch and avoid bugs, they also serve as a documentation for components. Other developers working on the same project will know exactly which props your components take, and what types they should be.

`npm install --save prop-types`

**Type checking in React**
- PropTypes
- TypeScript
- Flow

```jsx
import PropTypes from 'prop-types';

Header.propTypes = {
  title: PropTypes.string,
  player: PropTypes.arrayOf(PropTypes.object),
};
```

**#Static PropTypes and Default Props**

In class components, it's common to define `propTypes` inside the class with the static keyword. You can also set a default value for your props, with a `defaultProps` object.

```jsx
import PropTypes from 'prop-types';

class Player extends PureComponent {
  static propTypes = {
    index: PropTypes.number,
    isHighScore: PropTypes.bool,
  };
```

[**#Practice Component Rendering**](https://teamtreehouse.com/library/introducing-the-practice-37)

## C - REACT ROUTER 4 BASICS
### 1. Getting Started with React Router
**#Expand your React Skill**

Routing is the process of matching a URL to the set of components being rendered. Routing dynamically loads components and changes what's displayed in the browser as users navigate an app, all without reloading the page. React does not have built-in routing features, so developers rely on React Router, an external library designed specifically for React.

**#What is Routing?**

In single-page apps (SPAs), routing is responsible for loading and unloading content while matching the URL with the set of components being rendered. Routing should also keep track of browser history and link users to specific sections of your app.

_Q. A good routing solution should keep track of browser history and seamlessly link users to specific sections of your app._
- True. Users should navigate a single-page app using the browser’s back and forward buttons, and URL should always direct the user to the correct location

_Q. In web development, routing:_
- Matches a URL to the set of components being rendered

_Q. React Router does not let you change routes programmatically. For example, you are not able to create a route in response to a form submission_ - False

_Q. What is a single-page app (SPA)?_
- A web application that display on a single web page. The HTML, JS, and CSS are loaded once by the browser and the content changes dynamically as users interact with the app

_Q. React includes built-in routing features._
- False. React is a libarary concerned with just rendering your UI. You’ll install additional libraries and add-ons for certain features; React Router is the official routing library 

**#Installing React Router & Declaring Routes**

  `npm install —save react-router-dom`

**#Inline Rendering with <Route>**

  Besides the component prop, <Route> provides additional ways to render a component. For example, the render prop lets you do inline component rendering.

```jsx
import React from 'react';
import { BrowserRouter, Route, Switch } from 'react-router-dom';

// App components
import Header from './Header';
import Home from './Home';
import About from './About';
import Teachers from './Teachers';
import Courses from './Courses';

const App = () => (
  <BrowserRouter>
    <div className="container">
      <Header />
      <Route exact path="/" component={Home} />
      <Route path="/about" render={() => <About title="About" />} />
      <Route path="/teachers" component={Teachers} />
      <Route path="/courses" component={Courses} />
    </div>
  </BrowserRouter>
);

export default App;

```

_Q. Which component is one of the core components of React Router and keeps your UI in sync with the URL?_
	`<BrowserRouter>`

_Q. Which `<Route>` prop renders a component only when the path matches the URL exactly?_
	`exact`

_Q. React Router uses JSX syntax to declare routes._
- True. React Router is a set of components, and the declarative syntax of JSX makes it easier to visualize how routes are structured 

_Q. Which React Router component is responsible for rendering UI (or other components)?_ - Route

_Given this code:_

```jsx
<Route exact path="/signup" component={SignupForm} />
```

_Which of the following is true about Route?_
- It renders the SignupForm component only when the URL path is exactly '/signup'

_Q. Which `<Route>` prop accepts an inline function that gets called when the URL and path match?_ - render 

### 2. Navigating, Nesting and Redirecting Routes

**#Navigating between Routes**

Use React Router's `<Link>` component to navigate between our routes.

```jsx
import React from 'react';
import { Link } from 'react-router-dom';

const Header = () => (
  <header>
    <span className="icn-logo">
      <i className="material-icons">code</i>
    </span>
    <ul className="main-nav">
      <li>
        <Link exact to="/">Home</Link>
      </li>
      <li>
        <Link to="/about">About</Link>
      </li>
      <li>
        <Link to="/teachers">Teachers</Link>
      </li>
      <li>
        <Link to="/courses">Courses</Link>
      </li>
    </ul>
  </header>
);

export default Header;
```

**#Styling Active Links**
  
React Router provides a simple way to change the appearance of a link when it's active. The `<NavLink>` component is a special version of `<Link>` that can recognize when it matches the current URL.


React Router provides an `<Redirect>` component that instructs the router to redirect from one route to another.

The match object contains information about how a route is matching the URL. We can access this data from inside components being rendered by `<Route>`.  e'll use match to dynamically match `<Route>` and `<NavLink>` to the current URL and path.

```jsx
import React from 'react';
import { NavLink } from 'react-router-dom';

const Header = () => (
  <header>
    <span className="icn-logo">
      <i className="material-icons">code</i>
    </span>
    <ul className="main-nav">
      <li>
        <NavLink exact to="/">Home</NavLink>
      </li>
      <li>
        <NavLink to="/about">About</NavLink>
      </li>
      <li>
        <NavLink to="/teachers">Teachers</NavLink>
      </li>
      <li>
        <NavLink to="/courses">Courses</NavLink>
      </li>
    </ul>
  </header>
);

export default Header;

```

### 3. Going further with Routing

With React Router, you're able to declare dynamic routes using special URL parameters. The data passed to the URL parameters can be displayed in your app.
- Add a `?` to the end of a parameter
- The  object can be used to programmatically change the URL.

## D - CREATE REACT APP 

### 1. What is Create React app?

### 2. Installing and Using Create React App
- Use the npx command to install Create React App and create a new app, all at once. For example:
    
`npx create-react-app my-app`
    

## E - REACT CONTEXT API 
### 1. What is the Context API
React provides a way to pass data to components without having to pass props manually at every single level, or reach for a state management library like Redux. Context was an experimental feature in older versions of React, and it officially became a stable feature in React 16.3.

 - the cascade of props that gets data to parts of the React Component tree

React context API - provide a way to pass data down to components without having to pass props manually at every single level

### 2. How context works

- `createContext()`
    - set up a context and returns an object with a Provider and a Consumer
- Provider
    - used as high as possible in the component tree
    - allows a Consumer to subscribe to context changes
- Consumer

### 3. Create Context

**#Create `index.js` inside Context folder**

```jsx
import React from 'react';

const ScoreboardContext = React.createContext();

export const Provider = ScoreboardContext.Provider;
export const Consumer = ScoreboardContext.Consumer;
```

**#import `Provider` to App**

```jsx
import {Provider} from './Context';
```

**#Put code of return App into Provider tag**

### 4. Provide and Consumer State

Now that context is set and the provider is in place, we'll provide state to the entire app. We'll set up Consumers that subscribe (or connect) to the Provider component to make use of the context.

**#Add value to Provider**

```jsx
<Provider value={this.state.players}>
```

**#Import Consumer to Stats** 

```jsx
import {Consumer} from './Context';
```

**#Put code of return into Consumer tag**

`Render Prop` - a technique for sharing code between React components using a prop whose value is a function

`React.Fragment` - group a list of sibling elements or components without having to add an unnecessary reaper element 


### 5. Provide and Consumer Actions

### 6. Refractor the Provider 
- Move the `Provider`, along with the state and actions into a separate (higher order) component. As a result, the `App component` will have less code and responsibilities, making it easier to think about and maintain.

**Higher-order component** (HOC) - a technique for reusing component logic. 
- A HOC takes an existing component and returns a new component

`children` - a special React prop that lets you pass components as data to other components

### 7. Refractor the Consumer 
- use ES2015 destructuring to extract the state and actions from the value object received from the Provider.

## F - REACT 16 
### 1. Introducing React 16
The new core architecture of React 16, codenamed “Fiber,” keeps most of the API intact and backward compatible. You can update existing apps without running into issues. Fiber introduces lots of new, highly anticipated features and improvements to React.

### 2. Take control of errors with `componentDidCatch()`
One of the biggest changes in React 16 is how React handles JavaScript errors. It provides a built-in solution for handling errors gracefully, with a new lifecycle method called componentDidCatch().

### 3. Catching Errors with error boundaries
With `componentDidCatch()` comes a new concept of an error boundary. Error boundaries are wrapper components that use `componentDidCatch()` to capture errors anywhere in their child component tree and display a fallback UI.

_Note: Error boundaries only catch errors in the components below them in the tree. An error boundary can’t catch an error within itself._

### 4. New Return Types
React 16 no longer requires that a render method returns a single React element. You can render multiple sibling elements without a wrapping element by returning an array. This eliminates the need for an extra element just to wrap your component tree. The other new return types React 16 supports are strings and numbers.

Updates
React v16.2.0 provides a first-class <Fragment> component that can be used in place of arrays. This lets you return multiple children from a component’s render method. Read all about it in the docs.
Resources
* New render return types: fragments and strings
* List of supported return types

### 5. Render children into other DOM nodes with portals
React 16 introduces a new way of rendering into the DOM. You can render children into a DOM element that exists outside of your App's main DOM tree, with a new feature called “portals.”

### 6. Returning `null` from `setState`
React 16 lets you decide if state gets updated via setState to prevent unnecessary re-renders. In your events, you can check if the new value of state is the same as the existing one. If the values are the same, you can return `null` and it won’t re-render a component.

## G - DATA FETCHING IN REACT 
### 1. Fetching Data with the Fetch API

```js
constructor() {
    super();
    this.state = {
      gifs: [],
    };
  }

  componentDidMount() {
    fetch('http://api.giphy.com/v1/gifs/trending?api_key=dc6zaTOxFJmzC')
      .then((response) => response.json())
      .then((responseData) => {
        this.setState({ gifs: responseData.data });
      })
      .catch((error) => {
        console.log('Error fetching and parsing data', error);
      });
  }
```
  
**Resources**

- [Giphy API documentation](https://github.com/Giphy/GiphyAPI)
- [Fetch API – MDN](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)
- [Introduction to fetch()](https://developers.google.com/web/updates/2015/03/introduction-to-fetch)
- [fetch() polyfill](https://github.com/github/fetch)
  
### 2. Fetching Data with Axios
- Install axios  
`npm install --save axios`

```jsx
import axios from 'axios';

  componentDidMount() {
    axios
      .get('http://api.giphy.com/v1/gifs/trending?api_key=dc6zaTOxFJmzC')
      .then((response) => {
        this.setState({
          gifs: response.data.data,
        });
      })
      .catch((error) => {
        console.log('Error fetching and parsing data', error);
      });
  }
```
**Resouce**
- [Axios advantage over fetch](https://github.com/mzabriskie/axios/issues/314)
  
### 3. Displaying the Data
  
```jsx
import React from 'react';
import Gif from './Gif';

const GifList = (props) => {
  const results = props.data;
  let gifs = results.map((gif) => (
    <Gif url={gif.images.fixed_height.url} key={gif.id} />
  ));

  return <ul className="gif-list">{gifs}</ul>;
};

export default GifList;

import React from 'react';

const Gif = (props) => (
  <li className="gif-wrap">
    <img src={props.url} alt="" />
  </li>
);

export default Gif;
```

### 4. Building a Search feature

```jsx
performSearch = (query) => {
    axios
      .get(
        `http://api.giphy.com/v1/gifs/search?q=${query}&limit=24&api_key=dc6zaTOxFJmzC`
      )
      .then((response) => {
        this.setState({
          gifs: response.data.data,
        });
      })
      .catch((error) => {
        console.log('Error fetching and parsing data', error);
      });
  };
  
<SearchForm onSearch={this.performSearch} />
  
  handleSubmit = (e) => {
    e.preventDefault();
    this.props.onSearch(this.state.searchText);
    e.currentTarget.reset();
  };
```

### 5. Displaying the Search results

**#Add loading**
```jsx
constructor() {
    super();
    this.state = {
      gifs: [],
      loading: true,
    };
  }
  
.then((response) => {
        this.setState({
          gifs: response.data.data,
          loading: false,
        });
  
<div className="main-content">
          {this.state.loading ? (
            <p>Loading...</p>
          ) : (
            <GifList data={this.state.gifs} />
          )}
        </div>
```

## H - REACT HOOKS

### 1. Set and Update State with `useState`
  
### 2. Perform Side Effects with useEffect
  
  
### 3. Createa GIF Search App with React Hooks

### 4. Use React's Context API with Hooks

## I - DEPLOYING A REACT APP 

### 1. Create a Production Build

- `npm run build` 
- `npm install -g serve`
- `serve -s build`

### 2. Deploy to GitHub Pages
Learn how to deploy and host a React app on GitHub Pages, a free hosting solution provided by GitHub that lets others view your repository as a static website.

**#Step1. Add homepage to package.json**
  
```json
"homepage": "https://alan-nguyen.github.io/scoreboard",
```

**#Step 2. Install Github pages**

  `npm install --save gh-pages`

**#Step 3. Setup scripts in package.json**
	
```json
"predeploy": "npm run build",
   "deploy": "gh-pages -d build",
```

**#Step 4. Publish to build to Github pages**
        
`npm run deploy`

**Set a Base URL**
- When using React Router, if your app is served from a sub-directory, pass the `'basename'` prop to the router to set the base URL for all locations. For example:
    
```jsx
<BrowserRouter basename="/course-directory">
```
### 3. Deploy to Now

**#S1 - Install Now**

`npm install -g now`

**#S2 - create now.json file**

```json
{
  "version": 2,
  "name": "app-name",
  "builds": [
    { "src": "package.json", "use": "@now/static-build" }
  ],
  "routes": [
    {"src": "^/static/(.*)", "dest": "/static/$1"},
    {"src": "^/favicon.ico", "dest": "/favicon.ico"},
    {"src": "^/asset-manifest.json", "dest": "/asset-manifest.json"},
    {"src": "^/manifest.json", "dest": "/manifest.json"},
    {"src": "^/service-worker.js", "headers": {"cache-control": "s-maxage=0"}, "dest": "/service-worker.js"},
    {"src": "^/precache-manifest.(.*)", "dest": "/precache-manifest.$1"},
    {"src": "^/(.*)", "dest": "/index.html"}
  ]
}
```
**#S3 - Set up package.json script**

```json
"scripts": {
  ...
  "now-build": "react-scripts build && mv build dist"
}
```


**#S4 - Deploy** 
      
`now`

### 4. Deploy to Netlify
Simple way - drop build folder to Netlify

**#Command line** 
- Install Netlify cli `npm install netlify-cli -g`

**#Deploy project**
- `netlify deploy`
- `deploy path build`

**#Add _redirects file inside build folder** 
- Include rewrite rule
`/*    /index.html   200`

## J - Learn more
The following courses will help you practice building React apps, and guide you through the basics of Redux, a JavaScript library for managing application state.
### 1. React by Example
Learn React programming patterns by building an application for keeping track of RSVP's.

### 2. React Authentication
Learn how to implement the Basic Authentication scheme in a React application using an Express REST API.

### 3. Building Applications with React and Redux
Redux is a state management framework that provides a robust infrastructure that complements React applications.

## K - Using Create React Native App
https://teamtreehouse.com/library/introducing-create-react-native-app