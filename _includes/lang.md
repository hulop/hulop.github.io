{% assign tag_names = "" | split: "|"  %}

{% for posts_by_tag in site.tags %}
  {% assign tag_names = tag_names | push: posts_by_tag.first %}
{% endfor %}

{% assign tag_names = tag_names | sort %}

{% for tag_name in tag_names %}
{% if tag_name == page.lang %}
{% for post in site.tags[tag_name] %}
#### [{{ post.title }}]({{ post.url | prepend: baseurl }})
{% endfor %}
{% endif %}
{% endfor %}
