# The Doctype

`<!DOCTYPE html>` tells the browser that the document is an HTML document. It is not case-sensitive.

If you omit the doctype, the browser will render the page in quirks mode. This is a compatibility mode that allows the browser to render the page as if it were an older version of HTML. This can cause issues with the layout and appearance of the page.

# The lang attribute

The doctype tells the browser what kind of document it is, but it doesn't specify the language of the document.

The `lang` attribute of the `html` element can be used to specify the language of the document.

Why is this important?

- Screen readers and other assistive technologies that need to know the language of the content in order to provide the best user experience.
- Search engines use the language of the document to determine how to index and rank the content.
- Third-party tools such as Google Translate API use the language of the document to provide accurate translations.
- Browsers can use the language of the document to provide better spell-checking and other language-specific features.

If you need a quote in a different language, you can use the `lang` attribute on the `blockquote` element to specify the language of the quote.

```html
<blockquote lang="es">
  <p>El que no arriesga no gana.</p>
</blockquote>
```

And in CSS, you can use the `:lang()` pseudo-class to style elements based on the language of the content.

```css
:lang(es) {
  font-family: "Arial";
}
```

# Responsive Design

In accessibility, responsive design is the practice of creating web pages that work well on a variety of devices and screen sizes. This includes desktops, laptops, tablets, and smartphones.

It's important to be aware of the different ways that people interact with your website and to design with those needs in mind.

For example, on the smartphone, you might want to make the text larger and the buttons bigger to make it easier to read and tap. Another idea that comes to mind is making sure that both portrait and landscape orientations are supported.

## Allow pinch-to-zoom

If you've used any modern frameworks, you've probably seen this tag before in the `<head>` of your HTML document:

```html
<meta
  name="viewport"
  content="width=device-width,
initial-scale=1.0"
/>
```

This tag tells the browser to set the width of the viewport to the width of the device and to set the initial zoom level to 1.0. This allows users to zoom in and out of the page by pinching and zooming.

[Adrian Roselli has a great article](https://adrianroselli.com/2015/10/dont-disable-zoom.html) on why you should allow pinch-to-zoom on your website, some points:

- The text may be too small for the user to read.
- The user may want to see more detail in an image.
- Selecting words to copy/paste may be easier for users
  when the text is larger
  The user wants to crop animated elements out of the
  view to reduce distraction.
- The developer did a poor job of responsive design,
  and the user needs to zoom just to use the page
  (this happens!).
- There is a browser bug or quirk (still a bug) that causes
  the default zoom level to be odd.
- It can be confounding for users when a pinch/spread
  gesture is interpreted as something else.

# Font size

Browsers tend to default to a font size of 16px. This is a good starting point, but it's important to remember that not everyone has perfect vision.

People can adjust the font size in their browser settings, e.g., from 100% to 125%, 150%, etc. This is a common practice for people with low vision.

It's common in the root of the CSS file to set the font size to 62.5% (10px) to make it easier to calculate the font size in `rem` units.

```css
html {
  font-size: 62.5%;
}
```

This is bad. We should leave the font size at the default of 16px and use `rem` units for font sizes.

1rem is equal to the font size of the root element (16px by default). This makes it easier to scale the font size up or down by changing the font size of the root element.

A pattern I use is to use `calc` to set the font size.

For example, if I want the font size to be 18px, I would do:

```css
p {
  font-size: calc(1rem + 18px / 16);
}
```

This way, I know the font size I'm setting but calculate it based on the root font size.

To make sure fonts scale well, you should use relative units like `rem` or `em` for font size, padding, and margin.

# Progressive Enhancement

Progressive enhancement is a word thrown around a lot in web development. It's the idea that you start with a basic version of your website that works for everyone and then add enhancements for users with more capable devices.

The idea is that your website is functional for everyone. It should work, even if the user has JavaScript disabled or is using an older browser.

This makes the website accessible to a wider audience and ensures that everyone can access the content. It's also good for the business because you'll make money from users who might not have been able to access the content otherwise.

A progressively enhanced site should load scripts at the end of the body tag just before the closing `</body>` tag. This ensures that the content is loaded first and that the user can start interacting with the page right away.

# The <title> Element

The `<title>` element is used to define the title of the document. It is displayed in the browser tab and is used by search engines to determine the content of the page.

It's also the accessible name for the page. The `<title>` is read by screen readers when the page is loaded, and it's used by the browser to provide a name for the page when it's bookmarked.

# The <main> Element

The `<main>` element is used to define the main content of the document. It should contain the primary content of the page, such as articles, blog posts, or product listings.

Some screen readers have a shortcut to jump directly to the main content of the page, so it's important to use the `<main>` element to define the main content of the page.

# Skip Links

Skip links are hidden links that allow users to skip over repetitive content and jump directly to the main content of the page. They are useful for users who navigate the web using a keyboard or screen reader.

It's important to mention that skip links aren't just for screen reader users, but for anyone who uses the keyboard to navigate the web. They can be helpful for users who have motor impairments or other disabilities that make it difficult to use a mouse.

They should be hidden and when focused, they should become visible.

Let's look at some CSS:

```css
[href="”#main”"] {
  position: absolute;
  top: 0;
  right: 100%; /* moves off screen */
}

[href="”#main”"]:focus {
  right: auto;
}
```

When the user first lands on the page, the focus is on the site itself. After the user presses the tab key, the focus will move to the skip link. When the user presses enter, the focus will move to the main content of the page.

# Putting it all together

```html
<!DOCTYPE html>
<!-- the main language of the page declared -->
<html lang="en">
<head>
 <meta charset="utf-8">
 <!-- a viewport declaration which does not disable zooming -->
 <meta name="viewport" content="width=device-width, initialscale=1.0">
 <!-- a non-blocking base64-encoded font resource -->
 <link rel="stylesheet" href="fonts.css" media="none"
 onload="if(media!='all')media='all'">
 <noscript><link rel="stylesheet" href="fonts.css"></noscript>
 <!-- a non-blocking stylesheet -->
 <link rel="stylesheet" href="main.css" media="none"
 onload="if(media!='all')media='all'">
 <noscript><link rel="stylesheet" href="main.css"></noscript>
 <!-- a descriptive label for the page -->
 <title>Inclusive Design Template | Heydon's Site</title>
</head>
<body>
 <!-- a handy skip link for keyboard users -->
 <a href="#main">skip to main content</a>
 <!-- logo / page navigation etc. goes here -->
 <main id="main">
 <!-- unique content of page goes here -->
 </main>
 <!-- a non-blocking javascript resource -->
 <script src="scripts.js"></script>
</body
```
