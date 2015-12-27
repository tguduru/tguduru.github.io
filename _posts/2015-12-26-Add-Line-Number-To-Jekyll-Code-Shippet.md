---
layout: post
title: Add Line Numbers to Jekyll Code Snippet
tags: jekyll
category: misc
---

When adding code snippets to a Jekyll blog it would be nice to add line numbers to the code so that its easy to explain whats going on by referencing the line numbers.

<!--more-->

Fortunately Jekyll provides an easy way to add line number to code highligher by doing the following

{% gist 42db0eae177bb5f517a0 %}

The *linenos* will allows *pygments* which is a code highlighting ruby gem to generate line numbers as shown in the following image.

![](/assets/img/jekyll-line-numbers.png)

This works really well but there is an issue with this one, if somebody wants to copy the code this will also allows to copy the line numbers as well which makes it hard for them to use without manually removing the line numbers.

To prevent selecting line numbers when copying add the following css to the style.css or any other css file you referenced in your default.html.

{% gist 9d6875ba948a2bb1000f %}

Another simple fix for all code highlighting is create a public gist with a file name extension with the respective code extension, for example add name.java for java code, and reference that in Jekyll post using gist tag. As soon as you name the file with proper code extension Github will highlight the syntax for you.

When you reference that gist in a post Jekyll will inject the formatted code from **[Github Gist](https://gist.github.com/)**.

{% gist 88850833e63cd0b3cb68 %}

The above one is simple and easy for github hosted jekyll blogs.