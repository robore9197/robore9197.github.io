---
layout: page
title: Test
permalink: /test/
---

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

<h2>All Pages</h2>
<ul>
{% assign pages_list = site.pages %}
{% include JB/pages_list %}
</ul>


<h2> All Posts </h2>
<ul>
{% assign posts_collate = site.posts %}
{% include JB/posts_collate %}  
</ul>
