---
show: true
width: 12
date: 2020-01-12 00:01:00 +0800
group: My Life
---
<style>
  .gallery {
    display: grid;
    grid-template-columns: repeat(4, 1fr); /* 设置为四列 */
    grid-gap: 10px; /* 图片之间的间隔 */
  }
  .gallery img {
    width: 100%;
    height: auto;
    border-radius: 5px;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
  }
</style>
<div class="gallery">
  {% for image in site.static_files %}
    {% if image.path contains 'assets/dcim' %}
      <img src="{{ image.path | relative_url }}" class="img-fluid rounded" loading="lazy">
    {% endif %}
  {% endfor %}
</div>
