
---
show: true
width: 12
date: 2024-01-12 00:01:00 +0800
---

<div class="p-4" style="max-width: 1200px; margin: 0 auto;">
    <div style="display: flex; align-items: flex-start;">
        <!-- 左边：文字和视频 -->
        <div style="flex: 1; display: flex; flex-direction: column; justify-content: space-between;">
            <p style="font-size: 20px; margin: 0 0 20px 0;">
                <code>Showcase</code> Here, I will share some interesting aspects of my life, such as sports: basketball, table tennis, and badminton; travel; and some community activities I organize and participate in. I believe this will help you understand me better.
            </p>
            <div style="position: relative; padding-bottom: 55.56%; height: 0; overflow: hidden;">
                <!-- 视频宽高比为9:5 (5 / 9 ≈ 0.5556) -->
                <video style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;" controls>
                    <source src="/assets/videos/my_video.mp4" type="video/mp4">
                    Your browser does not support the video tag.
                </video>
            </div>
        </div>
        <!-- 右边：图片 -->
        <div style="margin-left: 20px; position: relative; padding-bottom: 75%; height: 0; overflow: hidden;">
            <!-- 图片宽高比为3:4 (4 / 3 ≈ 1.3333) -->
            <img src="/assets/images/abc.png" alt="Showcase image" style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; object-fit: cover;">
        </div>
    </div>
    <script>
        // 获取文字和视频容器以及图片元素
        const textVideoContainer = document.querySelector('.p-4 > div > div:first-child');
        const rightImageContainer = document.querySelector('.p-4 > div > div:last-child');

        // 等待图片加载完成
        const img = rightImageContainer.querySelector('img');
        img.onload = function() {
            // 获取文字和视频容器的总高度
            const textVideoHeight = textVideoContainer.offsetHeight;

            // 获取图片的原始宽高比
            const imgAspectRatio = 4 / 3; // 3:4

            // 计算图片的宽度，使其高度等于文字和视频容器的高度
            const imgWidth = textVideoHeight / imgAspectRatio;

            // 设置图片容器的宽度
            rightImageContainer.style.width = imgWidth + 'px';

            // 设置图片容器的高度等于文字和视频容器的高度
            rightImageContainer.style.height = textVideoHeight + 'px';
        };

        // 动态调整布局以适应窗口大小变化
        window.addEventListener('resize', function() {
            const img = rightImageContainer.querySelector('img');
            const textVideoHeight = textVideoContainer.offsetHeight;
            const imgAspectRatio = 4 / 3; // 3:4
            const imgWidth = textVideoHeight / imgAspectRatio;
            rightImageContainer.style.width = imgWidth + 'px';
            rightImageContainer.style.height = textVideoHeight + 'px';
        });
    </script>
