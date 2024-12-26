---
show: true
width: 12
date: 2020-01-12 00:01:00 +0800
group: My Life
---
<style>
  .gallery {
    display: flex;
    flex-wrap: wrap;
    margin: -5px; /* Negative margin to compensate for the padding */
  }
  .gallery img {
    flex: 1 0 21%; /* adjust number to increase/decrease width, keeping margin in mind */
    margin: 5px;
    max-width: calc(25% - 10px); /* adjust width minus twice the margin */
    height: auto;
    border-radius: 5px;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1); /* Optional: Adds shadow to images */
  }
</style>
<div class="gallery">
  {% for image in site.static_files %}
    {% if image.path contains 'assets/dcim' %}
      <img src="{{ image.path | relative_url }}" class="img-fluid rounded">
    {% endif %}
  {% endfor %}
</div>
