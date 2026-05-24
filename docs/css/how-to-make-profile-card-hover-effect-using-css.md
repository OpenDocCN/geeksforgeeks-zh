# 如何使用 CSS 制作侧面卡悬停效果？

> 原文:[https://www . geesforgeks . org/如何制作-简介-卡片-悬停-效果-使用-css/](https://www.geeksforgeeks.org/how-to-make-profile-card-hover-effect-using-css/)

几乎我们所有人都一定听说过‘第一印象就是最后印象’。简介卡包含了我们应该在第一时间了解的关于一个人的最重要的细节。更好的印象吸引更多的流量。因此，为了让更多的观众参与到网站中，专注于设计网站的每一个小部分是非常重要的。简介卡就是其中之一。

在本文中，我们将学习如何使用 CSS 创建个人资料卡悬停效果。

**方法:**

*   First, we create a basic HTML template (index.html) to insert images and configuration files.
*   We have an HTML *div* with a "card" class. In the *partition* , we have an image with the category "img-box" and the personal data name and name of the account holder with the category "info".
*   Use this [contour card image](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200719193804/Why-GeeksforGeeks-is-an-Essential-Platform-for-CS-IT-Students.png) .
*   We have included "style.css" in the "index.html" file containing all css styles.
*   We need to import the following Google fonts website for *font series: [meriwether], serif* **;**

```html
@import url("https://fonts.googleapis.com/css2?family=Merriweather:wght@700&display=swap");
```

**示例:**图像将上移，带有名称的配置文件名称将显示出来。还有一个按钮可以联系用户。

## HTML

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>Profile Card</title>
        <meta name="viewport" 
             content="width=device-width, initial-scale=1">
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <div class="card">
            <div class="img-box">
                <img src=
 "https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200719193804/Why-GeeksforGeeks-is-an-Essential-Platform-for-CS-IT-Students.png" 
                alt="profile pic">
            </div>
            <div class="info">
                <h2>Profile Card</h2>
                <p>Web Designer | Influencer</p>

                <button>Contact Me</button>
            </div>
        </div>
    </body>
</html>
```