# HTML5 游戏开发|无限滚动背景

> 原文:[https://www . geesforgeks . org/html 5-游戏-开发-无限-滚动-后台/](https://www.geeksforgeeks.org/html5-game-development-infinitely-scrolling-background/)

游戏设计与开发是一个新兴行业。虽然制作 AAA 标题需要游戏引擎、DirectX、OpenGL 等高级知识。小型 HTML5 视频游戏项目是一个不错的入手点。

HTML5 画布和 javascript 可以用来制作小游戏，同时学习游戏开发的基础知识，如碰撞检测、对象池等。

**无限滚动背景**

一个无限滚动的背景是一个重要的工具，这是必不可少的，当制作无休止的街机游戏，如 flappy bird 或在一个普通的平台，你没有时间或资源手工制作整个水平。

这个想法是连续绘制两次相同的图像，当第二个图像占据整个屏幕时，用第一个图像替换第二个图像，从而有效地重新开始这个过程。

**绘制图像**

图像应该是这样的，即两个图像的部分中间帧是适当的背景，分隔线不应该是可见的。同样的逻辑可以应用于创建无限侧滚动背景。
这里我们将以这张空间背景图为例:

```html

 spacebg.png

```

它是用 MS 油漆制成的。可以使用任何其他软件，如 Photoshop 或 Gimp。

**写代码**

**HTML:**

```html
<!DOCTYPE html> 
<html> 
<head> 
    <title>Infinitely Scrolling Background</title> 
</head> 
<body style="background-color: black;"> 
   <canvas id="canvas1" style="border: 1px solid black;"></canvas> 
</body> 
</html> 

<script src="main_javascript.js"></script> 
```

**JavaScript:**

```html
// inside main_javascript.js

var can = document.getElementById('canvas1');

// The 2D Context for the HTML canvas element. It
// provides objects, methods, and properties to draw and
// manipulate graphics on a canvas drawing surface.
var ctx = can.getContext('2d');

// canvas width and height
can.width = 600;
can.height = 600;

// create an image element
var img = new Image();

// specify the image source relative to the html or js file
// when the image is in the same directory as the file
// only the file name is required:
img.src = "spacebg.png";

// window.onload is an event that occurs when all the assets
// have been successfully loaded( in this case only the spacebg.png)
window.onload = function() {
    // the initial image height
    var imgHeight = 0;

    // the scroll speed
    // an important thing to ensure here is that can.height
    // is divisible by scrollSpeed
    var scrollSpeed = 10;

    // this is the primary animation loop that is called 60 times
    // per second
    function loop()
    {
        // draw image 1
        ctx.drawImage(img, 0, imgHeight);

        // draw image 2
        ctx.drawImage(img, 0, imgHeight - can.height);

        // update image height
        imgHeight += scrollSpeed;

        // reseting the images when the first image entirely exits the screen
        if (imgHeight == can.height)
            imgHeight = 0;

        // this function creates a 60fps animation by scheduling a
        // loop function call before the
        // next redraw every time it is called
        window.requestAnimationFrame(loop);
    }

    // this initiates the animation by calling the loop function
    // for the first time
    loop();

}
```

**方法和事件**

1.  **getContext(‘2d’) :** The HTML5 *canvas* tag is used to draw graphics via scripting (usually JavaScript).
    However, the *canvas* element has no drawing abilities of its own (it is only a container for graphics) – you must use a script to actually draw the graphics.
    The *getContext()* method returns an object that provides methods and properties for drawing on the canvas.
    **Syntax:**

    ```html
    var ctx = document.getElementbyId("canvasid").getContext('2d');
    ```

    对象可以用来在画布上绘制文本、线条、方框、圆圈等等。

2.  **window.onload :** The *onload* event occurs when an object has been loaded. It is commonly used in javascript to trigger a function once an asset has been loaded.
    **Syntax:**

    ```html
    object.onload = function() { /*myScript*/ };
    ```

    ***window.onload*** 具体发生在所有资产成功加载时，因此游戏的大部分 javascript 动画和渲染代码通常完全编写在由 *window.onload* 触发的函数中，以避免在加载图像之前调用 *drawImage()* 函数等问题。
    (尝试使用较重的图像并在*窗口外调用 *drawImage()* 函数. onload = function(){ 0..}* )

    它还可以用来检查访问者的浏览器类型和浏览器版本，并根据信息加载网页的正确版本。

3.  **window.requestAnimationFrame() :** The ***window.requestAnimationFrame()*** method tells the browser that you wish to perform an animation and requests that the browser call a specified function to update an animation before the next repaint. The method takes a callback as an argument to be invoked before the repaint.
    You should call this method whenever you’re ready to update your animation onscreen. This will request that your animation function be called before the browser performs the next repaint. The number of callbacks is usually 60 times per second, but will generally match the display refresh rate in most web browsers as per W3C recommendation.
    **Syntax:**

    ```html
    window.requestAnimationFrame(callback_function);
    ```

    callback _ funtion 被传递了一个参数，一个 DOMHighResTimeStamp，它指示了 requestAnimationFrame()排队的回调开始触发的当前时间。

**注意:**如果你想在下一次重画时激活另一帧，你的回调例程本身必须调用 requestAnimationFrame()。

**最终动画**
当打开 html 文件时，最终画布动画应该是这样的:

```html

<video class="wp-video-shortcode" id="video-199280-1" width="665" height="375" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/2018-05-14-12-03-12.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/2018-05-14-12-03-12.mp4](https://media.geeksforgeeks.org/wp-content/uploads/2018-05-14-12-03-12.mp4)</video>

```