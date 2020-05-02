---
layout: post
title: "Setup A Minimal Blog"
---

# Setup A Minimal Blog (Jekyll + GitHub Pages)

This post guides you to setup a blog, write a post with markdown, and publish it online. We
use [Jekyll](https://jekyllrb.com/) blogging tool and deploy on [GitHub Pages](https://pages.github.com/).

## Steps

__Step 1__: Create a github repo with name `<your_github_username>.github.io`.

__Step 2__: Add `_config.yml` file as below.

```yml
title: <YOUR_BLOG_NAME>
description: >-
  <YOUR_BLOG_DESCRIPTION>
```

__Step 3__: Add `index.html` file as below.

{% raw  %}
```html
---
layout: default
---
PUT_SOME_WELCOME_MESSAGE_HERE
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a> 
    </li>
  {% endfor %}
</ul>
```
{% endraw  %}

__Step 4__: Add a post under `_posts` folder with a name in this format:
`2020-04-05-MY-POST-NAME.md`. 

```md
---
layout: post
title: "MY POST TITLE"
---
I can write blog here... with markdown!
```

__Step 5__: Push the changes to GitHub.

```bash
# You might want to `git init` and `git remote add origin` first.
$ git add .
$ git commit -m "Start my blogging life."
$ git push
```

Done. Now, your minimal blog is ready at
`http://<your_github_username>.github.io`. It should be similar to this:

![Mini Blog Demo](/assets/2020-04-05-mini-blog.png)

Next, I describe some additional things you might want to do. They are optional.

## Additional: Run Locally

If you want to see the changes without affectings the one deployed online, you
can run the blog locally first. To keep you away from a series of installation
issues, I provide the following solution with docker.

__Step 1__: Install and run [Docker](https://docs.docker.com/get-docker/) on your
machine.

__Step 2__: Add `Gemfile` as below:

```bash
source "https://rubygems.org"
gem "github-pages", group: :jekyll_plugins
```

__Step 3__: Run the following command to start your blog locally.

```bash
$ export JEKYLL_VERSION=3.8
docker run --rm -p 4000:4000 \
  --volume="$PWD:/srv/jekyll" \
  -it jekyll/jekyll:$JEKYLL_VERSION \
  jekyll serve
```

__Step 4__: Visit your blog at `http://0.0.0.0:4000`.

Note the you don't have to re-run the command in Step 3 if you add or modify a
blog post. But, you need to re-run if you modify the `_config.xml` file.

## Additional: Display Date of Posts

If you want to display the date of the posts on your home page. In `index.html`
file, change

{% raw  %}
```html
<a href="{{ post.url }}">{{ post.title }}</a>
```
{% endraw %}

to

{% raw  %}
```html
{{ post.date | date: "%Y/%m/%d"}} <a href="{{ post.url }}">{{ post.title }}</a> 
```
{% endraw %}

## Additional: Change Theme

There are several [themes](https://pages.github.com/themes/) you can pick from.
Visit the github page of the theme, they provide a name for you to add to
`_config.yml`. For example, to use the [Minimal
theme](https://github.com/pages-themes/minimal), simply add the following to
`_config.yml`:

```
theme: jekyll-theme-minimal
```

## My Words

Many tutorials I found are over-engineered. For example, [Jekyll's official
document](https://jekyllrb.com/docs/ruby-101/) teaches you Gems tool before you
start to write a blog. Another example, if you follow the installation steps most
website provides, you may end up dealing with system dependency bugs like
[this](https://github.com/jekyll/jekyll/issues/7274#issuecomment-425069689)
and
[this](https://stackoverflow.com/questions/18599889/error-while-executing-gem-gemfilepermissionerror). I've been looking for a toturial on that provides the minimum steps needed for setting up a markdown blog but couldn't find one. So, I wrote one.

Please comment if anything doesn't work for you. We can figure it out together.
