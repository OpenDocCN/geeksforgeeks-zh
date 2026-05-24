# jQuery | slideUp()带示例

> 原文:[https://www.geeksforgeeks.org/jquery-slideup-with-examples/](https://www.geeksforgeeks.org/jquery-slideup-with-examples/)

**slideUp()** 是 jQuery 中的一个内置方法，用来隐藏选中的元素。
**语法:**

```html
$(selector).slideUp(speed);

```

**参数:**接受可选参数“速度”，指定效果持续时间的速度。

**返回值:**它不返回任何东西，只是隐藏所选元素。

<center>**jQuery 代码展示 slideUp()方法的工作方式:**</center>

**代码#1:**
在下面的代码中，没有参数传递给这个方法。

```html
<html>

<head>
    <script 
    src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
    <script>
        <!-- jQuery code to show the working of this method -->
        $(document).ready(function() {
            $(".btn1").click(function() {
                $("p").slideUp();
            });
        });
    </script>
    <style>
        div {
            width: 300px;
            height: 100px;
            padding: 20px;
            border: 2px solid green;
        }
    </style>
</head>

<body>
    <div>
        <p>This paragraph will get hide.</p>
        <!-- click on this button -->
        <button class="btn1">Slide up</button>
    </div>
</body>

</html>
```

**输出:**
在下面的视频中，已经展示了这种方法的工作原理。

<video class="wp-video-shortcode" id="video-228982-1" width="506" height="216" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20180921_234205.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20180921_234205.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20180921_234205.mp4)</video>

**代码#2:**
在下面的代码中，超速参数被传递给这个方法。

```html
<!DOCTYPE html>
<html>

<head>
    <script 
    src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
    <script>
        <!-- jQuery code to show the working of this method -->
        $(document).ready(function() {
            $(".btn1").click(function() {
                $("p").slideUp(3000);
            });
        });
    </script>
    <style>
        div {
            width: 300px;
            height: 100px;
            padding: 20px;
            border: 2px solid green;
        }
    </style>
</head>

<body>
    <div>
        <p>This paragraph will get hide.</p>
        <!-- click on this button -->
        <button class="btn1">Slide up</button>
    </div>
</body>

</html>
```

**输出:**
在下面的视频中，已经展示了这种方法的工作原理。

<video class="wp-video-shortcode" id="video-228982-2" width="364" height="206" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20180921_235252.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20180921_235252.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20180921_235252.mp4)</video>