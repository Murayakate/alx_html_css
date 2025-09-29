# My SmileSchool Website Development Journey

As I developed this website for SmileSchool, I documented my process and learning experience. This README shares my journey of building each component and understanding how HTML and CSS work together.

## 🎓 My Understanding of the Basics

### The Building Blocks I Used

1. **HTML Elements**: I learned that these are like building blocks, each serving a specific purpose:
   - `<div>`: I use these as containers to group related elements
   - `<p>`: For paragraphs of text
   - `<h1>`, `<h2>`, `<h3>`: For headings of different importance
   - `<img>`: To display all my images
   - `<button>`: For interactive buttons

2. **CSS Properties**: I discovered these are like different tools:
   - Colors: Using `color` and `background-color` to paint elements
   - Measurements: Using `width`, `height`, `padding`, and `margin` to size things
   - Layouts: Using `display`, `flex`, and `grid` to arrange elements

## 📸 How I Built Each Section

### 1. Creating My Header

For my website's header, I wanted a clean, professional look with the logo on the left and navigation menu on the right. Here's how I implemented it:

![Logo](./css_photos/logo.png)

First, I structured my HTML like this:
```html
<header>
    <nav>
        <img src="./css_photos/logo.png" alt="logo">
        <ul>
            <li><a href="#">COURSE</a></li>
            <li><a href="#">PRICING</a></li>
            <li><a href="#">LOGIN</a></li>
        </ul>
    </nav>
</header>
```

Then, I styled it using CSS. Here's what each part does:
```css
header {
    position: absolute;    /* I used this to make it float over the hero section */
    width: 100%;          /* Makes it span the full width of the page */
    top: 0;              /* Positions it at the top */
    padding: 35px 0;     /* Adds space above and below */
}

/* I used flexbox for the navigation layout */
nav {
    display: flex;       /* This makes my logo and menu sit side by side */
    justify-content: space-between;  /* Pushes logo to left, menu to right */
    max-width: 1440px;   /* Keeps content from getting too wide */
    margin: 0 auto;      /* Centers everything */
}
```

### 2. My Hero Section Implementation

The hero section was challenging because I needed to overlay text on a background image. Here's my solution:

![Hero Section](./css_photos/Object.png)

```css
/* I created a dark overlay on my background image using gradients */
main > section:first-of-type {
    background-image: linear-gradient(
        to bottom,
        rgba(7, 22, 41, 0.8),  /* Darker at top */
        rgba(7, 22, 41, 0.9)   /* Even darker at bottom */
    ),
    url('./css_photos/Object.png');
    
    /* These settings ensure my background image covers properly */
    background-size: cover;
    background-position: center;
    min-height: 100vh;   /* Makes it full screen height */
}
```

### 3. How I Styled The "Learn from the Pros" Section

This section needed circular profile images and a clean layout. Here's my approach:

![Instructor](./css_photos/1.png)

```css
/* My technique for circular images */
.pro-card img {
    width: 150px;
    height: 150px;
    border-radius: 50%;    /* This creates the circular shape */
    object-fit: cover;     /* Ensures images fill the circle nicely */
    margin-bottom: 15px;   /* Adds space below each image */
}

/* I used this layout for the cards */
.pros-grid {
    display: flex;
    justify-content: center;
    gap: 60px;             /* Adds equal spacing between cards */
    flex-wrap: wrap;       /* Allows cards to wrap on smaller screens */
}
```

### 4. My Video Tutorial Cards

For the video section, I wanted each card to have a hover effect and consistent spacing. Here's how I did it:

```css
.video-card {
    /* I added subtle shadows and padding */
    padding: 20px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    
    /* I made hover effects smooth using transitions */
    transition: transform 0.3s;
}

/* When someone hovers over my cards */
.video-card:hover {
    transform: translateY(-5px);  /* Card slightly floats up */
}
```

## 🎨 My Color Choices

I carefully selected these colors for my design:

```css
:root {
    /* My main brand colors */
    --purple: #C271FF;     /* Used for highlights and buttons */
    --dark-blue: #071629;  /* Used for dark backgrounds */
    
    /* I use transparent colors for overlay effects */
    --transparent-white: rgba(255, 255, 255, 0.9);
}
```

## 💻 My Development Tips

Through building this project, I learned some helpful practices:

1. **Organization**: I keep my CSS organized by sections, making it easier to find and modify styles

2. **Reusable Classes**: I created reusable classes for common styles:
   ```css
   .purple-text { color: var(--purple); }
   .centered { text-align: center; }
   ```

3. **Responsive Design**: I made my website work on different screen sizes using:
   ```css
   @media (max-width: 768px) {
       /* My adjustments for smaller screens */
   }
   ```

## 💡 Lessons I Learned

1. **Flexbox is Powerful**: I used it throughout my project for layouts
2. **CSS Variables Help**: They make it easy to maintain consistent colors and spacing
3. **Mobile-First Matters**: I started with mobile styles and enhanced for larger screens

## 📚 How to Use My Code

If you want to work with my code:

1. The structure is in `index.html`
2. All styling is in `style.css`
3. Images are in the `css_photos` folder

To make changes:
1. Find the section you want to change in `index.html`
2. Look for its corresponding styles in `style.css`
3. Modify the values to see how they affect the design

## 🚀 Setting Up Locally

To view my project:

```powershell
# Run from the css_advanced folder
python -m http.server 8000
```

Then open http://localhost:8000 in your browser.

I hope my notes help others learning web development! Feel free to explore the code and learn from my approach. 😊
![Logo](./css_photos/logo.png)

```html
<header>
    <nav>
        <img src="./css_photos/logo.png" alt="logo">
        <ul>
            <li><a href="#">COURSE</a></li>
            <li><a href="#">PRICING</a></li>
            <li><a href="#">LOGIN</a></li>
        </ul>
    </nav>
</header>
```

How we styled it in CSS:
```css
header {
    position: absolute;    /* This makes it float on top of other content */
    width: 100%;          /* Takes full width of screen */
    top: 0;              /* Sticks to the top */
    padding: 35px 0;     /* Space above and below */
}

/* Style the navigation menu */
nav {
    display: flex;       /* Makes items go side by side */
    justify-content: space-between;  /* Pushes logo and menu apart */
}
```

### 2. Hero Section (Big Welcome Area)
![Hero Section](./css_photos/Object.png)

What each part means:
```css
/* This makes the dark overlay on the background image */
background-image: linear-gradient(
    to bottom,
    rgba(7, 22, 41, 0.8),  /* Dark blue that's 80% transparent */
    rgba(7, 22, 41, 0.9)   /* Slightly less transparent at bottom */
),
url('./css_photos/Object.png');
```

### 3. The "Learn from the Pros" Section

How we make circular images:
![Instructor](./css_photos/1.png)

```css
/* This turns square images into circles */
img {
    width: 150px;
    height: 150px;
    border-radius: 50%;    /* This makes it circular */
    object-fit: cover;     /* Makes sure image fills circle nicely */
}
```

### 4. Video Tutorials Section

How we create the video cards:
```css
.video-card {
    /* This creates space around each card */
    padding: 20px;
    
    /* This adds a subtle shadow */
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    
    /* Smooth hover effect */
    transition: transform 0.3s;
}

/* When someone hovers over the card */
.video-card:hover {
    transform: translateY(-5px);  /* Card slightly moves up */
}
```

### 5. Special Effects We Use

1. **Hover Effects** (when you move your mouse over something):
```css
/* Links become slightly transparent when hovered */
a:hover {
    opacity: 0.8;
}

/* Buttons get darker when hovered */
button:hover {
    background-color: #a447ff;
}
```

2. **Spacing Magic** (Margin vs Padding):
```css
.example {
    margin: 20px;   /* Space OUTSIDE the element */
    padding: 20px;  /* Space INSIDE the element */
}
```

### 6. Colors We Use

```css
:root {
    /* Main colors */
    --purple: #C271FF;     /* Our brand purple */
    --dark-blue: #071629;  /* Background color */
    
    /* Transparent colors */
    --transparent-white: rgba(255, 255, 255, 0.9);
}
```

### 7. Making Things Line Up (Flexbox)

Flexbox is like a magic way to arrange things. Here's how we use it:

```css
/* Make things go side by side */
.footer-row {
    display: flex;
    
    /* Different ways to arrange things */
    justify-content: space-between;  /* Spreads things out */
    /* OR */
    justify-content: center;         /* Centers things */
    /* OR */
    justify-content: flex-start;     /* Puts things at start */
    
    /* Line things up vertically */
    align-items: center;
}
```

## 💡 Special Words Explained

- **padding**: Space inside a box
- **margin**: Space outside a box
- **rgba**: A way to make colors transparent (like rgba(255, 255, 255, 0.5) is half-transparent white)
- **border-radius**: Makes corners round
- **display: flex**: Makes things line up nicely
- **position: absolute**: Makes something float over other things
- **transition**: Makes changes smooth instead of sudden

## 🎨 Want to Change Colors?

In `style.css`, find these colors:
```css
/* Main purple color */
.purple {
    color: #C271FF;
}

/* Dark background */
.dark-bg {
    background-color: #071629;
}
```

## 📖 Want to Change Text?

1. Find the text in `index.html`
2. Change it there
3. The CSS will automatically style it

## 📷 Want to Change Images?

1. Put your new image in the `css_photos` folder
2. In `index.html`, find the `<img>` tag you want to change
3. Change the `src="..."` to your new image name

## 💻 Try It Yourself!

1. Open `index.html` and `style.css` in VS Code
2. Make a small change (like a color or text)
3. Save the file
4. Refresh your web browser
5. See what changed!

Remember: It's okay to experiment! If something breaks, you can always undo your changes.

Need more help? Want to understand something better? Just ask! 😊

## How HTML and CSS Work Together 🤝

Think of HTML as building blocks and CSS as the paint and decoration:
- HTML is like the skeleton of our website (structure)
- CSS is like the skin and clothes (style and appearance)

### How We Connect HTML and CSS:

In our `index.html`, we have this line that connects our CSS file:
```html
<link rel="stylesheet" href="/css_advanced/style.css">
```
This is like telling the HTML: "Hey, use these style rules from style.css!"

## Understanding Our HTML Structure 🏗️

Our website is divided into main parts (like rooms in a house):

1. **Header** (`<header>`)
   - Contains the logo and navigation menu
   - Lives at the top of the page

2. **Main Content** (`<main>`)
   - Different sections like:
     - Hero section (big welcome area)
     - Tutorials section
     - Testimonial section
     - FAQ section

3. **Footer** (`<footer>`)
   - The bottom part with logo and social links

## How We Style Things with CSS 🎨

Let's look at some examples of how we style different parts:

### 1. Basic Styling Rules:
```css
/* This means: "Style EVERY element" */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* This means: "Style the whole page" */
body {
    font-family: 'Source Sans Pro', sans-serif;
    color: white;
    background-color: #071629;
}
```

### 2. Styling Specific Sections:
```css
/* When you see a dot (.), it means we're styling a class */
.tutorials {
    background: white;
    padding: 80px 0;
    text-align: center;
}

/* When you see > it means "inside of" */
.video-card h3 {
    font-size: 16px;
    font-weight: 700;
}
```

## Cool CSS Features We Use 🌟

### 1. Flexbox Layout
We use this to arrange things in rows or columns:
```css
.footer-row {
    display: flex;                /* Makes items flex */
    justify-content: space-between; /* Spreads items apart */
    align-items: center;          /* Centers items vertically */
}
```

### 2. Making Things Pretty
```css
/* Round corners on buttons */
button {
    border-radius: 25px;
}

/* Hover effects when you move your mouse over something */
.social-links a:hover {
    opacity: 0.8; /* Makes it slightly transparent */
}
```

### 3. Colors and Transparency
```css
/* Solid colors use hex codes (#XXXXXX) */
.purple {
    color: #C271FF;
}

/* Semi-transparent colors use rgba */
.text {
    color: rgba(255, 255, 255, 0.9); /* White at 90% opacity */
}
```

## Common Patterns We Use 🔄

1. **Centering Content**:
```css
.section {
    max-width: 1440px;     /* Maximum width */
    margin: 0 auto;        /* Centers horizontally */
    padding: 0 170px;      /* Space on sides */
}
```

2. **Making Images Circular**:
```css
.profile-image {
    border-radius: 50%;    /* Makes square images circular */
    width: 150px;
    height: 150px;
    object-fit: cover;     /* Prevents image stretching */
}
```

## Tips for Understanding the Code 💡

1. **Classes in HTML**:
   - When you see `class="something"` in HTML, look for `.something` in CSS
   - Example: `<div class="footer">` matches `.footer { }` in CSS

2. **Nested Elements**:
   - If something is inside another thing, we can style it specifically:
   ```css
   .video-card h3 { }  /* Styles h3 tags inside video-card class */
   ```

3. **Common Properties**:
   - `margin`: Space outside an element
   - `padding`: Space inside an element
   - `color`: Text color
   - `background`: Background color or image
   - `display: flex`: Makes elements arrange in a row/column

## Want to Try Changes? 🔧

1. Find the element you want to change in `index.html`
2. Look for its class name
3. Find that class in `style.css`
4. Try changing values like colors, sizes, or spacing
5. Refresh your browser to see changes!

## Visual Examples 📸

### Our Hero Background:
![Hero background](./css_photos/Object.png)
*This is the big background image we use at the top of our page*

### Profile Pictures Style:
![Instructor example](./css_photos/1.png)
*See how we make square images circular using border-radius*

### Our Logo:
![Logo](./css_photos/logo.png)
*This logo appears in both header and footer*

## Quick Setup Tips 🚀

1. Open these files in VS Code:
   - `index.html` (the structure)
   - `style.css` (the styling)

2. View in your browser:
   - Use Chrome, Firefox, or Edge
   - If images don't show up, check that your `css_photos` folder is in the right place

3. For live preview:
```powershell
# Run this in PowerShell from the css_advanced folder
python -m http.server 8000
```
Then visit http://localhost:8000 in your browser

Remember: CSS is like giving instructions to paint a picture. Be specific about what you want to style and how you want it to look!

Need more help? Just ask! Sometimes the best way to learn is by experimenting with the code. 😊