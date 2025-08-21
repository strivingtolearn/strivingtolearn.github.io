---
title: Thoughts on jekyll and theming
date: 2025-08-20 07:31 -0400
description: >-
  Setting up jekyll in and of itself is rather simple. The problem comes when we
  decide to apply a pre-made theme to it. Mostly, I am not describing the minima
  or other jekyll-made themes. I'm talking about third-party themes.
categories: [computers]
tags: [jekyll]
---

### The trouble with documentation (jekyllrb)

Each third-party theme has their own opinions on how they should be set up and
I'm not just talking about how a site should _look_. I'm talking about the
_process_ of making it look that way.

In the [quickstart](https://jekyllrb.com/docs/) page for Jekyll, it has:
```sh
gem install jekyll bundler
jekyll new myblog
cd myblog
bundle exec jekyll serve
```

This is simple and concise and provides near copy-pastable instructions (except
for changing `myblog` to the actual name you want). The problem begins when you
are an engineer with 20+ years in the server deployment/administration field who
has installed many gems and even more bundles.

> Jekyll (and most gems) should generally _not_ be installed as a bare gem but
> rather as _bundles_. This makes gem management infinitely more manageable.
{: .prompt-tip }

However, the next command: `jekyll new myblog` requires that Jekyll be installed
and as it is a command that sets up the boilerplate (including a new `Gemfile`)
and that also runs `bundle install` for you, it is a necessary minimum
requirement in this paradigm.

Generally, what docs Jekyll has are good. They are just sparse and leave a lot
of questions (that a seasoned engineer might ask) unanswered. Their goal is
quick, fast, and easy pre-generated static websites, which is fine, however: is
aiming directly and only at the lowest possible common denominator the best
goal? Here is what I did, to sidestep this "problem" knowing that this is a
major contradiction to the standard ruby-ecosystem workflow:
```shell
mkdir myblog
cd myblog
echo -e "source 'https://rubygems.org'\n\ngem 'jekyll'\ngem 'minima'" >Gemfile
bundle install
bundle exec jekyll new . --force
```

With just one extra command it avoids having Jekyll's a system gem. And does
everything the Jekyll doc's commands will do. For complete a total n00bs, either
likely won't matter, but when you understanding the things that are happening,
it just might...

### The trouble with documentation (themes)

The next problem that left me shaking my fist
![Image](/assets/img/old-man-yells-at-jekyll.png){: h="50" w="50" .right } at
every 3rd party theme I found. **_THEY BREAK HOW JEKYLL DOES THINGS!_**.
Sometimes it is subtle. A particular Jekyll method that does not work with your
theme. Sometimes it is a vastly more in depth changing of Jekyll to get what they
believe is the Right Way® of doing what they are trying to do. This is open
source, and as such, I applaud this changing and modifying of code. However,
when a theme changes core, it seems that modifying the upstream project would be
the better way of doing things. **If** it were all documented well, then you
could at least navigate the situation, after DE tangling all the other docs (see
next rant). The problem appears to be mainly that web designers are making most
of these themes and software development is not their core competency. Sure,
exceptions exist, but they are just that: exceptions. This is no knock on web
designers. I am a systems-level software developer and as such web design is
nowhere near something I am capable of doing well. It's just how it is. We can't
be great at everything. :shrug: Every theme that I liked how wildly varying
amounts of documentation, wildly varying quality of documentation, and wildly
varying ideas on how to set the theme up. The ones I saw the most were:

* Fork a repo
* Create a repo from a template repo
* Download a zip file

I put those in order of most disgusting to least disgusting. Especially since a
simple one-line addition to your already extant `Gemfile` is all that should be
needed. They have different gripes and complaints about why using their gem is
less that ideal (note, they give no technical reasons, only ease of use for
n00bs). And their reasons conflict with upstream Jekyll's idea of The Right Way®
of doing it. In this instance, I agree with upstream. Here's a solid example
that I ran into a lot: Jekyll says install the gem. Theme maintainer says don't
use the gem because you can't update certain files like `_layout.html` (or
whatever). Here's the rub, the theme maintainers claim to be making it as easy
as possible to get started, but editing that file is not something you do when
getting started. And even if it is a gem and the file only exists in the gem's
path, code to override the built-in file if a local copy exists is a common and
simple pattern to keep simple and advanced users happy. Bottomline **IT IS
ACTUALLY HARDER TO UPDATE YOUR THEME WHEN THE THEME MAINTAINER MAKES CHANGES
WHEN USING ANYTHING BUT GEMS!** Unless you are setting up cronjobs or systemd
timers or github workflows to constantly pull changes in from the base repo that
you created from and then (carefully) merge those changes into your main (or
whichever) branch, test it, see if you actually _like_ the changes, and them
merge into your deployed branch. I could say more, but I'm a tad heated about
this and this rant has gone on long enough. :shrug:

### The trouble with documentation (consistency)

This one will be short. It boils down to:

- this doc says do steps 1, 2, 3
- that doc says do steps 4, 5, 6

and yet 100 other sites have other variations on those steps, or they re-order
them, or skip some, or they were written for and older (or newer) version of
Jekyll or for the GitHub Pages version of Jekyll. Or they assume GitHub Pages
deployment vs any other mode of deployment. It all gets pretty hairy pretty
fast. :sigh:

Anyway, welcome to my first article! ![Image](/assets/img/cheers.png){: .right }
