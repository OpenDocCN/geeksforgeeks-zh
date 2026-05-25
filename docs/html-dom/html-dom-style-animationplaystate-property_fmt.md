# HTML | DOM 样式动画播放状态属性

> 原文:[https://www . geesforgeks . org/html-DOM-style-animationplaystate-property/](https://www.geeksforgeeks.org/html-dom-style-animationplaystate-property/)

**HTML DOM Style `animationPlayState`**属性用于指定动画是正在运行还是暂停。

## 语法:

```html
animation-play-state: running|paused|initial|inherit;
```

## 返回值:
返回一个字符串，代表元素的动画播放状态属性。

## 属性值:

*   `running`: 该值用于运行/播放动画。
*   `paused`: 该值用于暂停动画。
*   `initial`: 该值将`animation-play-state`属性设置为父元素的值。
*   `inherit`: 该值用于设置`animation-play-state`属性为默认(`running`)。

## 示例: `animation-play-state: running`

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML | DOM Style animationPlayState Property
    </title>
    <style>
        div {
            height: 100px;
            width: 150px;
            font-size: 100px;
            -webkit-animation: movement 3s infinite;
            -webkit-animation-play-state: paused;
            animation: movement 3s infinite;
            color: darkgreen;
            position: relative;
            /* property value "running" */
            animation-play-state: running;
        }

        @-webkit-keyframes movement {
            from {
                left: 50px;
            }
            to {
                left: 400px;
            }
        }

        @keyframes movement {
            from {
                left: 50px;
            }
            to {
                left: 400px;
            }
        }
    </style>
</head>

<body>
    <br>
    <div id="block">Geeks For Geeks</div>
</body>

</html>
```

**输出:**

<video class="wp-video-shortcode" id="video-267660-1" width="665" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/Microsoft-Edge-18-01-2019-23_25_46.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/Microsoft-Edge-18-01-2019-23_25_46.mp4](https://media.geeksforgeeks.org/wp-content/uploads/Microsoft-Edge-18-01-2019-23_25_46.mp4)</video>

## 示例: `animation-play-state: paused`

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML | DOM Style animationPlayState Property
    </title>
    <style>
        div {
            height: 100px;
            width: 150px;
            font-size: 100px;
            -webkit-animation: movement 3s infinite;
            -webkit-animation-play-state: paused;
            animation: movement 3s infinite;
            color: darkgreen;
            position: relative;
            /* property value "paused" */
            animation-play-state: paused;
        }

        @-webkit-keyframes movement {
            from {
                left: 50px;
            }
            to {
                left: 400px;
            }
        }

        @keyframes movement {
            from {
                left: 50px;
            }
            to {
                left: 400px;
            }
        }
    </style>
</head>

<body>
    <button onclick="Play()">
      Click to make the object move
    </button>
    <script>
        function Play() {
            document.getElementById("block").style.WebkitAnimationPlayState = "running";
            document.getElementById("block").style.animationPlayState = "running";
        }
    </script>
    <br>
    <div id="block">Geeks For Geeks</div>
</body>

</html>
```

**输出:**

<video class="wp-video-shortcode" id="video-267660-2" width="665" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/Microsoft-Edge-18-01-2019-23_30_48.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/Microsoft-Edge-18-01-2019-23_30_48.mp4](https://media.geeksforgeeks.org/wp-content/uploads/Microsoft-Edge-18-01-2019-23_30_48.mp4)</video>

## 示例: `animation-play-state: inherit`

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML | DOM Style animationPlayState Property
    </title>
    <style>
        div {
            height: 50px;
            width: 150px;
            font-size: 100px;
            -webkit-animation: movement 3s infinite;
            -webkit-animation-play-state: paused;
            animation: movement 3s infinite;
            color: darkgreen;
            position: relative;
            animation-play-state: running;
        }

        h4 {
            width: 150px;
            -webkit-animation: movement 3s infinite;
            -webkit-animation-play-state: paused;
            animation: movement 3s infinite;
            color: darkgreen;
            position: relative;
            /* property value "inherit" */
            animation-play-state: inherit;
        }

        @-webkit-keyframes movement {
            from {
                left: 50px;
            }
            to {
                left: 400px;
            }
        }

        @keyframes movement {
            from {
                left: 50px;
            }
            to {
                left: 400px;
            }
        }
    </style>
</head>

<body>
    <br>
    <div id="block">
        Gfg
        <h4> I'm inherited</h4>
    </div>
</body>

</html>
```

**输出:**

<video class="wp-video-shortcode" id="video-267660-3" width="665" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/Microsoft-Edge-18-01-2019-23_56_18.mp4?_=3">[https://media.geeksforgeeks.org/wp-content/uploads/Microsoft-Edge-18-01-2019-23_56_18.mp4](https://media.geeksforgeeks.org/wp-content/uploads/Microsoft-Edge-18-01-2019-23_56_18.mp4)</video>

## 示例: `animation-play-state: initial`

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML | DOM Style animationPlayState Property
    </title>
    <style>
        div {
            height: 100px;
            width: 150px;
            font-size: 100px;
            -webkit-animation: movement 3s infinite;
            -webkit-animation-play-state: paused;
            animation: movement 3s infinite;
            color: darkgreen;
            position: relative;
            /* property value "initial" */
            animation-play-state: initial;
        }

        @-webkit-keyframes movement {
            from {
                left: 50px;
            }
            to {
                left: 400px;
            }
        }

        @keyframes movement {
            from {
                left: 50px;
            }
            to {
                left: 400px;
            }
        }
    </style>
</head>

<body>
    <br>
    <div id="block">Geeks For Geeks</div>
</body>

</html>
```

**输出:**

<video class="wp-video-shortcode" id="video-267660-4" width="665" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/Microsoft-Edge-18-01-2019-23_25_46.mp4?_=4">[https://media.geeksforgeeks.org/wp-content/uploads/Microsoft-Edge-18-01-2019-23_25_46.mp4](https://media.geeksforgeeks.org/wp-content/uploads/Microsoft-Edge-18-01-2019-23_25_46.mp4)</video>

## 支持的浏览器:
`animation-play-state`属性支持的浏览器如下:

*   Chrome: 43.0(4.0 webkit)
*   Firefox: 16.0
*   Safari: 4.0 webkit
*   Edge: 10.0
*   Opera: 30.0(15.0 webkit)