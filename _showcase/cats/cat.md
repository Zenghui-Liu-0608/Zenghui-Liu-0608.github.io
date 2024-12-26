---
show: true
width: 12
date: 2020-01-12 00:01:00 +0800
group: My Life
---
<style>
  .gallery {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
    grid-gap: 10px; /* 间隔 */
  }
  .gallery img {
    width: 100%;
    height: auto;
    border-radius: 5px;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1); /* 可选：为图片添加阴影 */
  }
</style>
<div class="gallery">
  {% for image in site.static_files %}
    {% if image.path contains 'assets/dcim' %}
      <img src="{{ image.path | relative_url }}" class="img-fluid rounded">
    {% endif %}
  {% endfor %}
</div>
