# Code Refactor

Welcome to the March 2022 release of the **_Hori<span style = "color:gray">seo</span>n_** website.

- Easy Navigation to the content of interest on **_<span style="color:yellow">single click</span>_**.
- **_<span style="color:yellow"> Tab enabled </span>_** navigation.
- Enhanced **_<span style="color:yellow">screen reader </span>_** experience.

## Now let's take a deep dive into the changes made to achieve above listed features

- <span style="text-decoration: underline"> Implementing **_Semantic HTML_**</span>

> Following semantic elements clearly describes its meaning to both the browser and the developer. The non-semantic elements tell nothing about its content. Reference: [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Glossary/Semantics#semantics_in_html)

so to make the code look semantically correct , div elements are replaced with <span style="color:yellow">header, section, aside and footer </span>elements wherever applicable.

Example code snippet:

Before:
~~`` `<div class="header"> <h1>Hori<span class="seo">seo</span>n</h1> <div>` ``~~

After:
Header with nav links

`` `<header class="hdr-main"> Hori<span class="hdr-main-span">seo</span>n` ``  
 `` `<nav>` ``  
 `` `<ul>` ``  
 `` `<li>` ``  
 `` `<a href=` ``

- <span style="text-decoration: underline"> Eliminating **_repeating CSS properties_**</span>

> There would be many scenarios where the CSS rules are same for multiple elements like sections, paragraphs, img etc., In such cases, CSS selectors would be higly useful in structurally organizing the rules as well as reducing the need to define the same properties over and over again. "CSS selectors define the elements to which a set of CSS rules apply." Reference: [CSS Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)

Example code snippet:

Before:
~~`` `.benefit-lead img {` ``~~
~~`` `display: block;` ``~~
~~`` `margin: 10px auto;` ``~~
~~`` `max-width: 150px; ` ``~~
~~`` `}` ``~~

~~`` `.benefit-brand img {` ``~~
~~`` `display: block;` ``~~
~~`` `margin: 10px auto;` ``~~  
 ~~`` `max-width: 150px;` ``~~
~~`` `}` ``` ``~~

After:

Define a common class for all the images and set the rule
`` `.container-child img {` ``
`` `height: 250px;` ``
`` `width: 350px;` ``
`` `padding: 30px;` ``
`` `}` ``

- <span style="text-decoration: underline"> Enhanced Screen Reader Accessibility</span>

> "The Web is fundamentally designed to work for all people, whatever their hardware, software, language, culture, location, or physical or mental ability. When the Web meets this goal, it is accessible to people with a diverse range of hearing, movement, sight, and cognitive ability." Reference: [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/Accessibility)

As mentioned in the MDN web docs, The most important quick win in semantic HTML is to use a structure of headings and paragraphs for the content. Because screen reader users tend to use the headings of a document as a sign post to find the content they need more quickly.

So, the code has been semantically and structurally organised using headers, headings, sections, <img> with alt text, <h>, <p> tags

Example code snippet

After:
`` `img` ``
`` `src="./images/social-media-marketing.jpg"` ``  
 `` `alt="social-media-marketing"` ``  
 `` `/>` ``

Certain HTML features can be selected using only the keyboard, such as pressing the tab key and then pressing Enter/Return will lead to its related content.

So in the new design, the links in the header navigation bar are tab enabled and on pressing enter on the link takes you to the available content below

Example:

Pressing tab and clicking Enter/Return on Search Engine Optimization link takes us to its content as shown in image2

![links navigation bar](images/Capture.PNG)

![link  Search Engine Optimization Content](images/Capture2.PNG)
