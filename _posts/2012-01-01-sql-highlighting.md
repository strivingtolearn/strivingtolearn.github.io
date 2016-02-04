---
layout: default
title: SQL Highlighting
---

Here is a mashup of SQL, MySQL, and PostgreSQL all in the same code blocks but
each with a different pygments lexer chosen (sql, mysql, postgresql). I just
want to see what looks different and which ones catch which keywords.

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
