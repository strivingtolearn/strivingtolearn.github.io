---
layout: default
title: Title doesn't match the file name
---

The title, if added to the [Front
Matter](https://jekyllrb.com/docs/frontmatter/), like so:

{% highlight text %}
---
title: Doesn't match the file name
---
{% endhighlight %}

Prevents autogeneration based on the filename. For example, this page is named
`{{page.path}}` and is not the same as the title.
