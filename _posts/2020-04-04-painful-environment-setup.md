# Painful Environment Setup

Setting up an environment to start contributing opensource projects is difficulty and messy.

# Problems

I followed [Github Official guide](https://help.github.com/en/github/working-with-github-pages/creating-a-github-pages-site-with-jekyll) to setup Jekyll and deploy it on Github Pages. The experience is terrible as I ran into a series of problems.

Background: `jekyll` is a tool that transform plain texts into static websites and blogs. Github Pages is a platform that we can host static websites. The guide guides us to install `jekyll` and deploy on Github Pages.

## Problem 1

When I started to `gem install`, I got:

```
ERROR: While executing gem ... (Gem::FilePermissionError)
```

This is the first error I got, and it seems to be the Mac built-in ruby prevents me from installing gem packages without `sudo`. It was resolved by:

```bash
$ brew install ruby
$ echo 'export PATH="/usr/local/opt/ruby/bin:$PATH"' > ~/.zshrc
```

## Problem 2

I tried `gem install` again and `bundler` was install without a problem, but for `jekyll`, I got an error while installing. [This Github Issue post](https://github.com/jekyll/jekyll/issues/7274#issuecomment-425069689) describes the solution to my issue. However, the `rbenv install` process took a very long time to run, and I didn't want to wait.

## Problem 3

Ah Ha. I think I can use docker containers to run `jekyll`. It should encapsulate the whole installation process and ganrantee a consistant behavior. Most importantly, it should not depend on what I've install or setup my on host environment. So I found [this docker](https://github.com/envygeeks/jekyll-docker/blob/master/README.md) image should solve my problem.

It describes how many `jekyll build` examples. But, it wasn't a full example of how we create a new `jekyll` project. I found [another docker image](https://github.com/BretFisher/jekyll-serve) provided on github where it demos examples of `jekyll new`, `jekyll serve`, etc. However, when I copied and pasted the command of `jekyll new` in it demostrated, it failed, and asked me to pass-in `-f` to overwrite something that has been generated before.

I ended up using the fist docker image I found, which seems to an official image released by `jekyll` and combined with the commands I learned from the original tutorial written by Github. Everything works.

## Other Problems

I described the exact problems and the corresponding solutions above. However, I have gone into some wrong paths as well while resolving the issues.

- This "[Easy Markdown to Github Pages](https://nicolas-van.github.io/easy-markdown-to-github-pages/)" tutorial taught me that I can simply put markdown files into the folder and push to a GitHub repo, then everything will work. I think it does work as there's some logic on Github end to handle this use case. However, that document didn't teach me about `Jekyll new or `Jekyll build` so I didn't know how to test locally.
- This ["jekyll-now" template](https://github.com/barryclark/jekyll-now) let people to "fork" the template and everything is set up. However, it still doesn't teach me how to test locally after I clone the template.

# Solution

My solution is to find a Dockerized approache whenver it's possible. In my case, I should just ignore all installation and run `Jekyll new` right the way with a prefix `export JEKYLL_VERSION=3.8  docker run --rm -p 4000:4000 --volume="$PWD:/srv/jekyll" -it jekyll/jekyll:$JEKYLL_VERSION`.

# Takeaway

