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
### k. Improved Styling with CSS

## 4. Making a Website Responsive

## 5. JavaScript Syntax - Part 1

## 6. JavaScript Syntax - Part 2

## 7. Building Interactive Websites

## 8. Making a Website Accessible

## 9. CSS Transitions and Animation

## 10. Command Line - Git - Github

## 11. HTML-CSS-JS Portfolio Project

## 12. JavaScript Syntax - Part 3

## 13. TDD Fundamentals

## 14. Async JavaScript and HTTP Requests

## 15. Web Apps

## 16. React - Part 1

## 17. React - Part 2 

## 18. Redux

## 19. Advanced Concepts in TDD

## 20. React & Redux Porfolio Project

## 21. Advanced Web Development 

## 22. Linear Data Structures

## 23. Complex Data Structures

## 24. Algorithms

## 25. Search & Graph Search Algorithms

## 26. Intervew Skills

## 27. Final Front-end Portfolio Project

## 28. Next Steps in Your Front-end engineer jouney




