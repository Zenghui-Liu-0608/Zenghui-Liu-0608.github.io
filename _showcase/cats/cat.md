---
show: true
width: 3
date: 2020-01-12 00:01:00 +0800
group: My Life
---
<div>
{% for image in site.static_files %}
  {% if image.path contains 'assets/dcim/' %}
    <img src="{{ image.path | relative_url }}" class="img-fluid rounded" >
  {% endif %}
{% endfor %}
</div>
