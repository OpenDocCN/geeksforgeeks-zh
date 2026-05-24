# 如何在 Twitter Bootstrap 中隐藏小设备上的元素？

> 原文: [https://www.geeksforgeeks.org/how-to-hide-element-on-small-devices-in-twitter-bootstrap/](https://www.geeksforgeeks.org/how-to-hide-element-on-small-devices-in-twitter-bootstrap/)

Twitter Bootstrap 广泛使用特定类来实现所有各种各样的功能。

*   要隐藏任意屏幕尺寸上的元素，您可以使用特定的引导程序`.d-none`类。
*   对于小的屏幕尺寸，可以修改使用`.d-sm-none`类。
*   对于超小屏幕尺寸，可以修改使用`.d-none`或`.d-xs-none`。
*   对于中屏幕设备，可以修改为使用`.d-md-none`。

## 基本方法

假设我们想要隐藏一个特定的`div`。我们所需要做的就是根据我们的需求将那个`div`应用到我们需要的特定类。上面列出了类名。

```html
<div class="d-sm-none">hide on small screens</div>
<div class="d-xs-none">hide on extra small screens</div>
<div class="d-md-none">hide on medium screens</div>
```

## 高效方法

假设我们想要隐藏小设备屏幕上的按钮“点击这里”。

*   只需瞄准所需元素。
*   应用类别`d-sm-none`。
*   为了可视化，下面描述了两个实例——在应用类名之前和应用类名之后。
*   在我们已经应用了类名之前，我们可以看到按钮清晰可见。
*   我们一应用类名，按钮就从小屏幕设备上消失了。

## 示例

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            Hide elements in Small devices
        </title>
        <!-- Include bootstrap CDN CSS file-->
        <link rel="stylesheet" 
              href="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css"
              integrity="sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh" 
              crossorigin="anonymous" />
        <!-- Style to create button -->
        <style>
            .GFG {
                background-color: white;
                border: 2px solid black;
                color: green;
                padding: 5px 10px;
                text-align: center;
                display: inline-block;
                font-size: 20px;
                margin: 10px 30px;
                cursor: pointer;
            }
        </style>
    </head>

<body>
        <h1>GeeksforGeeks</h1>

<!-- Adding link to the button on 
             the onclick event -->
        <!-- Notice the .d-sm-none class that 
             hides the button on small devices-->
        <button class="GFG d-sm-none"
                onclick="window.location.href = 'https://ide.geeksforgeeks.org';">
            Click Here
        </button>
    </body>
</html>
```

## 输出（移动设备）

在应用`.d-sm-none`类之前：

![](img/f23e174ac6d3cac2ddd8dcac0b6652e7.png)

在应用`.d-sm-none`类之后：

![](img/44989166e695f3ce93277d7b05a656e2.png)