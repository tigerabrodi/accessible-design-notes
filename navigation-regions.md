# The navigation landmark

Areas of web pages are referred to as regions, blocks or modules.

For navigation regions, the `nav` element is used. This element is used to define a block of navigation links.

- You can have more than one `nav` element on a page.
- The content inside navigation landmarks should be consistent between pages.

# Site-Wide Navigation

For the purposes of accessible UX, progressive enhancement and backwards compatibility, landmark regions should contain an unordered list of links. For site navigation, these links would pertain to the different pages available in your site or application.

```html
<nav>
  <ul>
    <li><a href="/">home</a></li>
    <li><a href="/about">about</a></li>
    <li><a href="/products">products</a></li>
    <li><a href="/contact">contact us</a></li>
    <li><a href="/login">login</a></li>
  </ul>
</nav>
```

Screen readers often provide a list of landmarks on a page. This allows users to quickly navigate to different sections of the page. By using the `nav` element, you are helping screen reader users to quickly find the navigation links on your page.

# Positioning

As humans we're used to seeing navigation at the top of a page. This is where users will expect to find it. This is the most inclusive approach. Users shouldn't have to tab through the entire page to find the navigation.

# Active state of current page

The nav link for the current page shouldn't just be styled with hue, but also with a different text color, background color, or underline. This helps users to know which page they are currently on.

# Current page link

You can tell the user using screen reader which page they're currently on:

```html
<nav>
  <ul>
    <li><a href="/">home</a></li>
    <li>
      <a href="/about"
        ><span class="visuallyhidden">Current page</span> about</a
      >
    </li>
    <li><a href="/products">products</a></li>
    <li><a href="/contact">contact us</a></li>
    <li><a href="/login">login</a></li>
  </ul>
</nav>
```
