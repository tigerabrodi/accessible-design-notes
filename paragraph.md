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
