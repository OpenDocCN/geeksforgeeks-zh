# 如何使用 CSS 创建自定义光标？

> 原文:[https://www . geesforgeks . org/how-create-custom-cursor-use-CSS/](https://www.geeksforgeeks.org/how-to-create-custom-cursor-using-css/)

自定义光标增强了文档的可读性，并将用户的注意力吸引到网页的特定部分。今天我们将学习如何使用 HTML、CSS 和 Javascript 为网页创建自定义光标。

**进场:**

*   隐藏默认光标。
*   定义包含所有动画的类。
*   当按下鼠标按钮或移动鼠标指针时，动态添加和移除这些类。

**例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        :root {
            --color: 255, 71, 84;
            --cursor-size: 30px;
        }

        * {
            cursor: none;
        }

        html,
        body {
            height: 100%;
        }

        body {
            margin: 0;
            overflow: hidden;

            background: #121212;
        }

        .custom-cursor {
            position: absolute;
            z-index: 99;
            top: 0;
            left: 0;

            width: var(--cursor-size);
            height: var(--cursor-size);

            border: calc(var(--cursor-size)
                        /30) solid #fff;
            border-radius: 50%;

            animation: cursor 800ms infinite
                    alternate ease-in-out;
        }

        .custom-cursor::before {
            content: "";
            display: block;
            width: calc(var(--cursor-size) / 2);
            height: calc(var(--cursor-size) / 2);

            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);

            border: calc(var(--cursor-size) / 6)
                    solid rgba(var(--color), 0.5);

            border-radius: 50%;

            animation: cursor-before 800ms infinite
                    alternate ease-in-out;
        }

        .custom-cursor.click {
            animation: cursor-click 800ms
                normal ease-in-out;
        }

        @keyframes cursor {
            from {
                transform: scale(1);
                border-color: #fff;
            }

            to {
                transform: scale(1.5);
                border-color: rgb(var(--color));
            }
        }

        @keyframes cursor-before {
            from {
                transform: translate(-50%, -50%) scale(1);
                border-color: rgba(var(--color), 0.5);
            }

            to {
                transform: translate(-50%, -50%) scale(1.5);
                border-color: rgba(var(--color), 0.75);
            }
        }

        @keyframes cursor-click {

            0%,
            100% {
                transform: scale(1);
            }

            50% {
                transform: scale(2.5);
                border-color: rgb(var(--color));
            }
        }
    </style>
</head>

<body>
    <div class="custom-cursor"></div>
</body>

</html>
```