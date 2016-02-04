---
layout: default
---

# Github's [markdown doc](https://guides.github.com/features/mastering-markdown/) will FOOL you!
It uses examples for github that don't necessarily work for github-pages. You
must put a blank line between many of these elements for them to render properly
in github-pages

# Header tag example (broken)

{% highlight text %}
Example
# This is an h1 tag with no blank line above it
## This is an h2 tag with no blank line above it
### This is an h3 tag with no blank line above it
#### This is an h4 tag with no blank line above it
##### This is an h5 tag with no blank line above it
###### This is an h6 tag with no blank line above it
{% endhighlight %}

### Renders as:

Example
# This is an h1 tag with no blank line above it
## This is an h2 tag with no blank line above it
### This is an h3 tag with no blank line above it
#### This is an h4 tag with no blank line above it
##### This is an h5 tag with no blank line above it
###### This is an h6 tag with no blank line above it

# Header tag example (working)

{% highlight text %}
Example

# This is an h1 tag with a blank line above it

## This is an h2 tag with a blank line above it

### This is an h3 tag with a blank line above it

#### This is an h4 tag with a blank line above it

##### This is an h5 tag with a blank line above it

###### This is an h6 tag with a blank line above it
{% endhighlight %}

### Renders as:

Example

# This is an h1 tag with a blank line above it

## This is an h2 tag with a blank line above it

### This is an h3 tag with a blank line above it

#### This is an h4 tag with a blank line above it

##### This is an h5 tag with a blank line above it

###### This is an h6 tag with a blank line above it

&nbsp;

# Header tag example when next line has no markup

{% highlight text %}
## It is fine to immediately follow a line that has markup
with a line that doesn't if you intend the 2nd line to not have markup.
{% endhighlight %}

### Renders as:

## It is fine to immediately follow a line that has markup
with a line that doesn't if you intend the 2nd line to not have markup.
