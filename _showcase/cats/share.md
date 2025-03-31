---
show: true
width: 12
date: 2020-01-12 00:01:00 +0800
group: My Share
---

<style>
  /* 分类整体区域 */
  .category-section {
    margin-bottom: 40px;
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

  /* 单个条目容器：左右分布，垂直居中 */
  .item-container {
    display: flex;
    align-items: center; /* 关键属性：使图片与文字垂直居中 */
    margin-top: 20px;
    gap: 20px; /* 图片与文字的间隔 */
  }
  /* 图片样式 */
  .item-container img {
    max-width: 300px; 
    height: auto;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0,0,0,0.1);
  }

  /* 文字区域 */
  .item-text {
    flex: 1;
  }
  /* 文字介绍样式 */
  .item-description {
    font-size: 1.3em; /* 加大字体 */
    line-height: 1.6em; 
    margin-bottom: 0; 
  }
  .item-description a {
    text-decoration: underline;
  }
</style>

<!--Tools -->
<div class="category-section">
  <h2 class="category-title">Tools</h2>
  <div class="item-container">
    <div>
      <img src="/assets/tools/99s.png" alt="IELTS-99 sentences" loading="lazy" />
    </div>
    <div class="item-text">
      <p class="item-description">
        A local webpage that displays 'Yangshuai 99 English sentences' with their Chinese translations 
        and provides text-to-speech functionality for convenient practice. 
        <br>
        <a href="/assets/tools/99s.html" target="_blank">Go</a>
      </p>
    </div>
  </div>


 <div class="item-container">
    <div>
      <img src="/assets/tools/s100.png" alt="IELTS-100 sentences" loading="lazy" />
    </div>
    <div class="item-text">
      <p class="item-description">
        This is an online tool based on Gujiabei IELTS writing 100 sentences translation practice, designed to help IELTS candidates systematically improve the basic writing skills. This tool selects 100 core sentence patterns of frequently used topics in IELTS writing, covering common topics such as society, education, environment and science and technology. Through the scientific training mode of "Chinese prompt - English translation - answer check", it helps learners to master authentic English expressions, correct common grammatical mistakes and accumulate academic writing vocabulary.
        <br>
        <a href="/assets/tools/100s.html" target="_blank">Go</a>
      </p>
    </div>
  </div>
</div>