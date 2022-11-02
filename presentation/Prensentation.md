# HTML & CSS

---

# HTML & CSS

👋  Hi, I'm David

🏡  Edegem

💼  Tech Lead @ ZinderLabs

👨‍🏫  Coach @ The Campus

🐱  @zl-david

---


### ZinderLabs

🎯 Follow [ZinderLabs](https://www.instagram.com/zinderlabs/) for bite-sized tips to level up your coding

![[../prep/images/zl-ig.png|300]]

---

# Agenda

1. 📃   HTML
2. 💅   CSS Foundations
3. 💅   CSS Best practices & architecture
4. 👓   SASS

---

# 📃 HTML - The Goal

![[fantastic-tags.jpg]]

---

# 📃 HTML

> "Hyper Text Markup Language"

HTML describes the structure of a Web page

---

### HTML 4 Empty document

```html
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/strict.dtd">
<html>
	<head></head>
	<body></body>
</html>
```

---

### October 2014: HTML 5 Empty document

```html
<!DOCTYPE html>
<html>
	<head></head>
	<body></body>
</html>

```

DOCTYPE is used by browsers to validate the HTML document according to a specific standard

---

### 💻 HTML

Go to your favorite website, right-click and "View page source". Which tags do you see?

![[view-page-source.png|200]]
💡 Use https://codebeautify.org/htmlviewer if source is minified.

---

### HTML 5: Semantic HTML

Elements such as `<header>`, `<footer>` and `<article>` are all considered semantic because they accurately describe the purpose of the element and the type of content that is inside them.

---

### Semantic HTML

![[semantic-html.png]]

---

```html
<header></header>
<section>
  <article>
    <figure>
      <img />
      <figcaption></figcaption>
    </figure>
  </article>
</section>
<footer></footer>
```
```html
<div id="header"></div>
<div class="section">
  <div class="article">
    <div class="figure">
      <img />
      <div class="figcaption"></div>
    </div>
  </div>
</div>
<div id="footer"></div>
```


---

### Section vs Article

- Article: Independently distributable or reusable
- Section: Thematic grouping of content

```html
<section>
  <p>Top Stories</p>
  <section>
    <p>News</p>
    <article>Story 1</article>
    <article>Story 2</article>
    <article>Story 3</article>
  </section>
  <section>
    <p>Sport</p>
    <article>Story 1</article>
    <article>Story 2</article>
    <article>Story 3</article>
  </section>
</section>
```

---

### Aside

Content that is not part of the flow, however still related in some way.

```html
<aside>
  <p>
    This is a sidebar, for example a terminology definition or a short background to a historical
    figure.
  </p>
</aside>
```

---

### Header

The `<header>` element is generally found at the top of a document, a section, or an article and usually contains the main heading and some navigation and search tools.

---

### Nav

- Wrapper for `<ul><li>` navigation. 
- It's common to have a global navigation in a `header`, and a local navigation in a `sidebar`
```html
<nav>
  <ul>
    <li><a href="/home">Home</a></li>
    <li><a href="/about">About</a></li>
    <li><a href="/contact">Contact us</a></li>
  </ul>
</nav>
```

---

### Footer

A `<footer>` is generally found at the bottom of a document, a section, or an article. Just like the `<header>` the content is generally metainformation, such as author details, legal information, and/or links to related information. It is also valid to include `<section>`elements within a footer.

---

### Other

```html
<footer><small>&copy;Company A</small> Date</footer>
```
```html
<time datetime="2017-10-31T11:21:00+02:00">Tuesday, 31 October 2017</time>
```
```html
<figure>
  <img src="https://en.wikipedia.org/wiki/File:Shadow_of_Mordor_cover_art.jpg" alt="Shadow of Mordor" />
  <figcaption>Cover art for Middle-earth: Shadow of Mordor</figcaption>
</figure>
```

https://developer.mozilla.org/en-US/docs/Web/HTML/Element

---

### 💻 HTML5

https://codepen.io/pen/

- Create a functional "Create your Monster" form
- Use only HTML
- Fields: Name, hair color, eye color, Fur type (multi-select), number of eyes, birthday, Tattoo upload, height (1-10), wings (yes/no), description, submit button


---

# 💅 CSS - The Goal

![[mentalmodel.jpeg]]

---

# 💅 CSS

> "Cascading Style Sheets"

CSS describes how HTML elements are to be displayed on screen, paper, or in other media

---

💻   What can you do with CSS?

1. Go to codepen.io
2. Search for "CSS Only"

---

What can you do with CSS? (examples)

-   [https://codepen.io/onediv/pen/BprVzp](https://codepen.io/onediv/pen/BprVzp)
-   [https://codepen.io/hrtzt/pen/JdYaEZ](https://codepen.io/hrtzt/pen/JdYaEZ)
-   [https://codepen.io/amit_sheen/pen/XWMXwvJ](https://codepen.io/amit_sheen/pen/XWMXwvJ)

---

### Browser default styling

- Normalize: https://necolas.github.io/normalize.css/
- Reset e.g.: https://meyerweb.com/eric/tools/css/reset/reset.css
- Other, e.g.: https://boltcss.com/

---
### Learning CSS

![[css-fireship.png]]

---

### Learning CSS
#### Starts simple

```css
.warning-text {
  color: red;
  font-style: italic;
}
```

---

### Learning CSS
#### Is hard
- Implicit language
- Browser dependent
- No exceptions or error logs
- Unexpected results

---

### 4 ways to include CSS

1. Inline CSS 
2. Internal CSS 
3. External CSS 
4. Using @𝗶𝗺𝗽𝗼𝗿𝘁

---

### Mental Model 1
#### Z-Index

🔧  CSS Z-Index Chrome plugin

https://chrome.google.com/webstore/detail/z-context/jigamimbjojkdgnlldajknogfgncplbh?hl=en

---

### Mental Model 2
#### Cascade & Specificity
 Mechanisms that control which CSS rule applies

---

### Cascade & Specificity

```css
#testId {
  background-color: purple;
}

div:first-child {
  background-color: blue;
}

.testClass {
  background-color: red;
}

body div {
  background-color: green
}
```

```html
<div class="testClass" id="testId"></div>
```

What's the background color of the `div`?

---

### The Cascade

1. Position and order of appearance 
2. Origin 
3. Importance {`!important` keyword}
4. Specificity 

---

### The Cascade
#### Specificity

1. Inline styles (`style="..."`)
2. Id selector (`#example`)
3. Pseudo class selector (`:hover`, `:first-child`)
4. Class selector (`.example`)
5. Element selector (`body div`)

---

## 🎯 Key takeaway

Specificity makes CSS hard.

Minimize specificity hell by **using only classes** to style your HTML.

---

### Inheritance

> Inheritance controls what happens when no value is specified for a property on an element.

1. Inherited properties
2. Non-inherited properties

---

### Controlling Inheritance

- `prop: inherit`: Use parent styling
- `prop: initial`: Browser default
- `prop: unset`:  if the property is naturally inherited it acts like `inherit`, otherwise it acts like `initial`.

---

#### 💻  Cascade Exercise
https://github.com/zl-david

---

### Mental Model 3
#### The Box Model

---

```html
<style>
  .parent {
    width: 200px;
    border: 2px solid black;
  }
  .box {
    width: 100%;
    border: 2px solid hotpink;
    padding: 20px;
  }
</style>

<div class="parent"><div class="box"></div></div>
```

How wide is the `.box` element?

1. 200px
2. 240px
3. 244px
4. 160px
---
![[box-model.png]]

---

### Mental Model 4
#### Layout Algorithms

---

### Layout Algorithms

1. Flow (= default)
2. Positioned (e.g. `position: absolute`)
3. Flexbox
4. Table
5. Grid

---

### Layout Algorithms
- There's no "`layout-mode`" property
- Several properties can tweak the layout algorithm used 

---

### Layout Algorithms
CSS property applied to an element: 

```css
.help-widget {
  /* Uses Positioned layout, because of this declaration: */
  position: fixed;
  right: 0;
  bottom: 0;
}

.floated {
  /* Uses Float layout, because of this declaration: */
  float: left;
  margin-right: 32px;
}
```

---

### Layout Algorithms
CSS property applied to _**the parent element**_: 

```html
<style>
  .row {
    display: flex;
  }
</style>

<ul class="row">
  <li class="item"></li>
  <li class="item"></li>
  <li class="item"></li>
</ul>
```

---

## Flexbox

https://flexbox.help/
https://flexbox.tech/

---

#### 💻  Flexbox Exercise
https://github.com/zl-david

---

#### 🐸  Flexbox Froggy

https://flexboxfroggy.com/

---


# 💅 Clean CSS - The Goal

![[cleanup.webp]]

---

### CSS Variables

```css
:root {
  --primary: blue;
}

button {
  background-color: var(--primary);
}
```

---

### BEM

> *Block, Element and Modifier*

a.k.a. Class naming convention

---
![[css-bem.png]]

- Green: Block
- Blue: Element
- Red: Modifier

---

### BEM
#### Block
Standalone entity that is meaningful on its own.

*E.g.: menu*

---

### BEM
#### Element
A part of a block that has no standalone meaning and is semantically tied to its block.

E.g.: *.menu__item*

---

### BEM
#### Modifier
A flag on a block or element. Use them to change appearance or behavior.

E.g.: *.button--big*


---

### 💻  DIY - Refactor

```
2022-10-31-css-exercise/02-css-flexbox/05-component
```

1. CSS Variables
2. BEM

---

### Specificity Graph

![[itcss-1.png]]

---

![[itcss-2.png]]

---
![[itcss-3.png]]
---
![[itcss-4.png]]
---

### ITCSS - Inverted Triangle CSS

ITCSS is a way of thinking, a high-level architecture.

![[ITCSS.jpeg]]

---
### Default Layers

-   Settings layers - Global SASS variables
-   Tools - SASS functions and mixins
-   Generic - Normalise or css resets. General global rules
-   Elements – typography elements like H1, a
-   Objects - Non cosmetic design patterns like layouts and Grids
-   Components - Styling main UI components
-   Trumps – Overwrides, utilities and helper calsses

---

#### Generic

```css
* {
  box-sizing: border-box;
}
```

---

#### Elements (or Base)

```css
ul {
	list-style: square outside;
}
```

---

#### Objects

```css
.ui-list {
	margin: 0;
	padding: 0;
	list-style: none;
}
.ui-list__item {
	padding: 8px;
}
```

---

#### Components

```css
.products-list {
	border-top: 1px solid green;
}
```

---

#### Trumps

```css
.hidden { 
	display: none !important;
}
.one-half {
    width: 50% !important;
}
```


---

### 💻  DIY

https://github.com/zl-david/2022-10-31-itcss-exercise

---
## Media Queries

![1*-ldpo5wcYVnuyRFbO24WPQ](https://cdn-media-1.freecodecamp.org/images/1*-ldpo5wcYVnuyRFbO24WPQ.png)

---

![1*7YeOvzoYgUEDJdfQy2ERXg](https://cdn-media-1.freecodecamp.org/images/1*7YeOvzoYgUEDJdfQy2ERXg.png)

---

```scss
@mixin for-phone-only {
  @media (max-width: 599px) { @content; }
}
@mixin for-tablet-portrait-up {
  @media (min-width: 600px) { @content; }
}
@mixin for-tablet-landscape-up {
  @media (min-width: 900px) { @content; }
}
@mixin for-desktop-up {
  @media (min-width: 1200px) { @content; }
}
@mixin for-big-desktop-up {
  @media (min-width: 1800px) { @content; }
}

// usage
.my-box {
  padding: 10px;
  
  @include for-desktop-up {
    padding: 20px;
  }
}
```

---

```css
.my-box {
  padding: 10px;
}

/* for-desktop-up */
@media (min-width: 1200px) {
  .my-box {
    padding: 20px;
  }
}
```

---

## Advanced CSS Animations

https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations

---

# 👓 SASS - The Goal

> How to make your code reusable & compact?

---

# 👓 SASS
> **Syntactically awesome style sheets**


Sass is a stylesheet language that’s compiled to CSS. It allows you to use [variables](https://sass-lang.com/documentation/variables), [nested rules](https://sass-lang.com/documentation/style-rules#nesting), [mixins](https://sass-lang.com/documentation/at-rules/mixin), [functions](https://sass-lang.com/documentation/modules), and more, all with a fully CSS-compatible syntax.

---

### SASS docs

https://sass-lang.com/guide

---

### 💻  DIY

https://github.com/zl-david/2022-10-31-itcss-exercise

---
![[dont-make-me-think.png]]