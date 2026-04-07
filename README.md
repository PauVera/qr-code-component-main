# Frontend Mentor - QR code component solution

This is a solution to the [QR code component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/qr-code-component-iux_sIO_H). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [AI Collaboration](#ai-collaboration)
- [Author](#author)


## Overview

### Screenshot

![Desktop solution](/images/mi-solucion/Frontend-Mentor-QR-code-component_desktop.png)
![Mobile solution](/images/mi-solucion/Frontend-Mentor-QR-code-component_movil.png)

### Links

- Solution URL: [Solution in Frontend Mentor](https://www.frontendmentor.io/solutions/responsive-qr-card-using-css-layers-tokens-flexbox-and-grid-GrqXDLPZJd)
- Live Site URL: [Live site in Github pages](https://pauvera.github.io/qr-code-component-main/)

## My process

### Built with

- Semantic HTML5 markup
- Mobile-first workflow
- Design tokens (CSS custom properties)
- Flexbox
- CSS Grid
- Component-based CSS architecture

### What I learned

The most significant learning from this project came from working through a layout problem that pushed me to think more carefully about how flexbox distributes space.
My initial approach used `display: grid` with `place-items: center` on the body to center the card. But once I decided to keep the attribution `<footer>` in the HTML, that approach broke down because grid was treating the card and the footer as two items to center together, not as a column where one grows and the other stays at the bottom.
This fix made something click for me. By switching `body` to `display: flex; flex-direction: column` and giving the `.wrapper` a `flex: 1`, the available viewport height gets distributed intentionally, making the wrapper expand to fill all remaining space, and the footer stays anchored at the bottom withou needing `position: fixed` or any magic number.

```css
/* base layer - body establishes the flex column */
body {
  min-height: 100svh;
  display: flex;
  flex-direction: column;
}

/* utilities layer - wrapper claims all remaining space  */
.wrapper {
  flex: 1;
}
```

The second thing I practiced was organizing CSS with `@layer`. Separating reset, tokens, base, components, and utilities from the start, even for a small project, kept specificity predictable and made it easy to see where each rule belonged.

```css
@layer reset, tokens, base, components, utilities;
```

Both of these feel like habits worth building early, before projects get complex enough to make them painful to retrofit.

### Continued development

The areas I want to keep focusing on in upcoming projects are layout, design systems and accesibility.

For layout, I want to get more deliberate about choosing between flexbox and grid from the start, understanding how each works, but more importantly which model fits a given problem before writing any CSS.

For design systems, I want to keep practicing th `@layer` and token approach I used here, and gradually develop a more considered system for naming and scaling values (spacing, type, color) in a way that stays consistent across projects.

For accesibility, this project was simple enough that it didn't surface many challenges, but I want to make it a habit to think about semantics, focus management, and contrast from the beginning rather than as an afterthought.

### AI Collaboration

I used ChatGPT during development to validate my code, explore alternative solutions, and get feedback on semantic HTML and CSS architecture, particularly whether my use of `@layer` made sense for a project of this scale.

I used Claude to help me articulate and write this documentation in English, translating what I wanted to say into clear, precise prose.

In both cases, I wasn't looking for the AI to make decisions for me, but to think out loud with something that could push back. That worked well. What requires more attention is knowing when a suggestion is genuinely better versus just different. That judgement still has to come from me.

## Author

- Website - [Pau's Github](https://github.com/PauVera)
- Frontend Mentor - [@PauVera](https://www.frontendmentor.io/profile/PauVera)