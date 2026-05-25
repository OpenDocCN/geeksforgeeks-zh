# Node.js GM randomThreshold()函数

> 原文: [https://www.geeksforgeeks.org/node-js-gm-randomthreshold-function/](https://www.geeksforgeeks.org/node-js-gm-randomthreshold-function/)

`randomThreshold()`函数是 GraphicsMagick 库中的一个内置函数，用于对图像应用随机阈值。该函数在成功时返回真值。

## 语法

```js
randomThreshold( channelType, LOWxHIGH )
```

## 参数

该函数接受两个参数，如下所述：

*   `channelType`: 该参数用于将通道类型的值指定为`all`、`intensity`、`red`、`green`、`blue`、`cyan`、`magenta`、`yellow`、`black`和`opacity`。
*   `LOWxHIGH`: 此参数用于指定级别的值。阈值从不超过指定的最大值（高），也从不小于指定的最小值（低）。

## 返回值

该函数返回 GraphicsMagick 对象。

## 示例

### 例 1

```js
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Invoke randomThreshold function
// with Channel Type as 'All' and
// lowxhigh as '10x200'
.randomThreshold('All', '10x200')

// Process and Write the image
.write("randomThreshold1.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/b5c34375927dad125f6f8dd38b0a6820.png)

### 例 2

```js
// Include gm library
var gm = require('gm');

// Import the image
gm(600, 300, 'white')

// Set the color for the stroke
.stroke("green", 3)

// Set the font
.font("Helvetica.ttf", 60)

// Call to drawText Function
.drawText(100, 280, "GeeksforGeeks!")

// Invoke random Threshold function
// with Channel Type as 'Green' and
// lowxhigh as 100x600
.randomThreshold('Green', '100x600')

// Process and write the image
.write("randomThreshold2.png", function (err) {
  if (!err) console.log('done');
});
```

**输出:**
![](img/a4c7f44e85822cb94088aa1a20dedca2.png)

## 参考

*   [http://www.graphicsmagick.org/GraphicsMagick.html#details-randomThreshold](http://www.graphicsmagick.org/GraphicsMagick.html#details-randomThreshold)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)