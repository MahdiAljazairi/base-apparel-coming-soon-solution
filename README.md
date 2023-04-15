# Frontend Mentor - Base Apparel Coming Soon Page Solution

This is a solution to the [Base Apparel coming soon page challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/base-apparel-coming-soon-page-5d46b47f8db8a7063f9331a0).  
Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

\*Me\* : I agree 👍

## Table of Contents

- [Overview](#overview)
  - [The Challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My Process](#my-process)
  - [About the Invalid State](#about-the-invalid-state)
  - [`method="dialog"`??](#method-dialog)
  - [What I Learned](#what-i-learned)
  - [Continued Development](#continued-development)
- [Tools](#tools)
- [Author](#author)

## Overview

### The Challenge

Users should be able to:

- View the optimal layout for the site depending on their device's screen size
- See hover states for all interactive elements on the page
- Receive an error message when the `form` is submitted if:
  - The `input` field is empty
  - The email address is not formatted correctly

### Screenshot

![My Fabulous Work!](./screenshot.png)

### Links

- Solution URL: <https://www.frontendmentor.io/solutions/carpet-of-fury-Z5Q_N-MIjw>
- Live Site URL: <https://base-apparel-coming-soon-solution-123.netlify.app>

## My Process

### About the Invalid State

When you look at the CSS, you'll notice that I used a `[data-invalid]` attribute, with some help of Javascript, on the `input` element to indicate whether it's invalid or not instead of simply an `:invalid` pseudo-class. This is because if I used the pseudo-class, the `input` would show invalid state styles immediately when the page loads -- since, of course, the `input` is `required`. Then, those styles would disappear the moment you type in a valid email address.

We don't want that. Because, as per the terms of the challenge, form validation should take place only if there was an attempt to submit the form. And this is exactly what I did. I put an `onclick` to call a function named `checkInput()` on my `button`, as it's the form's only submit button. This means it would still work even if the form was submitted using the Enter key. The form would behave as if its submit button has been clicked.

### `method="dialog"`??

I put a method of "dialog" on the form because otherwise the page would reload when the form is submitted as I didn't provide an actual `action` URL. This is for demo purpose only. In production, this should be switched to "post" instead.

### What I Learned

You can't animate a `background-blend-mode`, but you can animate a `background-color` instead:

```css
button.submit {
  /*  ...  */
  background-color: hsl(0, 0%, 50%); /* This won't alter anything */
  background-image: url(images/icon-arrow.svg),
                    linear-gradient(135deg, white, #fff5f5);
  background-blend-mode: overlay; /* MAGIC! */
  /*  ...  */
  transition: background-color 200ms;
}

button.submit:hover,
button.submit:active {
  background-color: hsl(0, 0%, 75%); /* This will lighten up the gradient */
}
```

Now I feel dumb because I could've just used `filter`. Still, It's fun to explore different ways to do something..

### Continued Development

I need to speed up the process.

## Tools

- [Dev Docs](https://devdocs.io) - The resource I was constantly referring to throughout the process. It's an offline web app that has a huge collection of documentations.
- [Brackets](https://brackets.io) - My text editor. Not as powerful as VS Code, but still my favorite.
- Chrome - This web page was only tested on Chrome. 

## Author

- GitHub - [Mahdi Aljaza'iri](https://github.com/MahdiAljazairi)
- Frontend Mentor - [@MahdiAljazairi](https://www.frontendmentor.io/profile/MahdiAljazairi)
