# HTML | DOM 样式动画持续时间属性

> 原文:[https://www . geesforgeks . org/html-DOM-style-animation duration-property/](https://www.geeksforgeeks.org/html-dom-style-animationduration-property/)

HTML DOM 中的 Style **animationDuration** 属性用于设置完成一个动画周期的时间间隔。

**语法:**

*   它返回 animationDuration 属性。

    ```html
    object.style.animationDuration
    ```

*   它设置动画持续时间属性。

    ```html
    object.style.animationDuration = "time|initial|inherit"
    ```

**返回值:**它返回一个字符串，代表元素的动画持续时间属性

**属性值:**

*   **时间:**用于指定动画完成一个循环的时间长度。默认值为 0，即不显示动画。
*   **初始值:**用于将 style animationDuration 属性设置为默认值。
*   **继承:**它从其父级继承样式 animationDuration 属性。

**厂商前缀:**为了浏览器兼容性，许多 web 开发人员通过使用扩展来添加浏览器特定的属性，例如-webkit-用于 Safari、Google Chrome 和 Opera，-ms-用于 Internet Explorer，-moz-用于 Firefox，-o-用于 Opera 的旧版本等。如果浏览器不支持任何扩展，它会简单地忽略它。

**例 1:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            HTML DOM Style animationDuration Property
        </title>

        <style> 
            div {
                width: 100px;
                height: 100px;
                background:#32CD32;
                position: relative;

                /*For Chrome, Safari, Opera browsers */
                /* animation name geeks */
                /* infinite animation iteration */
                -webkit-animation: geeks 5s infinite;

                animation: geeks 5s infinite; 
            }

            /* Used for Chrome, Safari, Opera */
            @-webkit-keyframes geeks {
                from {
                    left: 0px;
                    top:20px;
                }
                to {
                    left: 300px;
                    top:20px;
                }
            }
            @keyframes geeks {
                from {
                    left: 0px;
                    top:20px;
                }
                to {
                    left: 300px;
                    top:20px;
                }
            }
        </style>
    </head>

    <body>
        <button onclick = "myGeeks()">
            Click the button to speed up the duration of animation
        </button>

        <script>
        function myGeeks() {

            /* For Chrome, Safari, and Opera browsers */
            document.getElementById("GFG").style.WebkitAnimationDuration = "1s";
            document.getElementById("GFG").style.animationDuration = "1s";
        }
        </script>

        <div id = "GFG">
            GeeksforGeeks
        </div>
    </body>
</html>                    
```

**输出:**

*   **之前点击按钮:**
    <video class="wp-video-shortcode" id="video-266771-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/CSS-animationduration-before.mp4?_=1">[https://media . geeksforgeeks . org/WP-content/uploads/CSS-animation duration-Before . MP4](https://media.geeksforgeeks.org/wp-content/uploads/CSS-animationduration-before.mp4)</video>
*   **点击按钮后:**
    <video class="wp-video-shortcode" id="video-266771-2" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/CSS-animationduration-after01.mp4?_=2">[https://media . geeksforgeeks . org/WP-content/uploads/CSS-animation duration-After 01 . MP4](https://media.geeksforgeeks.org/wp-content/uploads/CSS-animationduration-after01.mp4)</video>

**例 2:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>
        HTML DOM Style animationDuration Property
    </title>

    <style>
        div {
            width: 100px;
            height: 100px;
            background:#32CD32;
            position: relative;

            /* For Chrome, Safari, Opera */
            /* infinite animation iteration */
            -webkit-animation: mymove 5s infinite;

            animation: mymove 5s infinite; 
        }

        /* Chrome, Safari, Opera */
        @-webkit-keyframes mymove {
            from {
                left: 0px; 
                background-color: white;
            }
            to {
                left: 200px; 
                background-color: #32CD32;
            }
        }
        @keyframes myanim {
            from {
                left: 0px; 
                background-color: white;
            }
            to {
                left: 200px; 
                background-color: #32CD32;
            }
        }

    </style>
</head>

<body>

    <button onclick = "myGeeks()">
        Click the button to speed
        up the duration of animation
    </button>

    <script>
        function myGeeks() {
            document.getElementById("GFG").style.WebkitAnimationDuration 
                    = "1s"; 

            document.getElementById("GFG").style.animationDuration = "1s";
        }
    </script>

    <div id = "GFG">
        The animation-duration Property
    </div>

</body>
</html>                    
```

**输出:**

*   **之前点击按钮:**
    <video class="wp-video-shortcode" id="video-266771-3" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/CSS-animduration01-before_Trim.mp4?_=3">[https://media . geeksforgeks . org/WP-content/uploads/CSS-animcduration 01-Before _ trim . MP4](https://media.geeksforgeeks.org/wp-content/uploads/CSS-animduration01-before_Trim.mp4)</video>
*   **点击按钮后:**
    <video class="wp-video-shortcode" id="video-266771-4" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/CSS-animduration01-after_Trim.mp4?_=4">[https://media . geeksforgeeks . org/WP-content/uploads/CSS-animduration01-After _ trim . MP4](https://media.geeksforgeeks.org/wp-content/uploads/CSS-animduration01-after_Trim.mp4)</video>

**支持的浏览器:**下面列出了*风格动画时长属性*支持的浏览器:

*   火狐 16.0， 5.0 -moz-
*   Opera 30.0
*   谷歌 Chrome 43.0
*   Safari 9.0