---
show: true
width: 12
date: 2024-01-12 00:01:00 +0800
---

<div class="p-4" style="max-width: 1200px; margin: 0 auto; font-family: 'Helvetica Neue', Arial, sans-serif;">
    <div style="display: flex; gap: 30px; align-items: flex-start;">
        <!-- 左侧区域：文字+视频 -->
        <div style="flex: 1; min-width: 0;">
            <p style="font-size: 24px; line-height: 1.6; margin-bottom: 30px; color: #333;">
                Here, I will share some interesting aspects of my life, such as sports: 
                <span style="font-weight: 600;">basketball</span>, 
                <span style="font-weight: 600;">table tennis</span>, and 
                <span style="font-weight: 600;">badminton</span>; 
                <span style="font-weight: 600;">travel</span>; and some 
                <span style="font-weight: 600;">community activities</span> 
                I organize and participate in. I believe this will help you understand me better.
            </p>
            
            <!-- 视频容器 (9:5比例) -->
            <div style="position: relative; padding-bottom: 55.56%; background: #f5f5f5; border-radius: 8px;">
                <video style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; object-fit: cover; border-radius: 8px;" controls>
                    <source src="/assets/images/my_video.mp4" type="video/mp4">
                </video>
            </div>
        </div>
        
        <!-- 右侧图片 (3:4比例) -->
        <div style="width: 350px; flex-shrink: 0;">
            <div style="position: relative; padding-bottom: 133.33%; height: 0; border-radius: 8px; overflow: hidden;">
                <img src="/assets/images/abc.png" 
                     style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; object-fit: cover;" 
                     alt="My activities showcase">
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
    
    function adjustLayout() {
        // 计算左侧总高度
        const leftHeight = leftColumn.offsetHeight;
        
        // 根据3:4比例计算图片宽度
        const imgWidth = Math.min(leftHeight * 0.75, 400); // 限制最大宽度
        
        // 设置图片容器尺寸
        rightColumn.style.width = imgWidth + 'px';
    }
    
    // 初始调整
    adjustLayout();
    
    // 响应式调整
    window.addEventListener('resize', adjustLayout);
    
    // 确保图片加载后重新计算
    const img = rightColumn.querySelector('img');
    img.onload = adjustLayout;
});
</script>

<style>
@media (max-width: 900px) {
    .p-4 > div {
        flex-direction: column;
    }
    .p-4 > div > div:last-child {
        width: 100% !important;
        margin-top: 30px;
    }
    .p-4 > div > div:last-child > div {
        padding-bottom: 75% !important; /* 移动端保持3:4比例 */
    }
    .p-4 p {
        font-size: 22px !important;
    }
}
</style>