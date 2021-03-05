---
title: Getting started with Markdown
date: 2021-02-28 10:41:49
tags: 
  - Markdown
categories:
  - Blog
---

This post walks through various elements in Markdown syntax:

<!-- toc -->

## Block Elements

### Paragraphs and Line Breaks

A **paragraph** consists of one or more consecutive lines of text without a line break. In another word, multiple paragraphs are seperated by one or blank lines. Paragraphs should not be indented with spaces or tabs. To insert a line break tag `<br>`, end a line with two or more spaces (commonly referred to as ''trailing whitespaces'') or with a `<br>` HTML tag directly, and then type return. The latter case is useful since it is hard to see the trailing whitespaces in an editor.

### Headers

Markdown offers two styles of headers: **Setext** and **atx**.

Setext-style headers contain two levels, `<h1>` and `<h2>`, which can be rendered by underlying the heading text with equal sign (`=`) and hyphens (`-`), respectively. 


    Level 1 Header
    ==============

    Level 2 Header
    --------------
    
The atx-style headers, on the other hand, are rendered by adding number signs (`#`) in front of the header text. There are six levels, ranging from `<h1>` through `<h6>`, in the atx-style headers.

    # This is an H1 header
    
    ## This is an H2 header
    
    ### This is an H3 header
    
    #### This is an H4 header
    
    ##### This is an H5 header
    
    ###### This is an H6 header

### Blockquotes

### Lists

### Code Blocks

### Horizontal Rules

## Span Elements

### Links

### Emphasis

### Code

### Images

## Miscellaneous

### Backslash Escapes

### Automatic Links
