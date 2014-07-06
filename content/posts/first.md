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
fork it into [vimeda][vimeda] with a focus on Electronic Design Automation
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

That was easy and it works!

## Installing [Pygments][pygments]

```
╭─ekendahl@Roberts-Retina-Macbook  ~
╰─$ sudo pip install Pygments                                                                                                                 1 ↵
```

Forgot the `sudo` the first time but otherwise even easier...

## Test build...

```
cd ~/Projects/rekendahl.github.io/
hugo server --watch
```

Open safari to http://localhost:1313. The cool thing is that after each save the page automatically reloads. __Nice!__

Once the pages looks satisfactory then `ctrl+c` the hugo server and:

1. `hugo`
2. `git add -A`
3. `git commit -m "<something descriptive>"`
4. `git push`

# Launch GitHub Pages lessons:

* Make sure `baseurl` in `config.yaml` is correct (i.e `rekendahl.github.io`) or the page won't work.
* If you do this for a personal page and not project page then you need to push to master and push
   to 'root'. So update `config.yaml` to read `publishdir: "."`


That's about it. So far _Hugo_ seems fast and easy to use. I'm really just
looking for the ability to write articles of the daily engineering work I do
and this should allow me to do that.

Next step is to go through setting up a cheap DNS service but that is another post...

[pages]:https://pages.github.com
[hugo]: http://hugo.spf13.com
[vimspf13]:http://vim.spf13.com
[md]:http://daringfireball.net/projects/markdown
[pygments]:http://pygments.org
[vimeda]:https://github.com/rekendahl/vimeda
