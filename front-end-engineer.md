# Front-end Engineer
By: Alan Nguyen

## 1. Introduction

## 2. Web Development Fundamentals

## 3. Improved Styling with CSS
### a. Intro
### b. CSS: The Box Model
### c. CSS: Display and Positioning
### d. CSS: Documentation & Debugging
### e. Color Theory 
### f. Color for UI
- Having a neutral background (any color with low lightness or saturation) is a good base
- a dark background with light colored text can be a reasonable alternative
- [Brand color](https://brandcolors.net/) is a hue that should dominate your color palette.
  -  accounts for roughly 60% of the color used 
- Button color can determine a lot in the user’s eyes
  - hover state (a shade or tint of the accent color )
  - disabled state
- Using a darker gray for text on a white background, or white text on a dark gray background,
- Whitespace, or negative space, refers to the emptiness between elements.
- Color blindness
  - red-green (difficult to differentiate between the red and green colors)
  - blue-yellow (blues tend to appear greener)
  - monochromatic (can’t see color at all)

Accessibility
- [Color Safe](http://colorsafe.co/)
- [Color Contrast Checker](https://webaim.org/resources/contrastchecker/)

Iterations: Define - Develop - Test - Research 

[Cloudflare](https://cloudflare.design/color)
This is a helpful tool to make it easier to work with color and build palettes.

### g. Text Design
**#HTML Headers**
- Differentiating important pieces of text, such as titles and subtitles
- HTML Best Practice
  - \<h1> — Used for titles.
        You should only have one header this style per page.
  - \<h2> — Used for headings.
        This should be to identify major sections you want the user to immediately be drawn towards.
  - \<h3> — Used for subheadings.
      > This should be used for smaller focal points, such as articles, that you want the user to notice when scanning the page.

**#Fonts**
- have most of your text in a serif font, and then create contrast with headings or subheadings in a sans-serif font
- can contrast between different pieces of text in a number of ways:
  - style
  - size
  - weight
  - color

**#Text Readability**
- Make sure that your text is big enough (over 16px).
- Have a strong contrast between the foreground and the background.
- Make sure there is enough space between lines and letters (remember, whitespace is king!)

How can we adjust whitespace within the text?
- Line spacing (leading) - distance between two lines of text
- Tracking - the space between the letters and the words
- Kerning - the space between two letters

**#Text Navigation**
- Stick to conventions about showing what is clickable
- Never use blue as a general accent color for text
- Having text on navigation buttons is important

If you organize the text into columns, the user’s eyes will likely not travel across the entire screen, they will travel to the end of a column and then down. 

**#Text length, columns, and line length**
- Text length - The average internet paragraph is only 1-3 sentences.
- Line length - has a larger impact than you would expect on the reader
  > Each time a reader gets to a new line the mind is slightly energized and encouraged (“Typographie”, E. Ruder).
  - users prefer shorter line lengths 
  - columns contain roughly 50-75 characters per line

**#What Content will the Users Notice and Remember?**
- Primacy and recency effects
  - People will notice and remember the first and last elements of a list or a page
- Image pairing
  - Users eyes are easily drawn to images quicker than they are to text.
  - This pairing can be accomplished by grouping with card designs (putting them in a div together with a shared background color).

**#F-Shaped skimming**
- You need to write and format your text with this skimmer in mind.
- Users will scan content on the left of the screen before the right of the screen, and the top of the screen before the bottom of the screen. Our eyes jump back to the left of the screen whenever we finish reading a line. 

[Google Font Pairings](https://www.reliablepsd.com/ultimate-google-font-pairings/)

### h. Links & Buttons
- Showing interactivity and clickability through signifiers

- Browser link styles
  - clicked (but not yet followed) links appear with red text,
  - previously visited links are styled with purple text.

**#Tooltips and titles**

```html
<p>
  <a href="https://www.codecademy.com" title="Codecademy is an online learning platform">Codecademy</a> is the best place to learn to code!
</p>
```

**#Link States**
Links have four main states: 
- normal (not clicked) - :link
- hover - :hover
- active (clicked) - :active
- visited - :visited. 

**#Skeuomorphism and Flat Design**
- If users can draw a metaphor between a familiar real-life object and an interface element, they are more likely to know how to use it without training. 
- Flat design uses simplicity and lack of clutter for its UI elements.

**#Buttons: Hover states**
- Users expect buttons to be clickable. Since buttons can consist of any number of total elements (rectangular/circular body, text, image(s)), all elements should be clickable

**#Affordances**
- Objects afford the ability of users to interact with them in various ways.
- Potentials for interaction are collectively called the affordances of an object.

**#Signifiers**
- Signifiers are aspects of an object that a designer uses to indicate potential and intended affordances of an object.
- The cup's handle is an example of a common user experience pattern. 

**#UX Patterns**
- User experience (UX) patterns establish reusable solutions to common problems. 

**#Affordances and Signifiers in Web Design**

One common example of visual feedback is the cursor image itself
- a pointing hand indicating that an interaction will occur
- an i-beam shape indicating that text can be selected
- a four-directional arrow showing that an element can be moved
- and many more cursor styles and interactions.

A ubiquitous example is the styling of hyperlinks

Further Reading
- [Signifiers, not affordances](https://www.jnd.org/dn.mss/signifiers_not_affordances.html) by Don Norman
- UIpatterns.com

**Quiz**

What is the proper cascade order for pseudo-classes so that they show all link states accurately?
- :link, :visited, :hover, :active

### i. Secondary Navigation
**#Intro**
- The primary navigation system typically contains the most important links and buttons that need to be displayed on every single page of the site.
- Secondary(breadcrumbs) navigation consists of a clickable list of pages or attributes that led to the current page.

Benefit of using breadcrumbs
- gives an idea of where they're on the website
- hints at the extent of the site.
- provides a way for a user to quickly jump backward in their navigation of the site

**#Breadcumb styles**

```html
<ul class="breadcrumb">
  <li><a href="">Asia</a></li>
  <li><a href="">Singapore</a></li>
  <li><a href="">Tourism</a></li>
  <li><a href="">Hotels</a></li>
</ul>
```

```css
.breadcrumb {
  text-align: left;
}
.breadcrumb li {
  float: left;
}

.breadcrumb a {
  color: #fff;
  background: darkcyan;
  text-decoration: none;
  position: relative;
  height: 30px;
  line-height: 30px;
  text-align: center;
  margin-right: 15px;
  padding: 0 5px;
}

.breadcrumb a::before,
.breadcrumb a::after {
  content: "";
  position: absolute;
  border-color: darkcyan;
  border-style: solid;
  border-width: 15px 5px;
}

.breadcrumb a::before {
  left: -10px;
  border-left-color: transparent;
}
.breadcrumb a::after {
  left: 100%;
}

.breadcrumb a::after {
  left: 100%;
  border-color: transparent;
  border-left-color: darkcyan;
}

.breadcrumb a:hover {
  background-color: blue;
}
.breadcrumb a:hover::before {
  border-color: blue;
  border-left-color: transparent;
}
.breadcrumb a:hover::after {
  border-left-color: blue;
}

```

**#Breadcrumb Types**

There are three major types of breadcrumbs:
- Location
- Attribute
- Path

In general, the rule of not adding anything extraneous to the design

### j. Build a Website Design System

## 4. Making a Website Responsive
### a. Responsive design
### b. Layout with Flexbox
### c. Grids & Spacing
### d. Grid
### e. Wireframing
### f. Company Home Page
### g. Responsive Club Website

## 5. JavaScript Syntax - Part 1
### a. JS in Web Development
### b. Running JS
### c. Syntax: Intro
### d. Syntax: Conditionals
### e. Syntax: Functions
### f. Syntax: Scope
### g. Number Guesser

## 6. JavaScript Syntax - Part 2
### a. Syntax: Arrays
### b. Syntax: Loops
### c. Syntax: Objects
### d. Syntax: Iterators
### e. Syntax: Errors and Debugging
### f. Syntax: Credit Card Checker
### g. Mysterious Organism

## 7. Building Interactive Websites
### a. JS interactive website
### b. JS and the DOM
### c. DOM Events with JS
### d. HTML Forms

## 8. Making a Website Accessible

## 9. CSS Transitions and Animation
### a. Transitions and Tranforms
### b. Animations

## 10. Command Line - Git - Github

### a. Web Hostings
### b. Command line for building websites
### c. Intro to Git
### d. Intro to GitHub
### e. Markdown

## 11. HTML-CSS-JS Portfolio Project

## 12. JavaScript Syntax - Part 3
### a. Syntax: Classes
### b. Syntax: Modules
### c. Syntax: Error Handling
### d. Practice Classes
### e. Find Your Hat

## 13. TDD Fundamentals
### a. Why Test?
### b. Write Good Tests with Mocha
### c. Learn TDD with Mocha

## 14. Async JavaScript and HTTP Requests
### a. Basics of Asynchronous JS
### b. Syntax: Promises
### c. Syntax: Async-Await
### d. APIs and HTTP Requests
### e. JS: Requests
### f. Securing your applications

## 15. Web Apps

## 16. React - Part 1
### a. Review ES6 Syntax
### b. Review Functional JS
### c. Intro to React.js
### d. The Virtual DOM
### e. JSX
### f. React Components

## 17. React - Part 2 
### a. Components and Props
### b. React State
### c. React Development Tools
### d. Stateless Components from Statefull Components
### e. Lifecycle Methods
### f. Jammming
### g. Deploying React Apps with Netlify
### h. Function Components and Hooks
### i. Advanced React
### j. React Testing with Jest

## 18. Redux
### a. Why Redux?
### b. Intro to Redux
### c. Advanced Redux
### d. Testing Redux

## 19. Advanced Concepts in TDD
### a. Advanced Testing: Mocking
### b. Advanced Testing: Browser Automation

## 20. React & Redux Porfolio Project

## 21. Advanced Web Development 
### a. Styling Applications
### b. SEO
### c. Build Tools
### d. Optimizing Application
### e. Adding Realtime Connectivity

## 22. Linear Data Structures
### a. Intro to Data Structures
### b. Nodes
### c. Singly Linked Lists
### d. Doubly Linked Lists
### e. Queues
### f. Stacks

## 23. Complex Data Structures
### a. Hash Maps
### b. Trees
### c. Heaps
### d. Graphs

## 24. Algorithms
### a. Recursion
### b. Asymptotic Notation
### c. Bubble Sort
### d. Merge Sort
### e. Quicksort

## 25. Search & Graph Search Algorithms
### a. Binary Search & Search Trees
### b. Graph Traversals

## 26. Intervew Skills
### a. Whiteboarding
### b. JS algorithms Practice
### c. Soft skills
### d. Real World Interview Problems

## 27. Final Front-end Portfolio Project

## 28. Next Steps in Your Front-end engineer jouney
### Mobile Applications

If you’d like to build apps for iOS or Android, try [React Native](https://reactnative.dev/). It uses the same component hierarchy as React, which you already know!
### TypeScript

JavaScript is powerful and available on every browser, but it lacks one major feature: types. [TypeScript](https://www.codecademy.com/learn/learn-typescript) is an extension of JavaScript that adds types, which can save you time catching errors and provide fixes before you run code.

### Static Site Generators

If you want to use React for a large-scale application, try [Gatsby](https://www.gatsbyjs.com/), an ecosystem of tools that optimizes everything around your application, making it faster, safer, scalable, and accessible.

### GraphQL
If you plan on using or building APIs, look into [GraphQL](https://graphql.org/), a query language that makes it easier to work with APIs.




