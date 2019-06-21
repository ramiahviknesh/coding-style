# Happyfox Website Code Conventions

[![N|Solid](https://storage.pardot.com/123182/71392/happyfox_logo.svg)](https://nodesource.com/products/nsolid)

[![Version Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

## Introduction
The goal of this document is to write well-structured and standards-compliant markup. The guidelines described here provide a brief introduction to best coding practices;


## HTML Conventions

### Lowercase names
Element and attribute names must be in all lower case:

```html
<!-- Bad -->
<INPUT name="name" TYPE="text" />

<!-- Good -->
<input name="name" type="text" />
```
### Use of Semantic Elements
Semantic markup is a way of writing and structuring your HTML (Hypertext Markup Language) so that it reinforces the semantics, or meaning, of the content rather than its appearance. Usege of tags with more semantic sense is advised. some of the popular semantic tags that can be used are header, footer, main, nav, section, aside, article, and etc.
Read more: https://html.com/semantic-markup/#ixzz5rI3UTQkL

```html
<!-- Bad -->
<div class="header">
    <div class="naviagtion">
        <a href="home">home</a>
        <a href="about">about</a>
        <a href="contact">contact</a>
    </div>
<div>
<div class="home-section">
    <span class="heading">Article Heading</span>
    <div class="article1">lorem ipsum </div>
</div>
<div class="footer">
    <p>copyrights</p>
</div>

<!-- Good -->
<header>
    <nav>
        <a href="home">home</a>
        <a href="about">about</a>
        <a href="contact">contact</a>
    </nav>
</header>
<section>
    <h1>Article Heading</h1>
    <article>lorem ipsum</article>
</section>
<footer>
    <p>copyrights</p>
</footer>
```
### Indendation
Use soft tabs with 2 spaces for code indentation. Use indentation consistently to enhance the readability of the code. When elements carry over more than one line of code, indent the contents of elements between the start tag and the end tag. This will make it easy to see where the element begins and ends.

```html
<!-- Example -->
<div class="container">
  <header class="header">
    <h1>Site Name<span></span></h1>
  </header>
  <hr>
  <nav class="navigation">
    <ul>
      <li><a href="#">Link</a></li>
      <li><a href="#">Link</a></li>
      <li><a href="#">Link</a></li>
      <li><a href="#">Link</a></li>
      <li><a href="#">Link</a></li>
    </ul>
  </nav>
</div>
```

### Quotes
Double quote convention should be followed throughout the website.
```html
<!-- Good -->
<main class="main">

<!-- Bad-->
<div class='main'>
````

### Atribute order
HTML attributes should be in this order for facilitate the reading.

* class
* id, name
* src, for, type, href
* data-*
* title, alt
* aria-*, role


## CSS Guidelines 
### General
- Avoid using HTML tags in CSS selectors
- Don't use ids in selectors
- Don’t nest more than 3 levels deep
- Avoid using nesting for anything other than pseudo selectors and state selectors.
- Don't use `!important` - If you must, leave a comment, and prioritise resolving specificity issues before resorting to `!important`.
- Use shorthand properties
- Avoid user agent detection as well as CSS “hacks”—try a different approach first.
- All the color codes should be in lowercase
### Spacing
- Put spaces after `:` in property declarations
  - E.g. `color: red;` instead of `color:red;`
- Put spaces before `{` in rule declarations
  - E.g. `.o-modal {` instead of `.o-modal{`
- Write your CSS one line per property
- Add a line break after `}` closing rule declarations
- When grouping selectors, keep individual selectors on a single line
- Place closing braces `}` on a new line
- Add a new line at the end of .scss files
- Trim excess whitespace
### Naming Convention - BEM
The naming convention follows the following pattern along with lowercase
```css
.block {}
.block__element {}
.block--modifier {}
````
- **.block**  represents the higher level of an abstraction or component.
- **.block__element**  represents a descendent of .block that helps form .block as a whole.
- **.block--modifier**  represents a different state or version of .block.
Here's an example:
```html
<div class="contact-card">
 <h2 class="contact-card__name">Person</h2>
 <div class="contact-card__content">
   <p class="contact-card__content__details">
     Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nesciunt
   </p>
 </div>
 <button class="contact-card__btn contact-card__btn--primay">
   Accept
 </button>
  <button class="contact-card__btn contact-card__btn--secondary">
   Reject
 </button>
</div>
````
### Rule ordering
Properties and nested declarations should appear in the following order
1. Layout and box-model properties
   - margin, padding, box-sizing, overflow, position, display, width/height, etc.
2. Typographic properties
   - E.g. font-*, line-height, letter-spacing, text-*, etc.
3. Stylistic properties
   - color, background-*, animation, border, etc.
4. UI properties
   - appearance, cursor, user-select, pointer-events, etc.
5. Pseudo-elements
    - ::after, ::before, ::selection, etc.
6. Pseudo-selectors
   - :hover, :focus, :active, etc.
7. Modifier classes
8. Child elements if applicable
Here’s a comprehensive example:
```css
.hf-btn {
  display: inline-block;
  padding: 6px 12px;
  text-align: center;
  font-weight: 600;
  background-color: red;
  border-radius: 3px;
  color: white;
}
.hf-btn::before {
  content: '';
}
.hf-btn:focus, .hf-btn:hover {
  box-shadow: 0 0 0 1px color(blue, 0.3);
}
.hf-btn--big {
  padding: 12px 24px;
}
.hf-btn > .hf-icon {
  margin-right: 6px;
}
```
### Media Queries
Start the development with generic rules with and add media queries with mobile first.
```css
/* Good */
.navbar {
  margin-bottom: 20px;
}
@media (min-width: 768px) {
  .navbar {
    padding: 10px;
  }
}
/* Bad */
.navbar {
  position: fixed;
  top: 0;
  left: 0;
}
@media (max-width: 767px) {
  .navbar {
    position: static;
    padding: 10px;
  }
}
````

## Accessibility

### General

- Use h1 - h6 to identify headings - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H4)
- Use structural elements to group links - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H50)
- Provide definitions for abbreviations by using the abbr and acronym elements - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H28)
- Use language attributes on html element to identify the default language of a document - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H57)


### Tables

- Use table markup to present tabular information - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H51)
- Use the scope attribute to associate header cells and data cells in data tables - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H63)
- Use the summary attribute of the table element to give an overview of data tables - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H73)

### Forms

- Provide submit buttons - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H32)
- Use alt attributes on images used as submit buttons - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H36)
- Use label elements to associate text labels with form controls - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H44)
- Use the title attribute to identify form controls when the label element cannot be used - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H65)
- Indicate required form controls - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H90)

### Images

- Use alt attributes on img elements - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H37)
- Use null alt text and no title attribute on img elements for images that Assistive Technology should ignore - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H67)

