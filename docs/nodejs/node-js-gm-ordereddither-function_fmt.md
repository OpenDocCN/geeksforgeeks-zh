# Node.js GM orderedDither() 函数

> 原文: [https://www.geeksforgeeks.org/node-js-gm-ordereddither-function/](https://www.geeksforgeeks.org/node-js-gm-ordereddither-function/)

`orderedDither()` 函数是 GraphicsMagick 库中的一个内置函数，用于对图像进行有序抖动。有序抖动方法用于将 `channel` 或 `channeltype` 参数缩减为二进制。通道类型的值为 `"all"`、`"intensity"`、`"red"`、`"green"`、`"blue"`、`"cyan"`、`"magenta"`、`"yellow"`、`"black"` 和 `"opacity"`。该函数在成功时返回真值。

## 语法

```js
orderedDither( ChannelType, NxN )
```

## 参数

该函数接受两个参数，如上所述，如下所述：

*   `ChannelType`: 此参数用于将通道类型指定为 `"all"`、`"intensity"`、`"red"`、`"green"`、`"blue"`、`"cyan"`、`"magenta"`、`"yellow"`、`"black"` 和 `"opacity"`。
*   `NxN`: 此参数用于指定强度的最小和最大水平。

## 返回值

该函数返回 GraphicsMagick 对象。

## 例 1

```js
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Invoke ordered Dither on Green
// Channel with 50 x 60
.orderedDither('Green', '50x60')

// Process and Write the image
.write("orderedDither1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/e0db284c0cfccb08842037cb6cf6f060.png)

## 例 2

```js
// Include gm library
var gm = require('gm');

//Import the image
gm(600, 300, 'white')

// set the color for the stroke
.stroke("green", 3)

// Set the font 
.font("Helvetica.ttf", 60)

//Call to drawText Function
.drawText(100, 280, "GeeksforGeeks!")

// Invoke ordered Dither with 'All'
// Channel with 110 x 110
.orderedDither('All', '110x110')

// Process and write the image 
.write("ordereddither2.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/1747a88653803d6e89cdc81f6715487b.png)

## 参考

*   [http://www.graphicsmagick.org/GraphicsMagick.html#details-ordered-dither](http://www.graphicsmagick.org/GraphicsMagick.html#details-ordered-dither)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)