# 如何在 Html & JavaScript 中使用网页分享 API 进行原生分享选项？

> 原文:[https://www . geesforgeks . org/如何使用-web-share-API-for-native-share-options-in-html-JavaScript/](https://www.geeksforgeeks.org/how-to-use-web-share-api-for-native-share-options-in-html-javascript/)

**网络共享应用编程接口**是一个 JavaScript 应用编程接口，允许网站通过与**操作系统**集成，通过设备的**本地共享对话框**共享**文本/网址/文件**。它只适用于**移动设备**和有限的浏览器。它最初是在 Chrome 61 中为安卓推出的。

**网页分享 API 功能:**

*   能够共享网址、纯文本或文件。
*   本机、用户友好和用户自定义的共享对话框。
*   更少的代码和操作系统管理的用户界面。(开发人员不需要手动处理对话框)
*   广泛的共享选项。(开发者不用担心。)

**网页分享 API 的限制:**

*   仅在特定浏览器和设备上受支持。(建议添加回退以防止兼容性问题)
*   仅通过 HTTPS 提供。
*   为了防止误操作，它只能在响应某些用户操作(如点击)时触发

**注意:**桌面和非 HTTPS 协议不支持 Web 共享 API。因此，为了使用它，有必要在 HTTPS 提供网页服务。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        How to use web share API for native 
        share options in HTML and JavaScript?
    </title>
</head>

<body style="text-align: center;">
    <h1 style="color: green;">GeeksforGeeks</h1>

    <h2>Web Share API Demonstration</h2>

    <button id="shareBtn">Share</button>

    <script>
        document.querySelector('#shareBtn')
        .addEventListener('click', event => {

            // Fallback, Tries to use API only
            // if navigator.share function is
            // available
            if (navigator.share) {
                navigator.share({

                    // Title that occurs over
                    // web share dialog
                    title: 'GeeksForGeeks',

                    // URL to share
                    url: 'https://geeksforgeeks.org'
                }).then(() => {
                    console.log('Thanks for sharing!');
                }).catch(err => {

                    // Handle errors, if occured
                    console.log(
                    "Error while using Web share API:");
                    console.log(err);
                });
            } else {

                // Alerts user if API not available 
                alert("Browser doesn't support this API !");
            }
        })
    </script>
</body>

</html>
```

**输出:**

<video class="wp-video-shortcode" id="video-566173-1" width="640" height="360" autoplay="" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210302114654/share.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210302114654/share.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210302114654/share.mp4)</video>

下面列出的许多浏览器都支持此方法:

*   Android chrome(61+)
*   Firefox android (79+)
*   Opera 安卓(48+)
*   iOS 之旅 （12.2+）
*   三星互联网(8.0+)

**参考:**[https://developer . Mozilla . org/en-US/docs/Web/API/Navigator/share](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/share)