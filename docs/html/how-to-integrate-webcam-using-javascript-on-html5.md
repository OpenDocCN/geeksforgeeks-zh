# 如何在 HTML5 上使用 JavaScript 集成网络摄像头？

> 原文:[https://www . geesforgeks . org/如何使用 html5 上的 javascript 集成网络摄像头/](https://www.geeksforgeeks.org/how-to-integrate-webcam-using-javascript-on-html5/)

在本文中，我们将分享一个非常简单的 JavaScript 代码片段，通过它您可以轻松地将网络摄像头集成到 HTML5 网页中。现在，每天大多数网站都提供实时网络摄像头集成，用于个人资料图片上传或任何帐户验证步骤。

首先，使用下面的代码片段创建一个 HTML DOM 结构。为了整合网络摄像头和网页，我们将使用 HTML video 标签。我们将使用 Bootstrap 和 jQuery 使我们的网页具有交互性。

```html
<video id="video" width="100%" height="100%" autoplay></video>
```

**示例:**本示例使用 HTML5、Bootstrap、JavaScript 和 jQuery 将网络摄像头与页面集成。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>
        How to Integrate Webcam using
        JavaScript on HTML5 ?
    </title>
    <link rel="stylesheet" href="css/style.css">
    <link href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css"
            rel="stylesheet">

    <script src=
"http://ajax.googleapis.com/ajax/libs/jquery/1.9.1/jquery.min.js" 
    type="text/javascript">

    </script>

    <script src=
"https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/js/bootstrap.bundle.min.js">
    </script>
</head>

<body>
    <div class="container">
        <div class="row">
            <div class="col-sm-12">
                <div class="card">
                    <h5 class="card-header h5 text-center">
                        HTML 5 & JS live Cam
                    </h5>
                    <div class="card-body">
                        <div class="booth">
                            <video id="video" width="100%" 
                                height="100%" autoplay>
                            </video>
                        </div>

                        <div class="text-right">
                            <a href="#!" class="btn btn-danger" 
                                onClick="stop()">
                                Stop Cam
                            </a>
                            <a href="#!" class="btn btn-success"
                                onClick="start()">
                                Start Cam
                            </a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        var stop = function () {
            var stream = video.srcObject;
            var tracks = stream.getTracks();
            for (var i = 0; i < tracks.length; i++) {
                var track = tracks[i];
                track.stop();
            }
            video.srcObject = null;
        }
        var start = function () {
            var video = document.getElementById('video'),
                vendorUrl = window.URL || window.webkitURL;
            if (navigator.mediaDevices.getUserMedia) {
                navigator.mediaDevices.getUserMedia({ video: true })
                    .then(function (stream) {
                        video.srcObject = stream;
                    }).catch(function (error) {
                        console.log("Something went wrong!");
                    });
            }
        }
        $(function () {
            start();
        });  
    </script>
</body>

</html>
```

**输出:**
![](img/c8954e1341e311c1480e1c4fad3abf43.png)

**Git 资料来源:**[https://github . com/gauravnewton/html 5-js-live cam](https://github.com/gauravnewton/html5-js-live-cam)