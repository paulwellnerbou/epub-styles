epub-styles
===========

This project contains sample HTML and CSS to beautify Ebooks in the epub format (epubs) and make code samples readable in all epub reader devices.

Code in epubs
-------------

There are several ways to embed code in epubs. Unfortunately monospace fonts does not seem to be tested very well by the render software in epub reader devices like the Sony Reader, Tolino or similar. In addition to that, most publishers does not seem to test their books on those reader devices neither. That often leads to almost unreadable code in technical ebooks.

### Size of monospace fonts

The default monospace font of the Sony Reader is quite huge. And if the font size is shrinked, the monospace font used in the sony reader makes it very hard to read anything. So I generally recommend to embed an own monospace font with a decent font size (in percent, not pixel, so that it scales if the reader changes font size).

The font size for monospace code in epubs published by O'Reilly is even larger. On small screen, as e-readers use to have, it is quite difficult to read source code which is a bit longer than a few lines.

Monospace font embedded in normal paragraphs should ideally use a font and size so that the height is the same as the normal font used in the paragraph itself. This improves readability and design aspect.

### Word wrap in monospace font blocks

Most epub render engines will render &lt;code&gt; and &lt;pre&gt; tags as a browser would render them. In principle, thats ok, and it works perfectly for computer screens, tablets and smartphones. But on screens where you are not able to scroll, like ebook reader use to have, a part of the text will disappear behind the right margin. There are two ways to solve this problem:

1. Wrap text in &lt;code&gt; and &lt;pre&gt; tags via CSS:

  code, pre {
    white-space: pre-wrap;
  }

2. Don't use &lt;code&gt; and &lt;pre&gt; tags, use a css class instead:

  .code {
    font-family: monospace;
    white-space: pre-wrap;
  }

<code>pre-wrap</code> is a CSS3 property and may not be supported by all epub reader software. See [http://css-tricks.com/snippets/css/make-pre-text-wrap/].
