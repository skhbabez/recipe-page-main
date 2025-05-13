# Frontend Mentor - Recipe page solution

This is a solution to the [Recipe page challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/recipe-page-KiTsR8QQKm). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)

**Note: Delete this note and update the table of contents based on what sections you keep.**

## Overview

### Screenshot

![](./screenshot.jpg)

### Links

- Solution URL: [https://github.com/skhbabez/recipe-page-main](https://github.com/skhbabez/recipe-page-main)
- Live Site URL: [https://skhbabez.github.io/recipe-page-main/](https://skhbabez.github.io/recipe-page-main/)

## My process

### Built with

- Semantic HTML5 markup
- CSS
- Flexbox
- Mobile-first workflow

### What I learned

I put additional effort into making the markup semantic, trying to utilize not only semantic elements, but also thinking more about the structure and avoiding unnecessary divs.

I refreshed my knowledge on CSS element selectors, using them to get more control on styling the lists according to the Figma file. While using `::marker `would have probably been enough, I tried to challenge myself using `::before` and counter to get a better idea for how they work. It was especially interesting to see how much control you have over list stylings this way. I will probably explore further options to do this in the future, figuring out how to simplify this. In this snippet I tried to center the text around the bullet points.

```css
.card :is(ul, ol) li {
  display: flex;
  gap: var(--space-4);
}

.card ul li {
  align-items: center;
}

.card ul li::before {
  content: "";
  width: 4px;
  height: 4px;
  border-radius: 50%;
  background-color: var(--brown-800);
  flex-shrink: 0;
}
```

Styling the image was also quite tricky, and I learned how to utilize a wrapper div to get more control over the image. This was necessary due to the aspect-ratio property in combination with `object-fit: cover` leaving a white space below the image.

```css
.card-img {
  aspect-ratio: 2 / 1;
  margin-bottom: var(--space-6);
}

.card-img img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}
```

Styling the table was challenging in regards to getting the spacings right. I experimented with the `border-collapse` property and got a better understanding of how this interacts with the `border-spacin`g property. This also got me to use the dev tools more to check what CSS is actually applied, which allowed me to figure out I needed to set the `vertical-align` property. It was also fun to experiment with the child selector and find a use for them that felt meaningful.

```css
.nutrition-table tbody tr:first-child :is(th, td) {
  padding-top: 0px;
  vertical-align: top;
}

.nutrition-table tbody tr:last-child :is(th, td) {
  padding-bottom: 0px;
  vertical-align: bottom;
}
```

Lastly, I tried to organize my CSS better, using a spacing system and trying to focus more on `rem` values when appropriate.

### Continued development

I will look deeper into using relational units like `em` and `rem`. I feel like I still lack a good feel for when to use them. I will also try to deepen my knowledge in regards to better class design. Currently, I overuse selectors where I could probably use classes. I will try a different approach in my next project, maybe utilizing a class approach like in Bootstrap. Otherwise, I will focus on refreshing my knowledge in CSS and HTML in general.

### Useful resources

- [https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content/Structuring_documents](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content/Structuring_documents) - This was a good read helping me to plan and structure the html for this project.
- [https://flexboxfroggy.com/](https://flexboxfroggy.com/) - Wonderful little game. I had some problems understanding the difference between align-content and align-items and this wonderful little game cleared this up.
