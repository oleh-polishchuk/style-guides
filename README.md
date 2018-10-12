## Contents

- [HTML/CSS style guides](#html-css-style-guides)
- [AngularJS style guides](#angularjs-style-guides)
- [REST API best practices](#rest-api-best-practices)
- [JavaScript style guides](#javascript-style-guides)
- [JSON style guides](#json-style-guides)
- [:sunglasses: My own style guides](#my-own-style-guides)

## HTML-CSS style guides

- [Google HTML/CSS Style Guide](http://google.github.io/styleguide/htmlcssguide.html)

## AngularJS style guides

- [Angular Style Guide](https://github.com/johnpapa/angular-styleguide/blob/master/README.md)

## REST API best practices

- [10 Best Practices for Better RESTful API](https://blog.mwaysolutions.com/2014/06/05/10-best-practices-for-better-restful-api/)

## JavaScript style guides

- [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript)

## JSON style guides

- [Google JSON Style Guide](https://google.github.io/styleguide/jsoncstyleguide.xml)

## My Own style guides

### BEM — Block Element Modifier 

Block Element Modifier is a methodology that helps you to create reusable components and code sharing in front-end development

A BEM class name includes up to three parts.

- **Block**: The outermost parent element of the component is defined as the block.
- **Element**: Inside of the component may be one or more children called elements.
- **Modifier**: Either a block or element may have a variation signified by a modifier.

If all three are used in a name it would look something like this:

    [block]__[element]--[modifier]

```
<!-- GOOD -->
<figure class="photo">
  <img class="photo__img" src="me.jpg">
  <figcaption class="photo__caption">Look at me!</figcaption>
</figure>

<style>
  .photo { } /* Specificity of 10 */
  .photo__img { } /* Specificity of 10 */
  .photo__caption { } /* Specificity of 10 */
</style>
```

```
<!-- BAD -->
<figure class="photo">
  <img src="me.jpg">
  <figcaption>Look at me!</figcaption>
</figure>

<style>
  .photo { } /* Specificity of 10 */
  .photo img { } /* Specificity of 11 */
  .photo figcaption { } /* Specificity of 11 */
</style>
```


### HTML5 New Elements

Below is a list of the new HTML5 elements, and a description of what they are used for.

```
<article>	Defines an article in a document
<aside>	    Defines content aside from the page content
<bdi>	    Isolates a part of text that might be formatted in a different direction from other text outside it
<details>	Defines additional details that the user can view or hide
<dialog>	Defines a dialog box or window
<figcaption>Defines a caption for a <figure> element
<figure>	Defines self-contained content
<footer>	Defines a footer for a document or section
<header>	Defines a header for a document or section
<main>	    Defines the main content of a document
<mark>	    Defines marked/highlighted text
<menuitem> 	Defines a command/menu item that the user can invoke from a popup menu
<meter>	    Defines a scalar measurement within a known range (a gauge)
<nav>	    Defines navigation links
<progress>	Represents the progress of a task
<rp>	    Defines what to show in browsers that do not support ruby annotations
<rt>	    Defines an explanation/pronunciation of characters (for East Asian typography)
<ruby>	    Defines a ruby annotation (for East Asian typography)
<section>	Defines a section in a document
<summary>	Defines a visible heading for a <details> element
<time>	    Defines a date/time
<wbr>	    Defines a possible line-break
```

### HTML5 Semantic Elements

Semantic elements = elements with a meaning.

A semantic element clearly describes its meaning to both the browser and the developer.

Examples of non-semantic elements: <div> and <span> - Tells nothing about its content.

Examples of semantic elements: <form>, <table>, and <article> - Clearly defines its content.
    
```
<!-- GOOD -->
<section>
  <h1>WWF</h1>
  <p>The World Wide Fund for Nature (WWF) is....</p>
</section>

<!-- GOOD -->
<article>
  <h1>What Does WWF Do?</h1>
  <p>WWF's mission is to stop the degradation of our planet's natural environment,
  and build a future in which humans live in harmony with nature.</p>
</article>

<!-- GOOD -->
<figure>
  <img src="pic_mountain.jpg" alt="The Pulpit Rock" width="304" height="228">
  <figcaption>Fig1. - The Pulpit Rock, Norway.</figcaption>
</figure>
```

### Project structure

Each wordpress project should have next structure:

```
project
│   README.md
│   .ebextensions
│   .ebextensions-production
│   .ebextensions-staging
│   .ebextensions-unused
│   package.json
│   wp-config.php
│   wp-config.php.production
│   ...
│
└───wp-content
    │   ...
    │
    └───releases
    │   └───original
    │   │       mysql-dump.sql.zip
    │   └───current
    │   │       current-mysql-dump.sql.zip
    │   └───1.0.0
    │   │       2018-04-26--production-before-this-release.sql.zip
    │   └───1.0.1
    │           2018-05-26--production-before-this-release.sql.zip
    │
    └───scripts
            git-pull.sh
            ...
 
```

### JavaScript Coding Style

Use soft tabs set to 4 spaces.

You can configure tab size at: 
    
``` Preferences → Editor → Code Style → JavaScript → Tab Size ``` :four: 

``` Preferences → Editor → Code Style → JavaScript → Indent ``` :four:
    
``` Preferences → Editor → Code Style → JavaScript → Continuation Indent ``` :four:

```
// GOOD
function() {
∙∙∙∙var name;
}

// BAD
function() {
∙∙var name;
}
```

### CSS Media Queries

Almost all device resolution can be found on this resource: [CSS Pixel Widths](https://www.canbike.org/CSSpixels/)

We use next list of media queries:
```
/* Mobile */

  // Apple iPhone 4S ( 640 x 960 ) DPR: 2.0
  @media only screen and (min-width: 319.98px) and (min-height: 479.98px) {}

  // Samsung Galaxy S6 ( 1440 x 2560 ) DPR: 4.0
  @media only screen and (min-width: 359.98px) and (min-height: 639.98px) {}

  // Apple iPhone 6 ( 750 x 1334 ) DPR: 2.0
  @media only screen and (min-width: 374.98px) and (min-height: 666.98px) {}


/* Desktop */

  // MacOS - Extra Small ( 1024 x 640 )
  @media only screen and (min-width: 1023.98px) {}

  // MacOS - Small ( 1280 x 800 )
  @media only screen and (min-width: 1279.98px) {}

  // MacOS - Medium ( 1440 x 900 )
  @media only screen and (min-width: 1439.98px) {}

  // MacOS - Large ( 1680 x 1050 )
  @media only screen and (min-width: 1679.98px) {}

  // MacOS - Extra Large ( 1920 x 1200 )
  @media only screen and (min-width: 1919.98px) {}
```

### Image Optimization

- Optimizilla 

Please, optimize all site images with http://imagecompressor.com/
    
### Font Optimization

- Transfonter

Please, optimize all site fonts with https://transfonter.org/




