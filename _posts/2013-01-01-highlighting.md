---
layout: default
---

## Ruby

{% highlight ruby %}
def show
  @widget = Widget(params[:id])
  respond_to do |format|
    format.html # show.html.erb
    format.json { render json: @widget }
  end
end
{% endhighlight %}

## Bash

{% highlight bash %}
#!/bin/bash
# Comment
trap something ERR
for i in {1..10}; do
  echo "Hello, world"
done
sed -i '/something/d' file
grep "^neat$" /path/to/file
{% endhighlight %}

## SH

{% highlight sh %}
#!/bin/sh
# Comment
trap something ERR
for i in {1..10}; do
  echo "Hello, world"
done
sed -i '/something/d' file
grep "^neat$" /path/to/file
{% endhighlight %}

## KSH

{% highlight ksh %}
#!/bin/ksh
# Comment
trap something ERR
for i in {1..10}; do
  echo "Hello, world"
done
sed -i '/something/d' file
grep "^neat$" /path/to/file
{% endhighlight %}

## CSH

{% highlight csh %}
#!/bin/csh
# Comment
trap something ERR
for i in {1..10}; do
  echo "Hello, world"
done
sed -i '/something/d' file
grep "^neat$" /path/to/file
{% endhighlight %}

## C

{% highlight c %}
#include <stdio.h>
#include <stdlib.h>

int main(void) {
  printf("Hello, world\n");
  return EXIT_SUCCESS;
}
{% endhighlight %}

## C++

{% highlight cpp %}
#include <iostream>

int main() {
  std::cout << "Hello, World.";
  return 0;
}

{% endhighlight %}

## HTML

{% highlight html %}
<!DOCTYPE html>
  <head>
    <title>Title</title>
    <style>body {width: 500px;}</style>
    <script type="application/javascript">
      function $init() {return true;}
    </script>
  </head>
  <body>
    <p class="test" id='title'>Hello, world</p>
    <!-- here goes the rest of the page -->
  </body>
</html>
{% endhighlight %}

## CSS

{% highlight css %}
{% endhighlight %}

## Perl

{% highlight perl %}
{% endhighlight %}

## Make

{% highlight make %}
{% endhighlight %}

## Diff

{% highlight diff %}
{% endhighlight %}

## Python

{% highlight python %}
{% endhighlight %}

## PHP

{% highlight php %}
{% endhighlight %}

## SQL

{% highlight sql %}
select name, ip, environment
	FROM hosts
	ORDER BY environment, name;
select name, updated_at, timediff(now(),created_at)
  from hosts
  where updated_at <= date_sub(now(), interval 24 hour);
select distinct fact_values.value
  from fact_names
  join fact_values
    on fact_values.fact_name_id=fact_names.id
  where fact_names.name="roles"
  order by value;
SELECT a, b FROM c JOIN (d,e) ON c.id = d.id AND d.id = e.fid;
SELECT a, b FROM c JOIN (d CROSS JOIN e) ON c.id = d.id AND d.id = e.fid;
\d pg_attribute
{% endhighlight %}

## MySQL

{% highlight mysql %}
select name, ip, environment
	FROM hosts
	ORDER BY environment, name;
select name, updated_at, timediff(now(),created_at)
  from hosts
  where updated_at <= date_sub(now(), interval 24 hour);
select distinct fact_values.value
  from fact_names
  join fact_values
    on fact_values.fact_name_id=fact_names.id
  where fact_names.name="roles"
  order by value;
SELECT a, b FROM c JOIN (d,e) ON c.id = d.id AND d.id = e.fid;
SELECT a, b FROM c JOIN (d CROSS JOIN e) ON c.id = d.id AND d.id = e.fid;
\d pg_attribute
{% endhighlight %}

## PostgreSQL

{% highlight postgresql %}
select name, ip, environment
	FROM hosts
	ORDER BY environment, name;
select name, updated_at, timediff(now(),created_at)
  from hosts
  where updated_at <= date_sub(now(), interval 24 hour);
select distinct fact_values.value
  from fact_names
  join fact_values
    on fact_values.fact_name_id=fact_names.id
  where fact_names.name="roles"
  order by value;
SELECT a, b FROM c JOIN (d,e) ON c.id = d.id AND d.id = e.fid;
SELECT a, b FROM c JOIN (d CROSS JOIN e) ON c.id = d.id AND d.id = e.fid;
\d pg_attribute
{% endhighlight %}

## Text 1

{% highlight text %}
set nocompatible
set backspace=2
set ruler
set background=dark
syntax on
let loaded_matchparen=1
map <F6> <Esc>:set spell spelllang=en_us<CR>
map <F7> <Esc>:set nospell<CR>
{% endhighlight %}

## Text 2

{% highlight text %}
$ head /etc/hosts
#
127.0.0.1	localhost.localdomain		localhost
#192.168.13.10	localhost.localdomain
{% endhighlight %}

## ViM

{% highlight vim %}
set nocompatible
set backspace=2
set ruler
set background=dark
syntax on
let loaded_matchparen=1
map <F6> <Esc>:set spell spelllang=en_us<CR>
map <F7> <Esc>:set nospell<CR>
{% endhighlight %}

## AWK?

{% highlight awk %}
awk 'BEGIN{print "Hello World"}'
echo "" | awk 'BEGIN{print "Hello World"}'
echo "Hello World" | awk '{print $0}'
{% endhighlight %}

## Console (neat!)

{% highlight console %}
$ cat /etc/vim/vimrc
set nocompatible
set backspace=2
set ruler
set background=dark
syntax on
let loaded_matchparen=1
map <F6> <Esc>:set spell spelllang=en_us<CR>
map <F7> <Esc>:set nospell<CR>
{% endhighlight %}
