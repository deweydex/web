# HTML & CSS Foundations Tutorial
## Building Your First GitHub Pages Site

Welcome. By the end of this tutorial, you will have a personal website hosted on GitHub Pages. It will be a real site with a real address that you can share with anyone.

---

## Before We Begin: A Note on Learning

There are countless tutorials, videos and references for learning HTML and CSS. You could spend weeks reading documentation before writing a single line of code. This tutorial takes a different approach.

**This is a sandbox.** Nothing here can break in any permanent way. If you make a change and everything looks wrong, nothing has failed. You have learned something about what that property does. If you want to start again from the beginning, you can fork the repository again.

**Puzzling things out has value.** When you meet something unfamiliar, try not to open another tab and search for the answer immediately. Pause for a moment. Try changing values. See what happens. Make a guess about how something works, then test your guess. This kind of exploration builds an understanding that reading documentation alone cannot give you.

**You do not need to understand everything right away.** Some ideas only make sense after you have met them several times in different contexts. That is normal. Keep moving forward even when things feel uncertain. Being comfortable with not knowing yet is part of learning.

The exercises below invite you to experiment. They suggest things to try, and you are welcome to go beyond them. The comments in the code files explain what things are called and roughly what they do. Use them as a reference when you are curious. They are not required reading.

---

## What You'll Need

- A GitHub account (free at github.com)
- A text editor (VS Code is popular, but any editor works)
- A web browser
- A willingness to experiment

No prior experience with HTML, CSS or programming is assumed.

---

## The Files

Once you fork this repository, you will have:

- `index.html`: your homepage
- `about.html`: a second page
- `styles.css`: the stylesheet that controls how the pages look
- `README.md`: this file, with the instructions and exercises
- `CONCEPTS.md`: deeper explanations for when you want more context (optional reading)

The HTML and CSS files contain many comments explaining what each part does. These comments are there for you. Browse them when you are curious.

---

## Quick Reference: What Things Are Called

You will meet these terms throughout. There is no need to memorize them now. Come back here when you need them.

**In HTML:** A **tag** is the thing in angle brackets, like `<p>` or `</p>`. An **element** is a complete unit: opening tag, content, closing tag. An **attribute** adds information to a tag, written as `name="value"`. A **class** is an attribute for grouping elements (`class="card"`). An **ID** is an attribute that identifies one element (`id="contact"`).

**In CSS:** A **selector** says which elements to style (`.card`, `#contact`, `p`). A **property** is what you are changing (`color`, `padding`). A **value** is what you are setting it to (`blue`, `20px`). A **rule** puts these together: a selector, then curly braces holding property and value pairs.

**Example:**
```html
<section class="hero" id="top">
    <h1>Welcome</h1>
</section>
```
```css
.hero {
    background-color: #2c3e50;
    padding: 2rem;
}
```

Here, `section` and `h1` are tags. The whole `<section>...</section>` is an element. `class="hero"` is an attribute. `.hero` is a CSS selector that finds elements with that class. `background-color` is a property and `#2c3e50` is its value.

---

## Part 1: Getting Set Up

### Exercise 1: Fork and Clone

Let's get your own copy of this project.

1. Click the **Fork** button in the top-right corner of this repository on GitHub.
2. This creates your own copy, which you can change freely.
3. Either clone it to your computer, or use GitHub's web editor. To use the web editor, click any file, then click the pencil icon.

### Exercise 2: Enable GitHub Pages

Let's put your site on the internet right away. Then every change you make becomes visible at a real address.

1. Go to your forked repository on GitHub.
2. Click **Settings** (the gear icon).
3. In the left sidebar, click **Pages**.
4. Under "Source", select **Deploy from a branch**.
5. Under "Branch", select **main** and **/ (root)**.
6. Click **Save**.
7. Wait a minute or two, then refresh the page.
8. You will see an address like `https://yourusername.github.io/repository-name/`.

Visit that address. You should see the template site. Bookmark it, because you will be checking it often.

### Exercise 3: Your First Change

Let's make something visibly different, so you know everything is working.

Open `index.html` and find the `<title>` element near the top, inside the `<head>` section. It currently says "My Portfolio". Change it to your name, or to anything else you like. Save the file.

If you are working on your own computer, refresh the browser. If you are using GitHub's web editor, commit your change, then wait a minute for GitHub Pages to rebuild.

Look at your browser tab. The text there should show your change. You have edited HTML and published it to the internet.

**Explore:** What happens if you make the title very long? What if you leave it completely empty?

---

## Part 2: Working Through Your Homepage

Now let's work through `index.html` from top to bottom, making it yours.

### Exercise 4: The Main Heading

Find the `<h1>` element in the hero section. It says "Welcome to My Portfolio". This is the main heading that visitors see.

Change it to something that represents you. Save and refresh.

**Explore:** The `<title>` appears in the browser tab. The `<h1>` appears on the page itself. Try making them identical, then try making them different. Which feels right for your site?

### Exercise 5: Your Introduction

Find the paragraph below the `<h1>`. It has `class="hero-text"`. This is your chance to introduce yourself.

Rewrite it in your own voice. Who are you? What are you working on? What interests you? A few sentences is plenty.

**Explore:** Try writing something very formal, then rewrite it casually. Notice how the same information can feel completely different.

### Exercise 6: Emphasis and Importance

HTML has tags that say certain words matter: `<strong>` for important text and `<em>` for emphasized text. Browsers usually show these as bold and italic. The tags carry a meaning beyond how they look.

In your introduction paragraph, wrap one important word or phrase in `<strong>` tags. Wrap something you want to emphasize in `<em>` tags.

**Explore:** Try `<b>` instead of `<strong>`, and `<i>` instead of `<em>`. Do they look the same? They often look the same, but they mean different things to screen readers and search engines. What happens if you nest them: `<strong><em>word</em></strong>`?

### Exercise 7: The About Preview Section

Scroll down to find the section with "A Little About Me". Inside is a card with placeholder text.

Rewrite this placeholder to give visitors a preview of who you are. This section links to your About page, so think of it as a short introduction to that page.

### Exercise 8: Adding a Skills Section

Let's add some new content. After the closing `</section>` tag of the about-preview section, add a new section:

```html
<section id="skills" class="section skills-section">
    <div class="container">
        <h2>What I'm Learning</h2>
        <p>Write something here about skills you're developing.</p>
        <div class="card">
            <h3>Technical Skills</h3>
            <p>List some things you're learning or want to learn.</p>
        </div>
    </div>
</section>
```

Save and refresh. The new section should appear, already styled. It inherits its styles from the `.section` and `.card` classes defined in the CSS file.

**Explore:** What happens if you remove `class="section"` from your new section? What styling disappears? Add it back, then try removing `class="card"` from the inner div instead.

### Exercise 9: Adding an Image

Let's add an image to your page. Inside your about-preview section, or your new skills section, try adding:

```html
<figure class="profile-image">
    <img src="https://picsum.photos/400/300" alt="A description of what's in the image">
    <figcaption>A caption for the image</figcaption>
</figure>
```

The `picsum.photos` address gives you a random placeholder image. Later you can replace it with an image of your own.

The `alt` attribute describes the image for people who cannot see it, for example people using screen readers. It also appears if the image fails to load. Write something meaningful there.

**Explore:** What happens if you remove the `alt` attribute entirely? Try leaving it empty (`alt=""`), then try removing it completely. What if you use a broken address for the `src`?

### Exercise 10: Linking to Your About Page

Find the button in the about-preview section. It is the `<a>` tag with `class="btn"`. It should already link to `about.html`.

Click it. You should arrive at the About page. Look at the navigation bar on both pages. There is already a link back.

**Explore:** Change `href="about.html"` to `href="abut.html"` (misspelled) and click the link. This is what a broken link looks like. Fix it afterwards.

### Exercise 11: Adding a Contact Section

Before the closing `</main>` tag, let's add a contact section:

```html
<section id="contact" class="section contact-section">
    <div class="container">
        <h2>Get In Touch</h2>
        <p>I'd love to hear from you.</p>
        <a href="mailto:your.email@example.com" class="btn">Send Me an Email</a>
    </div>
</section>
```

Replace the email address with your own, or leave it as a placeholder for now.

**Explore:** Click the email link. What happens? The `mailto:` prefix tells the browser to open an email application. What if you change it to `mailto:` with nothing after it?

### Exercise 12: Navigation

Find the `<nav>` element in the header. Update the links to point to your sections:

```html
<nav class="main-nav" aria-label="Main">
    <ul>
        <li><a href="index.html">Home</a></li>
        <li><a href="about.html">About</a></li>
        <li><a href="#skills">Skills</a></li>
        <li><a href="#contact">Contact</a></li>
    </ul>
</nav>
```

The `#skills` and `#contact` links are **anchor links**. They point to elements with those IDs on the same page. When clicked, the browser scrolls to that section.

For this to work, the sections need matching `id` attributes. You added those in exercises 8 and 11.

The `aria-label="Main"` attribute gives the navigation a name. A screen reader can then say "Main navigation" rather than just "navigation". This matters once a page has more than one `<nav>`.

**Explore:** Click the Skills link. The page should scroll smoothly to that section. Now look in the CSS file for `scroll-behavior: smooth`. That is what creates the smooth scrolling. Try changing it to `scroll-behavior: auto` and clicking the link again.

---

## Part 3: Exploring the Stylesheet

Now let's turn to `styles.css`. Open it in your editor and scroll through it. Notice the many comments explaining each section.

### Exercise 13: Changing Colors

Near the top of `styles.css`, find the `:root` section. It defines CSS variables, also called custom properties. A variable is a value you can reuse throughout the stylesheet.

Find `--primary-color` and `--accent-color`. Change them to colors you like. Save and refresh.

Notice how many elements changed at once. The header, the hero section, the footer and the buttons all use these variables.

The default colors were chosen so that text stays readable. White text on the accent color, and grey text on the light background, both pass the contrast check that accessibility guidelines ask for. A contrast checker, such as the one at [webaim.org](https://webaim.org/resources/contrastchecker/), tells you whether two colors pass.

**Explore:** Try setting both colors to the same value. Try very bright colors. Try colors that do not stand out well against white text. What makes a color scheme work, or not work? Do your colors pass the contrast checker?

If you want help choosing colors, [coolors.co](https://coolors.co) can generate palettes.

### Exercise 14: Backgrounds and Gradients

Find the `.hero` rule in the CSS file. Its background currently uses `var(--primary-color)`.

Try changing it to a gradient:
```css
background: linear-gradient(135deg, var(--primary-color), var(--accent-color));
```

**Explore:** Change the angle (135deg) to other values: 0, 45, 90, 180. Watch how the direction of the gradient shifts. Try `radial-gradient(circle, var(--primary-color), var(--accent-color))` for a completely different effect.

### Exercise 15: The Box Model

Every element on a web page is a rectangular box with four layers: content, padding, border and margin. Understanding this is the foundation of CSS layout.

Find the `.card` rule. Notice the `padding` property. Try changing it:
- Set padding to `0` and see how cramped the content becomes.
- Set padding to `4rem` and see how much space that creates.
- Try `padding: 1rem 3rem` for different values on each axis. The first value is vertical, the second horizontal.

**Explore:** Now find a rule with `margin` (try `.container`). Padding is space inside the element. Margin is space outside it. Try adding `margin: 2rem` to `.card` and notice how the cards push away from each other.

### Exercise 16: Borders and Rounded Corners

Still in the `.card` rule, find `border-radius`. This controls how rounded the corners are.

- Try `border-radius: 0` for sharp corners.
- Try `border-radius: 20px` for very rounded corners.
- Try `border-radius: 50%`. What happens depends on the shape of the element.

Add a visible border: `border: 2px solid var(--accent-color);`

**Explore:** Try different border styles: `dashed`, `dotted`, `double`. Try different widths. Try a different radius for each corner: `border-radius: 0 20px 0 20px;`

### Exercise 17: Text and Typography

Find the `.hero` rule and look at `text-align: center`.

Try changing it to `text-align: left`. Then try `text-align: right`.

**Explore:** Add a long paragraph somewhere and try `text-align: justify`. Resize your browser window and watch how the spacing between words changes. Which alignment is easiest to read for long text?

### Exercise 18: Making Sections Look Different

Right now all sections use the same styling. Let's make your skills section look different.

Add this to your CSS file, near the bottom, before any `@media` rules:

```css
.skills-section {
    background-color: var(--light-gray);
}

.skills-section .card {
    border-left: 4px solid var(--accent-color);
}
```

The selector `.skills-section .card` means "cards that are inside an element with the class skills-section". It styles those cards without affecting cards elsewhere.

**Explore:** Change `.skills-section .card` to just `.card` and watch what else on the page changes. This is CSS specificity at work. A more specific selector overrides a less specific one.

---

## Part 4: Layout and Positioning

### Exercise 19: The Container

Find the `.container` rule. Notice `max-width: 1200px` and `margin: 0 auto`.

The `max-width` stops content from stretching too wide on large screens. The `margin: 0 auto` centers the container horizontally. Automatic margins on the left and right share the available space evenly.

**Explore:** Change `max-width` to `600px` (very narrow) or `100%` (full width). Remove `margin: 0 auto` and see what happens. Try `margin-left: auto` without `margin-right: auto`.

### Exercise 20: Sticky Header

Find the `header` rule. Notice `position: sticky` and `top: 0`.

Scroll down your page. The header stays visible at the top. That is what sticky positioning does.

**Explore:** Change `position: sticky` to `position: fixed`. Scroll again. What is different? Look at the content behind the header for a clue. Change it to `position: relative`, which is the default, and the header scrolls away with the content. Set it back to `sticky`.

### Exercise 21: The Footer

Find the `footer` rule. Notice `margin-top: auto`.

This works because the `body` is set to `display: flex` with `flex-direction: column`. The automatic margin pushes the footer to the bottom, even when there is little content.

**Explore:** Remove `margin-top: auto` from the footer. Then leave only a few words on your page by temporarily deleting most of the content. Where does the footer end up? Add the automatic margin back.

---

## Part 5: Interactivity and Polish

### Exercise 22: Hover Effects

Let's make the cards respond when you hover over them. Add to your CSS:

```css
.card {
    transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.card:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
}
```

The transition property might already be there. If so, make sure the hover rule is added.

Hover over a card. It should lift slightly and its shadow should deepen.

**Explore:** Try `transform: translateY(-20px)` for a more dramatic lift. Try `transform: scale(1.05)` instead. Now the card grows rather than lifts. Change `0.2s` to `1s` to see the animation in slow motion.

### Exercise 23: Focus States

When someone moves through your site with a keyboard, pressing Tab to move between links, they need to see where they are. That is what focus styles are for.

Find the `a:focus` rule in the CSS. Press Tab repeatedly on your page and watch the outline move between links.

The very first Tab press lands on a link that says "Skip to main content". It is hidden until it has focus. It lets a keyboard user jump past the navigation instead of pressing Tab through every link on every page. Look for `.skip-link` in the CSS to see how it is hidden and shown.

**Explore:** Try removing the `:focus` rule entirely. Move through the page with Tab. Can you tell where you are? This is why focus styles matter for accessibility. Add the rule back.

### Exercise 24: Responsive Design

Open your browser's developer tools (usually F12) and find the device toolbar or responsive mode. Resize to a narrow width, like a phone.

Now find the `@media` section at the bottom of the CSS file. The rules inside `@media (max-width: 768px)` only apply when the screen is 768 pixels wide or narrower.

Add another breakpoint for very small screens:

```css
@media (max-width: 480px) {
    .hero h1 {
        font-size: 1.75rem;
    }
    
    .container {
        padding: 0 1rem;
    }
}
```

**Explore:** Change `max-width: 480px` to `max-width: 800px`. Notice when the styles start to apply. Try `min-width` instead of `max-width`. Now the rules apply above that size instead of below it.

### Exercise 25: Finishing Touches

A few small things to complete your site:

**Favicon:** This is the small icon in the browser tab. Create one at [favicon.io](https://favicon.io) and add it to the `<head>` of both HTML files:
```html
<link rel="icon" type="image/x-icon" href="favicon.ico">
```

**About Page:** Open `about.html` and replace all the placeholder content with real information about yourself.

**Footer:** Update the copyright year and name in both HTML files.

**Review:** Look at your site at both desktop and phone sizes. Click all your links. Is there placeholder text you forgot to replace?

---

## Part 6: Keep Going

You now have a working personal site. Here are some paths forward.

**Add more content.** Create new pages for projects, a blog, or anything else. Link to them from your navigation.

**Learn more CSS.** The CONCEPTS.md file in this repository explains some ideas in more depth. When you are ready for more, the resources below offer interactive practice.

**Learn JavaScript.** HTML structures content, CSS styles it, and JavaScript makes it interactive. That is a natural next step.

**Keep experimenting.** The best way to learn is to try things, break things, and work out how to fix them.

---

## Resources

### Interactive Learning

**Flexbox Froggy**: learn CSS flexbox by helping a frog reach lily pads  
https://flexboxfroggy.com

**Grid Garden**: learn CSS grid by watering a garden  
https://cssgridgarden.com

**CSS Diner**: practice CSS selectors by selecting plates and food  
https://flukeout.github.io

**Codepip**: a collection of games for learning CSS  
https://codepip.com

### Reference Documentation

**MDN Web Docs**: Mozilla's reference for HTML, CSS and JavaScript. When you need to look something up, this is the place.  
https://developer.mozilla.org/en-US/docs/Web

**CSS-Tricks**: practical guides, especially the Complete Guide to Flexbox and the Complete Guide to Grid.  
https://css-tricks.com

### Continued Learning

**The Odin Project**: a free, full curriculum for web development  
https://www.theodinproject.com

**freeCodeCamp**: an interactive curriculum with certificates  
https://www.freecodecamp.org

---

## What You've Practiced

Working through these exercises, you have met:

- HTML document structure and the relationship between elements
- Semantic elements like header, main, nav, section, article, footer
- Attributes including class, id, href, src, alt
- CSS selectors, properties, and values
- The box model: content, padding, border, margin
- CSS variables for consistent theming
- Layout techniques including flexbox and centering
- Positioning: static, relative, sticky, fixed
- Pseudo-classes like :hover and :focus
- Media queries for responsive design
- Transitions for smooth animations

More importantly, you have practiced experimenting, breaking things, and working out how they work.

---

*This tutorial is provided for educational purposes. Modify and share freely.*
