# A paragraph

Some say a picture paints a thousands words, and it can. But when it comes to the web and inclusive design, words are the most important thing.

Text is the most direct and efficient way to communicate information to users. It's important to make sure that the text is clear, concise, and easy to read.

# Length

The length of a paragraph is important. Long paragraphs can be hard to read, especially on small screens. It's important to break up long paragraphs into smaller, more digestible chunks.

However, too short paragraphs can make it hard on the eyes to read. It's important to strike a balance between long and short paragraphs.

The sweet spot is between 45-75 characters per line. This is the optimal line length for readability.

With CSS, you can achieve this via `ch` units. For example, if you want the line length to be 60 characters, you can do:

```css
p {
  max-width: 60ch;
}
```

`ch` stands for character width. It's a unit that represents the width of the `0` character in the current font.

# Justification

Text alignment is important for readability. Left-aligned text is the most readable, as it's the most natural way to read text in English.

Justified text can be hard to read, especially on small screens. It can create awkward spacing between words and make it hard to follow the flow of the text.

# Line height

Line height is the vertical space between lines of text. It's important to have enough line height to make the text easy to read. Too little line height can make the text feel cramped, while too much line height can make it hard to follow the flow of the text.

The optimal line height is 1.5. This is the default line height in most browsers.

Line height can be set in CSS using the `line-height` property. You should not use a fixed value for line height, as it won't scale well with different font sizes.

# Contrast

Contrast is important for accessibility. It's important to have enough contrast between the text and the background to make the text easy to read. Too strong contrast can make the text harder from some other users to read though.

There is not one inclusive design that's right for every user.

# Inline links

Inline links are common on the web. Links have by default an underline. To improve the underline, you can use background image in combination with a few properties.

```css
p a {
  text-decoration: none;
  text-shadow: 0.05em 0 0 #fff, -0.05em 0 0 #fff, 0 0.05em 0 #fff, 0 -0.05em 0
      #fff, 0.1em 0 0 #fff, -0.1em 0 0 #fff, 0 0.1em 0 #fff, 0 -0.1em 0 #fff;
  background-image: linear-gradient(
    to right,
    currentColor 0%,
    currentColor 100%
  );
  background-repeat: repeat-x;
  background-position: bottom 0.05em center;
  background-size: 100% 0.05em;
}
```

You can tweak the vertical positioning using background-position, and the thickness using background-size to find the most readable solution for the typeface.

# Focus styles

Browsers come with default focus styles, but in some cases, we can strengthen them. For example, for inline links, we can use a background color instead of an outline which can be harder to read when the link is inside a paragraph.

# External links

External links can be identified by an icon. You can put this icon at the top right of the link, usually a square with an arrow pointing to the right.

You can also provide some hidden text for screen readers to tell them it's an external link. Most screen readers support this:

```css
[href^="http"]:not([href*="heydonworks.com"])::after {
  display: inline-block;
  width: 1em;
  height: 1em;
  background-image: url("path/to/external-icon.svg");
  background-repeat: no-repeat;
  background-position: center;
  background-size: 75% auto;
  /* alternative text rules */
  content: "(external link)";
  overflow: hidden;
  white-space: nowrap;
  text-indent: 1em; /* the width of the icon */
}
```

# Content first design

When writing content, the content itself should be easy to read. This means using clear and concise language, breaking up long paragraphs, and using headings and lists to organize the content.
