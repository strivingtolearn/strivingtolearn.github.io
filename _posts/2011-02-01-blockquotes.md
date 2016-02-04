---
layout: default
---

## Single input line (wrapping as needed)

{% highlight text %}
> Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt
{% endhighlight %}

### Renders as:

> Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt

## Multiple input lines (forcing the wrapping)

This just isn't worth the effort to attempt markdown syntax as you will have to
also use liquid's remove tag to strip markdown's p tags. Just use straight html.

<pre>
&lt;blockquote&gt;Lorem ipsum dolor sit amet,&lt;/blockquote&gt;
&lt;blockquote&gt;consectetur adipiscing elit,&lt;/blockquote&gt;
&lt;blockquote&gt;sed do eiusmod tempor incididunt&lt;/blockquote&gt;
</pre>

### Renders as:

<blockquote>Lorem ipsum dolor sit amet,</blockquote>
<blockquote>consectetur adipiscing elit,</blockquote>
<blockquote>sed do eiusmod tempor incididunt</blockquote>

<p></p>

### For you really crazy bastards:

{% assign openTag = '{{' %}
{% assign closeTag = '}}' %}
{% assign filter = '| markdownify | remove: "&lt;p>" | remove: "&lt;/p>"' %}
<pre>
{{ openTag }} {{ '"> Lorem ipsum dolor sit amet,"' }} {{ filter }} {{ closeTag }}
{{ openTag }} {{ '"> consectetur adipiscing elit,"' }} {{ filter }} {{ closeTag }}
{{ openTag }} {{ '"> sed do eiusmod tempor incididunt"' }} {{ filter }} {{ closeTag }}
</pre>

### Renders as:

{{ "> Lorem ipsum dolor sit amet," | markdownify | remove: "<p>" | remove: "</p>" }}
{{ "> consectetur adipiscing elit," | markdownify | remove: "<p>" | remove: "</p>" }}
{{ "> sed do eiusmod tempor incididunt" | markdownify | remove: "<p>" | remove: "</p>" }}

<!-- vim: set tw=80 ts=2 sw=2 et: -->
