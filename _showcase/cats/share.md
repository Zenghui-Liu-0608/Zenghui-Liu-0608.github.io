---
show: true
width: 12
group: My Life
title: "Resource Sharing"
---

<style>
  .category-section {
    margin-bottom: 30px;
  }
  .category-title {
    font-size: 2em;
    font-weight: bold;
    margin-bottom: 15px;
    color: #2c3e50;
    border-bottom: 2px solid #3498db;
    display: inline-block;
    padding-bottom: 5px;
  }
  .masonry-gallery {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    grid-gap: 10px;
    grid-auto-flow: dense;
  }
  .masonry-gallery img {
    width: 100%;
    height: auto;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0,0,0,0.1);
    transition: transform 0.3s ease;
  }
  .masonry-gallery img:hover {
    transform: scale(1.05);
  }
  /* Responsive design for smaller screens */
  @media (max-width: 768px) {
    .masonry-gallery {
      grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
    }
  }
  @media (max-width: 480px) {
    .masonry-gallery {
      grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
    }
  }
  /* Optional styling for individual items */
  .share-item {
    text-align: center;
  }
  .share-item p {
    margin: 5px 0;
  }
</style>

{% assign categories = "Tools,Data,Code,Others" | split: "," %}

{% for cat in categories %}
  <div class="category-section">
    <h2 class="category-title">{{ cat }}</h2>
    <div class="masonry-gallery">

      {%
        comment
        Loop through a data file or collection that stores item info: category, image, intro, link, etc.
        In this example, we assume there's a data file named `resources.yml`.
        For each item, we check if its "category" matches the current cat, then display its info.
      endcomment
      %}
      {% for item in site.data.resources %}
        {% if item.category == cat %}
          <div class="share-item">
            <img src="{{ item.image | relative_url }}" alt="{{ item.name }}" loading="lazy">
            <p>{{ item.intro }}</p>
            <a href="{{ item.link | relative_url }}" download>Download</a>
          </div>
        {% endif %}
      {% endfor %}

    </div>
  </div>
{% endfor %}
