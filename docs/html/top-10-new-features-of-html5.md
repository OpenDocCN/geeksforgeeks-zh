# html 5 十大新功能

> 原文:[https://www.geeksforgeeks.org/top-10-new-features-of-html5/](https://www.geeksforgeeks.org/top-10-new-features-of-html5/)

HTML 代表超文本标记语言，是创建网页和网络应用程序的标准标记语言。HTML5 是 HTML 的第五个版本。随着 HTML5 功能的发明，不仅可以创建更好的网站，我们还可以创建动态网站。

**现在让我们来看看 HTML5 中添加的所有新功能，这些功能使它比 HTML 更好:**

1.  **Intro of** [**audio**](https://www.geeksforgeeks.org/html5-audio/) **and** [**video**](https://www.geeksforgeeks.org/html5-video/)**: **

    音频和视频标签是 HTML5 的两个主要补充。它允许开发者在他们的网站上嵌入视频或音频。HTML5 视频可以使用 CSS 和 CSS3 来设置视频标签的样式。您可以更改边框、不透明度、反射、渐变、过渡、变换，甚至动画。HTML5 使添加视频变得超级快，而且无需构建视频播放器。这为开发人员节省了时间，并为客户提供了更好、更经济的解决方案。

    **例:**

    ## 超文本标记语言

    ```html
    <!DOCTYPE html>
    <html>
    <body>
    <h2>Example of video and audio tag</h2>

      <video  width = "300" height = "200" controls autoplay>
           <source src = "/html5/foo.ogg" type ="video/ogg" />
           <source src = "/html5/foo.mp4" type = "video/mp4" />
            Your browser does not support the video element.
       </video>

       <audio controls autoplay>
           <source src = "/html5/audio.ogg" type = "audio/ogg" />
           <source src = "/html5/audio.wav" type = "audio/wav" />
            Your browser does not support the audio element.
       </audio>
    </body>
    </html>
    ```