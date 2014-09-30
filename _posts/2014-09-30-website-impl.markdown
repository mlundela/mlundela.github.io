---
layout: post
title: "How this site was built"
date:   2014-09-30
categories: blog
---

This site was created with the excellent static html generator tool [Jekyll][jekyll], and hosted on Github
thanx to their integration with Jekyll.

In this post I will explain how I decided to organize my Jekyll project, in order to present my portfolio and blog posts,
while keeping the project structure as simple as possible.

Project structure:

    _layouts
      default.html
      post.html
      posts.html
    _posts
      2014-08-26-nnl.markdown
      2014-09-30-website-impl.markdown

    portfolio.html
    index.html

The idea is that *_posts* can have both _portfolio_ and _blog_ posts, and I use the _categories_ tag to separate them.

This is a blog post:

    ---
    layout: post
    title: "How this site was built"
    date:   2014-09-30
    categories: blog
    ---

Now, I like to use the same layout for both the portfolio page and the blog page:

By blog posts (_index.html_):

    ---
    layout: posts
    title: blog
    ---

_portfolio.html_:

    ---
    layout: posts
    title: portfolio
    ---

The layout (__layouts/posts.html_) is where the magic happens:

    ---
    layout: default
    ---
    {% raw %}
    {% for post in site.posts %}
        {% if post.categories contains page.title %}
            <p class="date">{{post.date | date: "%b %-d, %Y" }}</p>
            <h1>{{post.title}}</h1>
            {{post.content}}
        {% endif %}
    {% endfor %}
    {% endraw %}




[jekyll]:    http://www.jekyllrb.com