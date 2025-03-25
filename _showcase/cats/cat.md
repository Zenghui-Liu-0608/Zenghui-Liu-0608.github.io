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
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    grid-auto-rows: 100px; /* 定义基础行高，便于计算跨度 */
    grid-gap: 10px;
    grid-auto-flow: dense; /* 紧密排列 */
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
  /* 响应式设计 */
  @media (max-width: 768px) {
    .masonry-gallery {
      grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
      grid-auto-rows: 80px; /* 调整小屏幕行高 */
    }
  }
  @media (max-width: 480px) {
    .masonry-gallery {
      grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
      grid-auto-rows: 60px; /* 调整小屏幕行高 */
    }
  }
</style>

{% assign years = "2025,2024,2023,2022,2021,2020,2019,before2019" | split: "," %}

{% for year in years %}
  <div class="year-section">
    <h2 class="year-title">{{ year }}</h2>
    <div class="masonry-gallery" id="gallery-{{ year }}">
      {% for image in site.static_files %}
        {% if image.path contains 'assets/dcim/' and image.path contains year %}
          <img src="{{ image.path | relative_url }}" title="{{ image.path | split: '/' | last | split: '.' | first }}" class="img-fluid rounded" loading="lazy">
        {% endif %}
      {% endfor %}
    </div>
  </div>
{% endfor %}

<script>
  document.addEventListener('DOMContentLoaded', function() {
    {% for year in years %}
      const gallery{{ year }} = document.getElementById('gallery-{{ year }}');
      const images{{ year }} = gallery{{ year }}.querySelectorAll('img');
      images{{ year }}.forEach(img => {
        img.addEventListener('load', function() {
          const height = img.clientHeight; // 获取图片实际高度
          const rowHeight = parseInt(window.getComputedStyle(gallery{{ year }}).getPropertyValue('grid-auto-rows')); // 获取网格行高
          const span = Math.ceil(height / rowHeight); // 计算应跨越的行数
          
          // 如果图片高度接近或超过两倍行高，设置跨越两行
          if (span >= 2) {
            img.style.gridRow = 'span 2';
          } else {
            img.style.gridRow = 'span 1'; // 普通图片占一行
          }
        });
      });
    {% endfor %}
  });
</script>