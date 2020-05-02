---
layout: post
title: "Why I Am Buffering Blogs?"
---

# Why I Am Buffering Blogs?

I already have [Heron's Blog](https://blog.heron.me) and [Heron's
Note](https://note.heron.me) to log my software related things, and why I am
creating another one here? I am trying to answer my own question in this post.

## Fast

Existing platforms I've been using such as Medium or Blogspot offer web
interfaces for us to edit posts, which is good but not fast enough. Blogging on
Vim is what I've been looking for. Therefore, I've been looking for a platform
that enables me to focus on typing, and the platform takes care of rest such as
formatting, publishing, etc.

I've tried [SimpleNote](https://simplenote.com/) which is a note-taking app
supporting markdown. Advanced users can use [a vim
plugin](https://github.com/simplenote-vim/simplenote.vim) to compose in Vim.
However, I found that saving a file in vim and commiting that change back to the
applciation server is slow and using a Mac application to view the preview is
somehow too much for me. I also encountered few cases where the vim plugin and
the application server didn't sync well.

I also tried to use some desktop applications like [iA
Writer](https://ia.net/writer) or [Typora](https://typora.io/) to edit my blog
drafts. The rendered page is very pretty and I liked a lot; however, there's
just no vim binding supports, so, it's still not fast enough.

GitHub Pages + Jekyll is my current solution now. I'm typing this blog on Vim,
in a terminal. I'm writing in markdown langauge. I can start composing a post
with `vim _posts/xxx.md`, and publish a post with `git add _posts/xxx.md && git
push`. Super fast, super nice.

## Fun

Typing in Vim and pushing out the changes through a command are just fun. They
are like writing code where we compose something locally, test it, and deploy
it. I feel like I am having the full control of my tools and I know what exact
byte I'm pushing out.

![Vim Screenshot](/assets/2020-04-05-screenshot.png)

## Content-First

It's very easy to get distracted to compose a blog on a fancy website,
especially in the case where you have to deal with layouts. For example, if I'm
writing in HTML directly instead of markdown, I will spend a lot of time
adjusting the margin sizes or the color of hyperlinks. Even worse, I have to
test my post on different sizes of screen. At the end, I spent lots of time on
content unrelated things and I even have to worry whether things will break over
time.

Writing in markdown is simple and makes me focus on the content only. I've been
searching for a platform that will take care of rest and I only have to two
simple thing: "write" and "publish".

## Okay, So Why I Am Buffering Blogs?

With above reasons, I want to blog on this platform, GitHub Pages + Jekyll, but
I don't want to migrate my existing blogs or future blogs to here. The workflow
I planned is to write drafts here which are supposed to be fast-written. Then,
when a post is ready, I publish it to Medium using ["Export to Medium" feature
provided by iA Writer](https://ia.net/writer/support/mac/import-export-share).
