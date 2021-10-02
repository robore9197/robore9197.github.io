---
layout: page
title: Blogs
permalink: /blogs/
---

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

```
git clone https://<username>:<ACCESS_TOKEN>@github.com/<username>/repository.git
```

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


<h2> Categories </h2>
<ul>
  	  {% assign categories_list = site.categories %}  
  	  {% include JB/categories_list %}
</ul>

{% if site.JB.categories_list.provider == "custom" %}
  {% include custom/categories_list %}
{% else %}
  {% if categories_list.first[0] == null %}
    {% for category in categories_list %} 
    	<li><a href="{{ BASE_PATH }}{{ site.JB.categories_path }}#{{ category }}-ref">
    		{{ category | join: "/" }} <span>{{ site.categories[category].size }}</span>
    	</a></li>
    {% endfor %}
  {% else %}
    {% for category in categories_list %} 
    	<li><a href="{{ BASE_PATH }}{{ site.JB.categories_path }}#{{ category[0] }}-ref">
    		{{ category[0] | join: "/" }} <span>{{ category[1].size }}</span>
    	</a></li>
    {% endfor %}
  {% endif %}
{% endif %}
{% assign categories_list = nil %}
