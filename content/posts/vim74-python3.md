---
title: "Installing python3 support for VIM 7.4"
date: "2014-07-06"
description: "How to get python3 & python2 support for VIM 7.4"
categories:
    - "vim"
    - "python"
---
# VIM and Python3

I've been lucky enough to learn [Python][python] at work recently. It is
quickly become my favorite language! Since we're starting a new exploratory
project at work we decided to work with python3. It's the right decision
__but__ unfortunately VIM still lacks great plug-ins that "just work" with
python3.

I'm currently using [python-mode][pymode] which is _ok_ but I'm considering
testing out [jedi-vim][jedi] which seem like a more interesting alternative.

I've learned that both these plug-ins do support python3 but they both require
[vim] to be installed with `+python3` to support it. I've had some issue
getting this to work but here are the instructions for the different OS' I need
to work in.

# MAC:

OS-X turned out to be easy (there is a reason it's my preferd OS), yet it still
took me awhile to figure out! I use [homebrew][brew] and [macvim][macvim] and
after I finally looked _inside_ the [homebrew _formula_] [formula] I managed to
figure out the switch (see below). As a side not I also learned you can `brew
options <formula>` to see available switches.

So to get python 2 & 3 support for [macvim] using [brew] I simply did:

```
brew install macvim -override-system-vim -with-python3
```

That's it! With that I show "dynamic" support (`__+__python/dyn` &
`__+__python3/dyn`) for both Python 2 & 3 when I do `mvim --version` or
`:version` from inside [macvim] in normal mode. Hopefully this will make python
mode work even better with my python3 files.

While I was at it I also reinstalled [vim] with:

```
brew install vim --override-system-vi --with-python3
```

Which gave me this warning: `Your PYTHONPATH points to a site-packages dir for
Python 2.x but you are running Python 3.x!` but still worked and shows
`+python3/dyn`. I use vim less frequently on mac but hopefully it's working!

# Next steps...

I also need to get python3 support for [vim] under [cygwin]. I will update this
page if I figure out how to do that. I think it will require me to build from
source.


[python]:http://www.python.org
[pymode]:https://github.com/klen/python-mode
[jedi]: https://github.com/davidhalter/jedi-vim
[vim]: http://www.vim.org
[formula]: https://github.com/Homebrew/homebrew/blob/master/Library/Formula/macvim.rb
[macvim]: https://github.com/b4winckler/macvim
