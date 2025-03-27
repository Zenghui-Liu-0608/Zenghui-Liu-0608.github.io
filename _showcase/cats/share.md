---
show: true
width: 12
date: 2025-03-27 00:01:00 +0800
group: My Share
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
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); /* 自动填充列，列宽最小200px */
    grid-gap: 10px; /* 图片间距 */
    grid-auto-flow: dense; /* 密集排列，减少空白 */
  }
  .masonry-gallery img {
    width: 100%;
    height: auto; /* 高度自适应 */
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0,0,0,0.1);
    transition: transform 0.3s ease;
  }
  .masonry-gallery img:hover {
    transform: scale(1.05);
  }
  .item-description {
    margin: 8px 0;
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

<!-- 工具 -->
<div class="category-section">
  <h2 class="category-title">工具</h2>
  <div class="masonry-gallery">
    
    <!-- 你的IELTS-99 sentences 工具 -->
    <div>
      <img src="/assets/tools/99s.png" alt="IELTS-99 sentences" loading="lazy"/>
      <p class="item-description">
        A local webpage that displays 99 English sentences with their Chinese translations 
        and provides text-to-speech functionality for convenient practice. 
        <a href="/assets/tools/99s.html" target="_blank">下载</a>
      </p>
    </div>

    

  </div>
</div>


