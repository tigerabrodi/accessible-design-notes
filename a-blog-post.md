# A blog post

# The main element

Every web page should have a `<main>` element. The `<main>` element is used to define the main content of the document.

```html
<main id="main">
  <!-- blog article here -->
</main>
```

# Heading Structure

`<h1>` represents the main heading of the page, `<h2>` represents the subheading, and so on. The heading structure should be logical and follow a hierarchy.

You shouldn't have more than one `<h1>` element on a page. The `<h1>` element should be the main heading of the page and should describe the content of the page.

Screen readers offer shortcut to jump both to main content and to the headings.

```html
<!-- don’t use this -->
<main id="main">
  <div class="meta">
    Published on <time datetime="2017-12-12">12/12/2017</time>
  </div>
  <h1>How To Mark Up Inclusive Blog Articles</h1>
  <!-- article content here -->
</main>
<!-- use this -->
<main id="main">
  <h1>How To Mark Up Inclusive Blog Articles</h1>
  <div class="meta">
    Published on <time datetime="2017-12-12">12/12/2017</time>
  </div>
  <!-- article content here -->
</main>
```

In the first, commented out example, someone navigating
by heading using the generic h key would be unaware of
the publish date because the screen reader would take them
silently past it.

# Subheadings

To create a subheading, use the `<h2>` element. The `<h2>` element should describe the content that follows it.

The hierarchy is important here, as it helps screen reader users understand the structure of the content.

```html
<h1>How To Mark Up Blog Articles</h1>
<!-- introductory content -->
<h3>A quick note on the word ‘semantic’</h3>
<!-- wait! Where’s the second nesting level? -->
```

Some developers prefer using semantically right thing but e.g. h2 styles for h3 element. While this works, you're now styling for both visual and non visual users. Try to avoid this when possible. Collaborate and work closely with designers.

# Subtitles

Do not use a new heading for subtitles. Instead, include it in the same heading with a span.

If you want it as a subtitle and do not feel like it's too important, you can do something like this:

```html
<h1>How To Mark Up Blog Articles</h1>
<p><span class="visually-hidden">Subtitle:</span> In Seven Simple Steps</p>
```

Hide the subtitle visually, but still inform screen readers about the text being a subtitle.

# The <article> Element

The JAWS screen reader (and only the JAWS screen reader) announces “Article” on entering the element and “Article end” on exiting it. Arguably, this is useful information where there are several <article>s on the same page and the user is reading from top to bottom, element by element

Besides that, articles don't provide much in terms of accessibility.

# Progressive Enhancement

A good test is to turn off CSS and see if the page still has the right structure.

# Heading and link text

Screen readers can list all the headings and links on a page. Make sure they make sense out of context. Autonomously, they should give a good idea of what the content is about.

# Video

To make videos accessible, provide captions and transcripts. This is important for users who are deaf or hard of hearing, as well as for users who are in a noisy environment and can't hear the audio.

## player

Make the player accessible. This includes keyboard navigation, focus styles, and controls that are easy to understand.
