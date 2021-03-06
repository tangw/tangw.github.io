---
title: Getting started with Blogging
date: 2021-03-05 15:58:56
tags:
  - Markdown
categories:
  - Blog
---

*Acknowledgement*: The following text heavily depends on the article posted in [this link](https://daringfireball.net/projects/markdown/) and is presented here for my self-study.

This post walks through various elements in Markdown syntax:

<!-- toc -->

## Block Elements

### Paragraphs and Line Breaks

A **paragraph** consists of one or more consecutive lines of text without a line break. Multiple paragraphs are seperated by one or blank lines. Paragraphs should not be indented with spaces or tabs. A **blank line** is a line containing nothing or abitrary number of **spaces**/**tabs** only. To insert a line break tag `<br>`, end a line with two or more spaces (commonly referred to as ''trailing whitespaces'') or with a `<br>` tag directly. 

### Headers

Markdown offers two styles of headers: **Setext** and **atx**.

Setext-style headers contain two levels, `<h1>` and `<h2>`, which can be rendered by underlying the heading text with arbitary number of equal signs (`=`) and hyphens (`-`), respectively. For example,


    Level 1 Header
    ==============

    Level 2 Header
    --------------
    
The atx-style headers are rendered by adding hash signs (`#`) in front of the heading text. There are six levels in the atx-style headers ranging from `<h1>` through `<h6>`. For example,

    # This is an H1 header
    
    ## This is an H2 header
    
    ### This is an H3 header
    
    #### This is an H4 header
    
    ##### This is an H5 header
    
    ###### This is an H6 header

### Blockquotes

Markdown uses email-style `>` characters for blockquoting, rendered as tag `<blockquote>`. It looks best if you hard wrap the text and put a `>` in front of every line. For example,


    > This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
    > consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
    > Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
    > 
    > Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
    > id sem consectetuer libero luctus adipiscing.

Alternatively, it is also allowable to only put the `>` before the first line of a hard-wrapped paragraph. For example,

    > This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
    consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
    Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
    
    > Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
    id sem consectetuer libero luctus adipiscing.

Blockquotes can be nested (i.e. a blockquote-in-a-blockquote) by adding additional levels of `>`. For example,

    > This is the first level of quoting.
    >
    > > is nested blockquote.
    >
    > Back to the first level.

Blockquotes can contain other Markdown elements, including headers, lists and code bocks. For example,

    > ## This is a header.
    > 
    > 1.   This is the first list item.
    > 2.   This is the second list item.
    > 
    > Here's some example code:
    > 
    >     return shell_exec("echo $input | $markdown_script");

### Lists

Markdown supports unordered (bulleted) ordered (numbered) lists.

Unordered lists, rendered as tag `<ul>`, use asterisks (`*`), pluses (`+`), and hyphens (`-`), interchangablly as list markers. For example,

    * Red
    * Green
    * Blue
    
is equivalent to

    + Red
    + Green
    + Blue

and

    - Red
    - Green
    - Blue

Ordered lists, rendered as tag `<ol>`, use numbers followed by a period. For example,

    1. Bird
    2. McHale
    3. Parish

It is important to note that the actual numbers you use to mark the list have no effect on the HTML output that Markdown produces. For example, the list is written down in Markdown as below:

    1. Bird
    3. McHale
    2. Parish
    
the rendered HTML output will be

1. Bird
3. McHale
2. Parish

Please note that Markdown starts ordered lists at an arbitrary number. With the lazy list numbering as shown above, one should still start the list with the number 1.

List markers typically start at the left margin, but may be indented by up to three spaces. List markers must be followed by one or more spaces or tab.

### Code Blocks

Pre-formatted code blocks are used for writing about programming or markup source code. Rather than forming normal paragraphs, the lines of a code block are interpreted literally. Markdown wraps a code block in both `<pre>` and `<code>` tags.

To produce a code block in Markdown, simply indent every line of the block by at least four spaces or one tab. For example, given the input below

    This is a normal paragraph:
    
        This is a code block.
        
Markdown will produce

    <p>This is a normal paragraph:</p>
    
    <pre><code>This is a code block.</code></pre>
    
One leve of indentation is removed from each line of a code block. For example,

    Here is an example of AppleScript:
    
        tell application "Foo"
            beep
        end tell

will turn into

    <p>Here is an example of AppleScript:</p>
    
    <pre><code>tell application "Foo"
        beep
    end tell</code></pre>

Within a code block, ampersands (`&`) and angle brackets (`<` and `>`) will be automatically converted into HTML entities.

Pre-formatted code blocks are used for writing about programming or markup source code. Rather than forming normal paragraphs, the lines of a code block are interpreted literally. Markdown wraps a code block in both <pre> and <code> tags.

### Horizontal Rules

A horizontal rule tag, `<hr/>`, is rendered by placing three or more hyphens (`-`), asterisks (`*`), or underscores (`_`) on a line by themselves. Spaces are allowed between the hyphens, asterisks, or underscores. For example, each of the following lines will produce a horizontal rule:

    ***
    * * *
    -----
    ____
    
---

## Span Elements

### Links

Markdown supports two style of links: inline and reference.

In both styles, the link text is delimited by `[`square brackets`]`.

To create an inline link, use a set of regular parentheses immediately after the link text’s closing square bracket. Inside the parentheses, put the URL where you want the link to point, along with an optional title for the link, surrounded in quotes. For example,

    This is [an example](http://example.com/ "title") inline link.
    
    [This link](http://example.net/) has no title attribute.

will produce

    <p>This is <a href="http://example.com/" title="title">
    an example</a> inline link.</p>
    
    <p><a href="http://example.net/">This link</a> has no title
    attribute.</p>

Relative paths can be used if a local resource is referred on the same server.

    See my [About](/about/) page for details.
    
Reference-style links use a second set of square brackets, inside which you place a label of your choice to identify the link. For example,

    This is [an example][id] reference-style link.
    
You can optionally use a space to separate the sets of brackets. For example,

    This is [an example] [id] reference-style link.

Then, anywhere in the document, the corresponding link label can be given on a line as below

    [id]: http://example.com/ "optional title here"

In summary,

* Square brackets containing the link identifier (optionally idented from the left margin using up to three spaces);
* followed by a colon;
* followed by one or more spaces (or tabs);
* followed by the URL for the link;
* optionally followed by a title attribute for the link, enclosed in double or single quotes, or enclosed in parentheses.

### Emphasis

Markdown treats asterisks (`*`) and underscores (`_`) as indicators of emphasis. Text wrapped with one `*` or `_` will be wrapped with an `<em>` tag; double `*`'s or `_`'s will be wrapped with an `<strong>` tag. For example,

    *single asterisks*
    
    _single underscores_
    
    **double asterisks**
    
    __double underscores__
    
will be rendered as

    <em>single asterisks</em>
    
    <em>single asterisks</em>
    
    <strong>double asterisks</strong>
    
    <strong>double underscores</strong>

Emphasis can be used in the middle of a word as below

    abso\*frigging\*lutely

Asterisks or underscores surrounded with spaces will be treated literally. To produce a literal askterisk or underscore at any position, one can use backslash to escape it. Please see details below.

### Code

To indicate a span of code, wrap it with backtick quotes (`` ` ``). Unlike a pre-formatted code block, a code span indicates code within a normal paragraph. For example,

    Use the `printf()` function.

will produce

    <p>Use the <code>printf()</code> function.</p>

To include a literal backtick character within a code span, one can use multiple backticks as the opening and closing delimiters. For example, the following

    ``There is a literal backtick (`) here.``

will be rendered as

    <p><code>There is a literal backtick (`) here.</code></p>

With a code span, ampersands and angle brackets are encoded as HTML entities automatically, which makes it easy to include example HTML tags. 

### Images

Markdown allows for two styles of image syntax: *inline* and *reference*.

Inline image syntax looks like this:

    ![alt text](/path/to/img.jpg)
    
    ![alt text)(/path/to/img.jpg "optional title")

That is:

* An exclamation point: `!`;
* followed by a set of square brackets, containing the alt attribute text for the image;
* followed by a set of parentheses, containing the URL or path to the image, and an optional title attribute enclposed in double or single quotes.

Reference-style image syntax looks like this:

    ![alt text][id]

where ``id'' is the name of a defined image reference. Image references are defined using syntax identical to link references:

    [id]: url/to/image "optional title attribute"

---

## Miscellaneous

### Backslash Escapes

Markdown uses backslash escapes to generate literal characters that would otherwise have special meaning in Markdown's syntax. For example, a word surrounded with literal asterisks is *emphasized*, rendered with a `<em>` tag. If the literal asterisks are expected otherwise, a backslash shall be put before the asterisks. For example,

    \*literal asterisks\*
    
Markdown provides backslash escapes for the following characters:

    \   blakslash
    `   backtick
    *   asterisk
    _   underscore
    {}  curely braces
    []  square brackets
    ()  parentheses
    #   hash mark
    +   plus sign
    -   minus sign (hyphen)
    .   dot
    !   exclamation point

### Automatic Links

Markdown supports a shortcut style for creating ``automatic'' links for URLs and email addresses: simply surround the URL or email address with a pair of angle brackets. Then the actual text of a URL or email address will become a clickable link. For example,

    <http://example.com/>
    
will be rendered as

    <a>href="http://example.com/">http://example.com/</a>
    
Automatic links for email addresses work similarly except that Markdown will also perform a bit of randomized encoding to help obscure the email address from addres-havasting spambots. For example, the following email address

    <address@example.com>

will be rendered as something by Markdown below

    <a href="mailto:&#x61;&#x64;&#x64;&#114;&#x65;&#x73;&#x73;&#x40;&#101;&#120;&#x61;
    &#109;&#112;&#x6c;&#101;&#46;&#x63;&#x6f;&#x6d;">&#x61;&#x64;&#x64;&#114;&#x65;&#x73;
    &#x73;&#x40;&#101;&#120;&#x61;&#109;&#112;&#x6c;&#101;&#46;&#x63;&#x6f;&#x6d;</a>
    
Please note that the above entity-encoding trick will not prevent all address-harvesting bots.

