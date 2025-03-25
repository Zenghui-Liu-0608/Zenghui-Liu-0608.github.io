---
show: true
width: 12
date: 2020-01-12 00:01:00 +0800
group: My Life
---
<style>
  .year-section {
    margin-bottom: 30px;
  }
  .year-title {
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
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); /* 自动填充列，列宽最小200px */
    grid-gap: 10px; /* 图片间距，最小化但保留美观 */
    grid-auto-flow: dense; /* 密集排列，减少空白 */
  }
  .masonry-gallery img {
    width: 100%;
    height: auto; /* 高度自适应，保持宽高比 */
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0,0,0,0.1);
    transition: transform 0.3s ease;
  }
  .masonry-gallery img:hover {
    transform: scale(1.05); /* 鼠标悬停时放大，增加交互性 */
  }
  /* 响应式设计 */
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
</style>

{% assign years = "2025,2024,2023,2022,2021,2020,2019,before2019" | split: "," %}

{% for year in years %}
  <div class="year-section">
    <h2 class="year-title">{{ year }}</h2>
    <div class="masonry-gallery">
      {% for image in site.static_files %}
        {% if image.path contains 'assets/dcim/' and image.path contains year %}
          <img src="{{ image.path | relative_url }}" title="{{ image.path | split: '/' | last | split: '.' | first }}" class="img-fluid rounded" loading="lazy">
        {% endif %}
      {% endfor %}
    </div>
  </div>
{% endfor %}