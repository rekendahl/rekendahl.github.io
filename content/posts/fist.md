---
title: "A new home"
date: "2014-07-04"
description: "Configuring new home using GitHub Pages and Hugo"
categories:
    - "hugo"
    - "github"
---
# A new home

I have decided to host my domain through [GitHub Pages][pages] using
[Hugo][hugo]. Hopefully it will give me a good environment for quick blog posts
on technical stuff I find interesting at work. This post will details what I
had to do to make it all work (hopefully not too much).

I decided to use [Hugo][hugo] mostly because I _love_ the [spf13 Vim
distribution][vimspf13]. I love it so much, in fact, that I decided to create
fork it into [edavim][edavim] with a focus on Electronic Design Automation
languages. More on that later. When I found that the same author had created a
fast, static website generator using [markdown][md] I know I had to try it.

The clincher was when I found [some
instructions](http://hugo.spf13.com/tutorials/github_pages_blog) for how to use
[Hugo][hugo] with the free [GitHub pages][pages] service.

After some reading I realized I should start with installing [Hugo][hugo] and
[pygments][pygments]

## Installing Hugo:

Download [latest version](https://github.com/spf13/hugo/releases)(`v0.11`) of
[Hugo][hugo], uzip to `/usr/local/bin` on my macbook.

```
cd ~/Downloads/
mv hugo_0.11_darwin_amd64 /usr/local/bin/.
ln -s /usr/local/bin/hugo_0.11_darwin_amd64 /usr/local/bin/hugo
```

## Installing [Pygments][pygments]

```
╭─ekendahl@Roberts-Retina-Macbook  ~
╰─$ sudo pip install Pygments                                                                                                                 1 ↵
Password:
Downloading/unpacking Pygments
  Downloading Pygments-1.6.tar.gz (1.4MB): 1.4MB downloaded
  Running setup.py (path:/private/tmp/pip_build_root/Pygments/setup.py) egg_info for package Pygments

Installing collected packages: Pygments
  Running setup.py install for Pygments

    Installing pygmentize script to /usr/local/bin
Successfully installed Pygments
Cleaning up...
```

## Test build...

```
cd ~/Projects/rekendahl.github.io/
hugo server --watch
```

Open safari to http://localhost:1313. The cool thing is that after each save the page automatically reloads. __Nice!__

# Launch GitHub Pages lessons:

1. Make sure `baseurl` in `config.yaml` is correct
2. If you do this for a personal page then you need to push to master and push
   to 'root'. So update `config.yaml` to read publishdir: "."

[pages]:https://pages.github.com
[hugo]: http://hugo.spf13.com
[vimspf13]:http://vim.spf13.com
[md]:http://daringfireball.net/projects/markdown
[pygments]:http://pygments.org
