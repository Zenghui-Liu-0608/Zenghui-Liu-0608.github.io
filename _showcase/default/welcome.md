---
show: true
width: 12
date: 2024-01-12 00:01:00 +0800
---

<style>
    @media (max-width: 600px) {
        .responsive-layout {
            flex-direction: column;
        }
        .responsive-layout img {
            margin-top: 20px;
        }
    }
</style>

<div class="p-4" style="max-width: 800px; margin: 0 auto;">
    <h2>Welcome to Showcase!</h2>
    <hr />
    <div class="responsive-layout" style="display: flex; align-items: flex-start; gap: 20px;">
        <!-- 文字部分 -->
        <div style="flex: 1;">
            <p style="font-size: 20px;">
                <code>Showcase</code> Here, I will share some interesting aspects of my life, such as sports: basketball, table tennis, and badminton; travel; and some community activities I organize and participate in. I believe this will help you understand me better.
            </p>
        </div>
        <!-- 图片部分 -->
        <div>
            <img src="/assets/images/abc.png" alt="Showcase image" width="300" height="400"/>
        </div>
    </div>
    <!-- 视频部分 -->
    <div style="margin-top: 20px; text-align: center;">
        <video width="640" height="360" controls>
            <source src="/assets/images/my_video.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>
    </div>
</div></div>