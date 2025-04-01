---
show: true
width: 12
date: 2024-01-12 00:01:00 +0800
---

<div class="p-4" style="max-width: 1200px; margin: 0 auto;">
    <div style="display: flex; gap: 20px;">
        <!-- 左侧区域：文字+视频 -->
        <div style="flex: 1; min-width: 0;">
            <p style="font-size: 20px; margin-bottom: 20px;">
                <code>Showcase</code> Here, I will share some interesting aspects of my life...
            </p>
            
            <!-- 视频容器 (9:5比例) -->
            <div style="position: relative; padding-bottom: 55.56%; background: #f0f0f0;">
                <video style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; object-fit: cover;" controls>
                    <source src="/assets/images/my_video.mp4" type="video/mp4">
                </video>
            </div>
        </div>
        
        <!-- 右侧图片 (3:4比例) -->
        <div style="width: 300px; flex-shrink: 0;">
            <div style="position: relative; padding-bottom: 133.33%; height: 0;">
                <img src="/assets/images/abc.png" 
                     style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; object-fit: cover;" 
                     alt="Showcase image">
            </div>
        </div>
    </div>
</div>

<script>
document.addEventListener('DOMContentLoaded', function() {
    // 获取左侧区域和图片容器
    const leftColumn = document.querySelector('.p-4 > div > div:first-child');
    const rightColumn = document.querySelector('.p-4 > div > div:last-child');
    const imgContainer = rightColumn.firstElementChild;
    
    // 计算左侧总高度
    const leftHeight = leftColumn.offsetHeight;
    
    // 根据3:4比例计算图片宽度
    const imgWidth = leftHeight * 0.75; // 3/4 = 0.75
    
    // 设置图片容器尺寸
    rightColumn.style.width = imgWidth + 'px';
    imgContainer.style.paddingBottom = '133.33%'; // 保持3:4比例
    
    // 响应式调整
    window.addEventListener('resize', function() {
        const newLeftHeight = leftColumn.offsetHeight;
        const newImgWidth = newLeftHeight * 0.75;
        rightColumn.style.width = newImgWidth + 'px';
    });
});
</script>

<style>
@media (max-width: 768px) {
    .p-4 > div {
        flex-direction: column;
    }
    .p-4 > div > div:last-child {
        width: 100% !important;
        margin-top: 20px;
    }
    .p-4 > div > div:last-child > div {
        padding-bottom: 75% !important; /* 移动端保持3:4比例 */
    }
}
</style>