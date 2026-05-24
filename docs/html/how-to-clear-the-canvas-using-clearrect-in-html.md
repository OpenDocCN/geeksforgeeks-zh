# 如何在 HTML 中使用 clearRect 清除画布？

> 原文:[https://www . geeksforgeeks . org/如何使用 html 中的 clearrect 清除画布/](https://www.geeksforgeeks.org/how-to-clear-the-canvas-using-clearrect-in-html/)

画布 2D API 的 **clearRect()方法**，用于通过将像素颜色设置为**透明黑色(rgba(0，0，0，0))** 来擦除矩形区域中的像素。

**语法:**

```html
abc.clearRect(x, y, width, height);
```

**参数:**

*   **x，y:** 这些参数代表矩形框的左上角坐标。
*   **宽度:**用于设置矩形框的宽度
*   **高度:**用于设置矩形框的

**示例 1:** 在以下示例中，`clearRect()`方法用于从(50，20)中清除大小为(200×300)的矩形的像素。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>
        How to clear the canvas
        using clearRect in HTML?
    </title>
</head>

<body>
    <canvas id="canvas"></canvas>

    <script>
        const canvas = document.getElementById("canvas");
        const abc = canvas.getContext('2d');

        abc.beginPath();
        abc.fillStyle = "red";
        abc.fillRect(0, 0, 200, 300);

        abc.clearRect(50, 20, 100, 100);
    </script>
</body>

</html>
```

**输出:**
![](img/3cd7f42afba5998352edc1daa34c0dd6.png)

**例 2:**

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>
        How to clear the canvas
        using clearRect in HTML?
    </title>
</head>

<body>
    <canvas id="canvas"></canvas>

    <script>
        const canvas = document.getElementById("canvas");
        const abc = canvas.getContext('2d');

        // Draws a rectangle of 200x300
        abc.beginPath();
        abc.fillStyle = "red";
        abc.fillRect(0, 0, 200, 300);

        // Draws a traiangle
        abc.beginPath();
        abc.fillStyle = "green";
        abc.moveTo(10, 10);
        abc.lineTo(150, 10);
        abc.lineTo(120, 120);
        abc.closePath();
        abc.fill();

        abc.clearRect(40, 25, 100, 70);
    </script>
</body>

</html>
```

**输出:**
![](img/0742ca584e0bcdb9a37e29eb00274fb0.png)

**示例 3:** 在本例中，我们将**擦除整个画布。**

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>
        How to clear the canvas
        using clearRect in HTML?
    </title>
</head>

<body>
    <canvas id="canvas"></canvas>

    <script>
        const canvas = document.getElementById("canvas");
        const abc = canvas.getContext('2d');

        abc.beginPath();
        abc.fillStyle = "red";
        abc.fillRect(0, 0, 200, 300);

        // This line will erase whole canvas and
        // we will get an empty screen
        abc.clearRect(0, 0, canvas.width, canvas.height);
    </script>
</body>

</html>
```

**注意:**注意如果你没有正确使用路径`clearRect()`可能会导致意想不到的副作用。在调用`clearRect()`之后开始绘制新项目之前，一定要调用 [beginPath()](https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/beginPath) 。

**参考:**T2】https://www.geeksforgeeks.org/html-canvas-clearrect-method/