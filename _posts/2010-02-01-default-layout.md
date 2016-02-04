This is what it looks like when the ***layout*** attribute is set to "default"
in either a [configuration file](https://jekyllrb.com/docs/configuration/)
(generally `_config.yml`) or in a YAML block referred to as [Front
Matter](https://jekyllrb.com/docs/frontmatter/) in individual pages.

'single' and "double" quotes should not be broken. The layout will also allow
you to turn off smart quotes if you want.

## Smart quotes

Example that shows turning off smart quotes on
[kramdown](http://kramdown.gettalong.org/syntax.html) (the default markdown
engine for jekyll)

#### _config.yml

{% highlight yaml %}
defaults:
  -
    scope:
      path: ""
      type: "posts"
    values:
      layout: "default"
<...>
markdown: kramdown

kramdown:
    smart_quotes: ["apos", "apos", "quot", "quot"]
{% endhighlight %}


<!-- vim: set tw=80 ts=2 sw=2 et: -->

