# Concepts and Context
## Going Deeper When You're Curious

This document offers more context for ideas you meet in the tutorial. You do not need to read it to complete the exercises. Many people learn better by doing first and reading explanations later, or never. Come back here when something puzzles you, or when you want to understand not only what works but why it works.

These explanations are one way of thinking about these ideas. As you gain experience, you will develop your own mental models, and they might be quite different. That is fine. The goal is not to memorize definitions but to build understanding through practice.

---

## Every Element Is a Box

This is perhaps the most useful mental model for understanding CSS layout. Every element on a web page is a rectangular box. That includes every heading, paragraph, image and div. It includes text that flows in a line, circular images, and things that do not look rectangular at all. Everything is a box.

Each box has four layers, working from the inside out:

**Content** is the thing itself: your text, your image, whatever the element contains.

**Padding** is space between the content and the border. It is like the space between a picture and its frame. Padding takes on the background color of the element.

**Border** is the edge. It can be visible, with a color and style, or invisible, with zero width. Rounded corners affect the border.

**Margin** is space outside the border. It pushes other elements away. Margins are always transparent.

When you set `width: 200px`, what exactly is 200 pixels wide? By default, only the content. Padding and border add extra width. This is confusing, which is why the tutorial sets `box-sizing: border-box` on everything. With border-box, `width: 200px` means the whole box, content plus padding plus border, is 200 pixels. The content shrinks to fit.

If elements are not appearing where you expect, thinking in terms of boxes often helps. Where does this box's margin end? What is the padding doing? Is the box as wide as you think it is?

---

## How Browsers Build Pages

When your browser loads an HTML file, it does not display the text directly. It reads through the code and builds a tree structure in memory. This tree is called the Document Object Model, or DOM.

Imagine your HTML as a family tree. The `<html>` element is at the top. It has two children: `<head>` and `<body>`. The body has children like `<header>`, `<main>` and `<footer>`. The main element might contain several `<section>` elements. Each section might contain `<h2>`, `<p>` and `<div>` elements. And so on.

This tree structure matters because CSS uses it to work out which styles apply where. When you write a selector like `.hero h1`, you are saying "find any h1 that has an ancestor with class hero". The browser walks down the tree to find matches.

The tree also explains inheritance. When you set `color: blue` on the body, text inside paragraphs inside divs inside sections all turns blue. They are all descendants of body. Some properties inherit down the tree and others do not. If you are puzzled about why a style is not applying, inheritance, or the lack of it, might be the reason.

---

## What Semantic HTML Means

HTML has many different tags. They fall into two groups: tags that say what the content is, and tags that only create containers.

A `<div>` creates a generic container. It groups things together but says nothing about what those things are. A `<nav>` also creates a container, but it says: this is navigation. A `<header>` says: this is introductory content for the page or section. A `<main>` says: this is the primary content.

Why does this matter? Screen readers are software that reads pages aloud for people who cannot see them. A screen reader can announce "navigation" when it meets a `<nav>` tag. Search engines use semantic tags to understand which content matters most. Other developers reading your code can quickly grasp the page structure.

Using semantic tags mostly does not change how your page looks. It changes what your page means. When you are choosing between `<div>` and a more specific element, ask: is there a tag that says what this content is?

---

## How CSS Selectors Find Elements

A CSS rule starts with a selector that says which elements to style. Selectors range from very broad to very specific.

**Element selectors** target all elements of a type. `p` selects every paragraph. `h1` selects every level-one heading.

**Class selectors** start with a dot and target elements with that class attribute. `.card` selects every element with `class="card"`. An element can have several classes, and many elements can share a class.

**ID selectors** start with a hash and target the one element with that ID. `#contact` selects the element with `id="contact"`. Each ID should appear only once on a page.

**Descendant selectors** combine selectors with a space. `.hero h1` selects h1 elements that are inside an element with class hero. They can be anywhere inside it, not only direct children.

**Combinations** can get quite specific. `.skills-section .card:hover` selects cards inside the skills section, but only while the mouse is over them.

When you are trying to style something and it is not working, the selector is often the problem. Is it specific enough? Is it too specific? Does it match what you think it matches?

---

## When Rules Conflict: Specificity

What happens when two CSS rules both try to style the same element? The browser needs a way to decide which rule wins.

Specificity works like a scoring system. Each type of selector adds points:
- Element selectors (`p`, `h1`) = 1 point
- Class selectors (`.card`) = 10 points  
- ID selectors (`#contact`) = 100 points

The higher score wins. So `.hero h1` (10 + 1 = 11) beats `h1` (1). And `#contact .btn` (100 + 10 = 110) beats `.section .btn` (10 + 10 = 20).

If the scores are equal, the rule that appears later in the CSS file wins.

If your style is not applying, there is probably a more specific rule overriding it. The browser's developer tools can show you which rules are competing and which one won.

---

## Units: Pixels, Rems, Percentages

CSS offers many ways to give a size. The choice matters for consistency and for accessibility.

**Pixels (px)** are fixed. `16px` is always 16 pixels, whatever else is going on. Predictable, but inflexible.

**Rems** are relative to the root font size. Browsers set this to 16px by default, so `1rem` equals `16px`. The main benefit is this: some people set their browser to use larger fonts, which is common for people with visual impairments. If your sizes are in rems, they all scale up to match. Using rems for font sizes and spacing makes your site more accessible.

**Percentages** are relative to the parent element. `width: 50%` means half the parent's width. They are useful for flexible layouts that adapt to their containers.

**Viewport units** are relative to the browser window. `100vh` is 100% of the viewport height. They are useful for full-screen sections.

The tutorial uses rems for most spacing and font sizes. This is a deliberate choice. It makes the site adapt better to different people's settings.

---

## Layout with Flexbox

Before flexbox, laying out elements side by side was surprisingly awkward. Flexbox makes it straightforward.

Set `display: flex` on a container, and its children become flex items that you can arrange in rows or columns.

Two properties do most of the work:

**justify-content** controls spacing along the main axis, which is horizontal by default. `space-between` pushes the first item to the start and the last to the end, with space shared between them. `center` groups the items in the middle.

**align-items** controls position along the cross axis, which is vertical by default. `center` centers the items vertically. `stretch` makes them all the same height.

The header in the tutorial uses flexbox to put the logo on the left and the navigation on the right, with `justify-content: space-between`. The navigation list uses flexbox to arrange its links horizontally.

Flexbox can do much more, but these basics handle most everyday layout needs. When you want more, Flexbox Froggy, linked in the resources, is a playful way to learn.

---

## Responsive Design and Media Queries

People view websites on phones, tablets, laptops and large monitors. A layout that works well at one size might be cramped or sparse at another. Responsive design means creating layouts that adapt.

Media queries are the main tool. They let you apply CSS rules only when certain conditions are met:

```css
@media (max-width: 768px) {
    /* These rules only apply when the viewport is 768px or narrower */
}
```

The tutorial uses this to stack the navigation vertically on smaller screens, where a horizontal layout would be too cramped.

You can also use `min-width` to target larger screens:

```css
@media (min-width: 1200px) {
    /* These rules only apply above 1200px */
}
```

There are two common approaches. One starts with small screens and adds complexity for larger ones. This is called mobile-first. The other starts with large screens and adjusts for smaller ones. This is called desktop-first. Which you use is a matter of preference. The important thing is to think about how your layout works at different sizes.

---

## CSS Variables

CSS variables, officially called custom properties, let you define a value once and reuse it throughout your stylesheet.

```css
:root {
    --primary-color: #2c3e50;
}

.header {
    background-color: var(--primary-color);
}
```

The benefit is more than avoiding repetition. Variables make your styles easier to maintain and understand. Want to change your site's primary color? Change it in one place. Want to know what color something is? The variable name tells you it is the primary color, rather than leaving you with a hex code.

Variables also make theming possible. You could define different values for a dark mode, then switch the variables based on the user's preference.

---

## Transitions and Transforms

CSS can animate changes smoothly, which gives visual feedback when people interact with the page.

**Transitions** animate a change in a property over time. Instead of a color switching from blue to red at once, it shifts smoothly over a fraction of a second.

One thing is worth knowing here. Define the transition on the base state, not on the hover state. Then the animation works in both directions, hovering on and hovering off.

```css
.button {
    background-color: blue;
    transition: background-color 0.2s ease;
}

.button:hover {
    background-color: red;
}
```

**Transforms** change an element's position, size or shape without affecting the layout around it. `translateY(-5px)` lifts an element up. `scale(1.1)` makes it larger. `rotate(45deg)` rotates it.

Combining transitions and transforms creates effects like the card hover in the tutorial, where the card appears to lift towards the viewer.

---

## Further Exploration

The resources in the main README offer paths for continued learning. Interactive games like Flexbox Froggy and Grid Garden build understanding through play. MDN Web Docs is a thorough reference for when you need to look something up.

Resources only take you so far. The deeper understanding comes from building things, meeting problems, and working through them. When something does not work the way you expect, that is the learning itself, not an obstacle to it.
