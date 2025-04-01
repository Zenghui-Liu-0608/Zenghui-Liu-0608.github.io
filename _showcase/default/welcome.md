---
show: true
width: 12
date: 2024-01-12 00:01:00 +0800
---

<div class="p-4" style="max-width: 1200px; margin: 0 auto;">
    <div style="display: flex; align-items: flex-start;">
        <!-- 左边：文字和视频 -->
        <div style="flex: 1; display: flex; flex-direction: column; justify-content: space-between;">
            <p style="font-size: 20px;">
                要实现左边是文字（文字下面是视频），右边是图片，并且图片的高度等于文字加视频的总高度，可以使用CSS的Flexbox布局。以下是实现该布局的代码示例：

```html
---
show: true
width: 12
date: 2024-01-12 00:01:00 +0800
---

<div class="p-4" style="max-width: 1200px; margin: 0 auto;">
    <div style="display: flex; align-items: flex-start;">
        <!-- 左边：文字和视频 -->
        <div style="flex: 1; display: flex; flex-direction: column; justify-content: space-between;">
            <p style="font-size: 20px;">
                <code>Showcase</code> Here, I will share some interesting aspects of my life, such as sports: basketball, table tennis, and badminton; travel; and some community activities I organize and participate in. I believe this will help you understand me better.
            </p>
            <div style="margin-top: 20px;">
                <video width="100%" height="auto" controls>
                    <source src="/assets/images/my_video.mp4" type="video/mp4">
                    Your browser does not support the video tag.
                </video>
            </div>
        </div>
        <!-- 右边：图片 -->
        <div style="margin-left: 20px;">
            <img src="/assets/images/abc.png" alt="Showcase image" style="width: 300px; height: auto;" id="right-image"/>
        </div>
    </div>
    <script>
        // 获取文字和视频容器以及图片元素
        const textVideoContainer = document.querySelector('.p-4 > div > div:first-child');
        const rightImage = document.getElementById('right-image');

        // 等待图片加载完成
        rightImage.onload = function() {
            // 获取文字和视频容器的总高度
            const textVideoHeight = textVideoContainer.offsetHeight;

            // 设置图片的高度等于文字和视频容器的总高度
            rightImage.style.height = textVideoHeight + 'px';
        };
    </script>
</div>