# HTML & CSS Foundations Tutorial
## Building Your First GitHub Pages Site

Welcome. By the end of this tutorial, you'll have a working personal website hosted on GitHub Pages—a real site with a real URL that you can share with anyone.

## Where This Fits

This tutorial is Step 1 of the Web Authoring and Databases course. The course front page is at [deweydex.github.io/dewstack](https://deweydex.github.io/dewstack/). It holds the plan for the whole course and every link you need. When an exercise here leaves you with a question, the [tutorials](https://deweydex.github.io/dewstack/tutorials/) there have the longer explanation. The [GitHub guides](https://deweydex.github.io/dewstack/tutorials/github-guides/01-getting-started.html) show each step of making an account, saving your work, and publishing a site.

---

## Before We Begin: A Note on Learning

There are countless tutorials, videos, and references for learning HTML and CSS. You could spend weeks reading documentation before writing a single line of code. This tutorial takes a different approach.

**This is a sandbox.** Nothing here can break in any permanent way. If you make a change and everything looks wrong, that's not failure—that's information. You've learned something about what that property does. If you want to start completely fresh, you can always fork the repository again.

**Puzzling things out has value.** When you encounter something unfamiliar, resist the urge to immediately open another tab and search for the answer. Sit with it for a moment. Try changing values. See what happens. Make a guess about how something works, then test your guess. This kind of exploration builds intuition that reading documentation alone cannot provide.

**You don't need to understand everything right away.** Some concepts won't click until you've encountered them several times in different contexts. That's normal. Move forward even when things feel uncertain. Comfort with indeterminacy is part of the learning process.

The exercises below invite you to experiment. They'll suggest things to try, but feel free to wander off the path. The comments in the code files explain what things are called and roughly what they do—use them as a reference when you're curious, not as required reading.

---

## What You'll Need

- A GitHub account (free at github.com)
- A text editor (VS Code is popular, but any editor works)
- A web browser
- Willingness to experiment

No prior experience with HTML, CSS, or programming is assumed.

---

## The Files

Once you fork this repository, you'll have:

- `index.html` — Your homepage
- `about.html` — A second page
- `styles.css` — The stylesheet that controls appearance
- `README.md` — This file (instructions and exercises)
- `CONCEPTS.md` — Deeper explanations if you want more context (optional reading)

The HTML and CSS files contain extensive comments explaining what each part does. These comments are for your reference—browse them when curious.

---

## Quick Reference: What Things Are Called

You'll encounter these terms throughout. Don't memorize them now; refer back when needed.

**In HTML:** A **tag** is the thing in angle brackets like `<p>` or `</p>`. An **element** is a complete unit: opening tag, content, closing tag. An **attribute** adds information to a tag, written as `name="value"`. A **class** is an attribute for grouping elements (`class="card"`). An **ID** is an attribute for uniquely identifying one element (`id="contact"`).

**In CSS:** A **selector** specifies which elements to style (`.card`, `#contact`, `p`). A **property** is what you're changing (`color`, `padding`). A **value** is what you're setting it to (`blue`, `20px`). A **rule** combines these: selector, then curly braces containing property-value pairs.

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

Here, `section` and `h1` are tags. The whole `<section>...</section>` is an element. `class="hero"` is an attribute. `.hero` is a CSS selector targeting elements with that class. `background-color` is a property, `#2c3e50` is its value.

---

## Part 1: Getting Set Up

### Exercise 1: Fork and Clone

Let's get your own copy of this project.

1. Click the **Fork** button in the top-right corner of this repository on GitHub
2. This creates your own copy that you can modify freely
3. Either clone it to your computer or use GitHub's web editor (click any file, then the pencil icon)

### Exercise 2: Enable GitHub Pages

Let's make your site live on the internet right away. This way, every change you make becomes visible at a real URL.

1. Go to your forked repository on GitHub
2. Click **Settings** (the gear icon)
3. In the left sidebar, click **Pages**
4. Under "Source," select **Deploy from a branch**
5. Under "Branch," select **main** and **/ (root)**
6. Click **Save**
7. Wait a minute or two, then refresh the page
8. You'll see a URL like `https://yourusername.github.io/repository-name/`

Visit that URL. You should see the template site. Bookmark it—you'll be checking it frequently.

### Exercise 3: Your First Change

Let's make something visibly different so you know everything is working.

Open `index.html` and find the `<title>` element near the top (inside the `<head>` section). It currently says "My Portfolio." Change it to your name or anything else you like. Save the file.

If you're working locally, refresh the browser. If you're using GitHub's web editor, commit your changes and wait a minute for GitHub Pages to rebuild.

Look at your browser tab. The text there should reflect your change. You've just edited HTML and published it to the internet.

**Explore:** What happens if you make the title very long? What if you leave it completely empty?

---

## Part 2: Working Through Your Homepage

Now let's work through `index.html` from top to bottom, making it yours.

### Exercise 4: The Main Heading

Find the `<h1>` element in the hero section. It says "Welcome to My Portfolio." This is the main heading visitors see.

Change it to something that represents you. Save and refresh.

**Explore:** The `<title>` appears in the browser tab; the `<h1>` appears on the page itself. Try making them identical, then try making them different. Which feels right for your site?

### Exercise 5: Your Introduction

Find the paragraph below the `<h1>` (it has `class="hero-text"`). This is your chance to introduce yourself.

Rewrite it in your own voice. Who are you? What are you working on? What interests you? A few sentences is plenty.

**Explore:** Try writing something very formal, then rewrite it casually. Notice how the same information can feel completely different.

### Exercise 6: Emphasis and Importance

HTML has tags for indicating that certain words matter: `<strong>` for important text and `<em>` for emphasized text. Browsers typically display these as bold and italic, but the tags carry meaning beyond just appearance.

In your introduction paragraph, wrap one important word or phrase in `<strong>` tags. Wrap something you want to emphasize in `<em>` tags.

**Explore:** Try `<b>` instead of `<strong>`, and `<i>` instead of `<em>`. Do they look the same? (They often do visually, but they mean different things to screen readers and search engines.) What happens if you nest them: `<strong><em>word</em></strong>`?

### Exercise 7: The About Preview Section

Scroll down to find the section with "A Little About Me." Inside is a card with placeholder text.

Rewrite this placeholder to give visitors a preview of who you are. This section links to your About page, so think of it as a teaser.

### Exercise 8: Adding a Skills Section

Let's add entirely new content. After the about-preview section's closing `</section>` tag, add a new section:

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

Save and refresh. The new section should appear, already styled—it inherits styles from the `.section` and `.card` classes defined in the CSS file.

**Explore:** What happens if you remove `class="section"` from your new section? What styling disappears? Add it back and try removing `class="card"` from the inner div instead.

### Exercise 9: Adding an Image

Let's add an image to your page. Inside your about-preview section (or your new skills section), try adding:

```html
<figure class="profile-image">
    <img src="https://picsum.photos/400/300" alt="A description of what's in the image">
    <figcaption>A caption for the image</figcaption>
</figure>
```

The `picsum.photos` URL gives you a random placeholder image. Later you can replace this with your own image.

The `alt` attribute describes the image for people who can't see it (using screen readers) and appears if the image fails to load. Write something meaningful there.

**Explore:** What happens if you remove the `alt` attribute entirely? Try leaving it empty (`alt=""`) versus removing it completely. What if you use a broken URL for the `src`?

### Exercise 10: Linking to Your About Page

Find the button in the about-preview section (the `<a>` tag with `class="btn"`). It should already link to `about.html`.

Click it. You should navigate to the about page. Look at the navigation bar on both pages—there's already a link back.

**Explore:** Change `href="about.html"` to `href="abut.html"` (misspelled) and click the link. See what a broken link looks like. Fix it afterward.

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

Replace the email address with your own (or leave it as a placeholder for now).

**Explore:** Click the email link. What happens? The `mailto:` protocol tells the browser to open an email application. What if you change it to `mailto:` with nothing after it?

### Exercise 12: Navigation

Find the `<nav>` element in the header. Update the links to point to your sections:

```html
<nav class="main-nav">
    <ul>
        <li><a href="index.html">Home</a></li>
        <li><a href="about.html">About</a></li>
        <li><a href="#skills">Skills</a></li>
        <li><a href="#contact">Contact</a></li>
    </ul>
</nav>
```

The `#skills` and `#contact` links are **anchor links**—they point to elements with those IDs on the same page. When clicked, the browser scrolls to that section.

For this to work, the sections need matching `id` attributes (which you added in exercises 8 and 11).

**Explore:** Click the Skills link. The page should scroll smoothly to that section. Now look in the CSS file for `scroll-behavior: smooth`—that's what creates the smooth scrolling. Try changing it to `scroll-behavior: auto` and clicking the link again.

---

## Part 3: Exploring the Stylesheet

Now let's shift our attention to `styles.css`. Open it in your editor and scroll through. Notice the extensive comments explaining each section.

### Exercise 13: Changing Colors

Near the top of `styles.css`, find the `:root` section. This defines CSS variables (also called custom properties)—values you can reuse throughout the stylesheet.

Find `--primary-color` and `--accent-color`. Change them to colors you like. Save and refresh.

Notice how many elements changed at once. The header, hero section, footer, and buttons all use these variables.

**Explore:** Try setting both colors to the same value. Try very bright colors. Try colors that don't contrast well with white text. What makes a color scheme work or not work?

If you want help choosing colors, try [coolors.co](https://coolors.co) to generate palettes.

### Exercise 14: Backgrounds and Gradients

Find the `.hero` rule in the CSS file. The background currently uses `var(--primary-color)`.

Try changing it to a gradient:
```css
background: linear-gradient(135deg, var(--primary-color), var(--accent-color));
```

**Explore:** Change the angle (135deg) to other values: 0, 45, 90, 180. Watch how the gradient direction shifts. Try `radial-gradient(circle, var(--primary-color), var(--accent-color))` for a completely different effect.

### Exercise 15: The Box Model

Every element on a web page is a rectangular box with four layers: content, padding, border, and margin. Understanding this is fundamental to CSS.

Find the `.card` rule. Notice the `padding` property. Try changing it:
- Set padding to `0` and see how cramped the content becomes
- Set padding to `4rem` and see how much space that creates
- Try `padding: 1rem 3rem` (vertical horizontal) for different values on each axis

**Explore:** Now find a rule with `margin` (try `.container`). Padding is space inside the element; margin is space outside. Try adding `margin: 2rem` to `.card` and notice how cards push away from each other.

### Exercise 16: Borders and Rounded Corners

Still in the `.card` rule, find `border-radius`. This controls how rounded the corners are.

- Try `border-radius: 0` for sharp corners
- Try `border-radius: 20px` for very rounded corners
- Try `border-radius: 50%` (what happens depends on the element's shape)

Add a visible border: `border: 2px solid var(--accent-color);`

**Explore:** Try different border styles: `dashed`, `dotted`, `double`. Try different widths. Try setting different radii for each corner: `border-radius: 0 20px 0 20px;`

### Exercise 17: Text and Typography

Find the `.hero` rule and look at `text-align: center`.

Try changing it to `text-align: left`. Then try `text-align: right`.

**Explore:** Add a long paragraph somewhere and try `text-align: justify`. Resize your browser window and watch how the spacing between words changes. Which alignment is easiest to read for long text?

### Exercise 18: Making Sections Look Different

Right now all sections use the same styling. Let's make your skills section visually distinct.

Add this to your CSS file (near the bottom, before any `@media` rules):

```css
.skills-section {
    background-color: var(--light-gray);
}

.skills-section .card {
    border-left: 4px solid var(--accent-color);
}
```

The selector `.skills-section .card` means "cards that are inside an element with class skills-section." This targets specific cards without affecting cards elsewhere.

**Explore:** Change `.skills-section .card` to just `.card` and watch what else on the page changes. This is CSS specificity at work—more specific selectors override less specific ones.

---

## Part 4: Layout and Positioning

### Exercise 19: The Container

Find the `.container` rule. Notice `max-width: 1200px` and `margin: 0 auto`.

The `max-width` prevents content from stretching too wide on large screens. The `margin: 0 auto` centers the container horizontally (auto margins on left and right split the available space evenly).

**Explore:** Change `max-width` to `600px` (very narrow) or `100%` (full width). Remove `margin: 0 auto` and see what happens. Try `margin-left: auto` without `margin-right: auto`.

### Exercise 20: Sticky Header

Find the `header` rule. Notice `position: sticky` and `top: 0`.

Scroll down your page. The header stays visible at the top. That's what sticky positioning does.

**Explore:** Change `position: sticky` to `position: fixed`. Scroll again. What's different? (Hint: look at the content behind the header.) Change it to `position: relative` (the default) and the header scrolls away with the content. Set it back to `sticky`.

### Exercise 21: The Footer

Find the `footer` rule. Notice `margin-top: auto`.

This works because the `body` is set to `display: flex` with `flex-direction: column`. The auto margin pushes the footer to the bottom even when there's little content.

**Explore:** Remove `margin-top: auto` from the footer. Add just a few words to your page (temporarily delete most content). Where does the footer end up? Add the auto margin back.

---

## Part 5: Interactivity and Polish

### Exercise 22: Hover Effects

Let's make cards respond when you hover over them. Add to your CSS:

```css
.card {
    transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.card:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
}
```

(The transition property might already be there; if so, make sure the hover rule is added.)

Hover over a card. It should lift slightly and its shadow should deepen.

**Explore:** Try `transform: translateY(-20px)` for a more dramatic lift. Try `transform: scale(1.05)` instead—the card grows rather than lifts. Change `0.2s` to `1s` to see the animation in slow motion.

### Exercise 23: Focus States

When someone navigates your site with a keyboard (pressing Tab to move between links), they need to see where they are. That's what focus styles are for.

Find the `a:focus` rule in the CSS. Press Tab repeatedly on your page and watch the outline move between links.

**Explore:** Try removing the `:focus` rule entirely. Navigate with Tab. Can you tell where you are? This is why focus styles matter for accessibility. Add the rule back.

### Exercise 24: Responsive Design

Open your browser's developer tools (usually F12) and find the device toolbar or responsive mode. Resize to a narrow width, like a phone.

Now find the `@media` section at the bottom of the CSS file. Rules inside `@media (max-width: 768px)` only apply when the screen is 768 pixels wide or narrower.

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

**Explore:** Change `max-width: 480px` to `max-width: 800px`. Notice when the styles kick in. Try `min-width` instead of `max-width`—now the rules apply above that size instead of below.

### Exercise 25: Finishing Touches

A few small things to complete your site:

**Favicon:** This is the small icon in the browser tab. Create one at [favicon.io](https://favicon.io) and add to the `<head>` of both HTML files:
```html
<link rel="icon" type="image/x-icon" href="favicon.ico">
```

**About Page:** Open `about.html` and replace all the placeholder content with real information about yourself.

**Footer:** Update the copyright year and name in both HTML files.

**Review:** Look at your site on both desktop and mobile sizes. Click all your links. Is there placeholder text you forgot to replace?

---

## Part 6: Keep Going

You now have a working personal site. Here are paths forward:

**Add more content.** Create new pages for projects, a blog, or anything else. Link to them from your navigation.

**Learn more CSS.** The CONCEPTS.md file in this repository explains some ideas in more depth. When you're ready for more, the resources below offer interactive practice.

**Learn JavaScript.** HTML structures content, CSS styles it, JavaScript makes it interactive. That's a natural next step.

**Keep experimenting.** The best way to learn is to try things, break things, and figure out how to fix them.

---

## Resources

### Interactive Learning

**Flexbox Froggy** — Learn CSS flexbox by helping a frog reach lily pads  
https://flexboxfroggy.com

**Grid Garden** — Learn CSS grid by watering a garden  
https://cssgridgarden.com

**CSS Diner** — Practice CSS selectors by selecting plates and food  
https://flukeout.github.io

**Codepip** — Collection of games for learning CSS  
https://codepip.com

### Reference Documentation

**MDN Web Docs** — Mozilla's comprehensive reference for HTML, CSS, and JavaScript. When you need to look something up, this is the place.  
https://developer.mozilla.org/en-US/docs/Web

**CSS-Tricks** — Practical guides, especially the Complete Guide to Flexbox and Complete Guide to Grid.  
https://css-tricks.com

### Continued Learning

**The Odin Project** — Free, comprehensive curriculum for web development  
https://www.theodinproject.com

**freeCodeCamp** — Interactive curriculum with certifications  
https://www.freecodecamp.org

---

## What You've Practiced

Working through these exercises, you've encountered:

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

More importantly, you've practiced experimenting, breaking things, and figuring out how they work.

---

*This tutorial is provided for educational purposes. Modify and share freely.*
