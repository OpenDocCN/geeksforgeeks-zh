# Node.js GM `charcoal()` Function

> 原文: [https://www.geeksforgeeks.org/node-js-gm-charcoal-function/](https://www.geeksforgeeks.org/node-js-gm-charcoal-function/)

The `charcoal()` function is a built-in function in the GraphicsMagick library used to add a charcoal filter to an image. It returns a truthy value on success.

## Syntax

```js
charcoal( factor )
```

## Parameters

This function accepts a single parameter as mentioned above and described below:

*   `factor`: This parameter stores the value of the charcoal factor to be applied to the image.

## Return Value

This function returns a Gmagick charcoal image.

## Original Image

![](img/3a7f2a0c7a1b7410f45c9428c4fda2ad.png)

## Example 1

```js
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Invoke Charcoal function
// with charcoal factor as 12
.charcoal(4)

// Process and Write the image
.write("charcoal1.png", function (err) {
    if (!err) console.log('done');
});
```

**Output:**
![](img/ca5731090d2bc14f2cbd83fd5b04b8a2.png)

## Example 2

```js
// Include gm library
var gm = require('gm');

// Import the image
gm('1.png')

// Set stroke color
.stroke("#fe1232")

// Set fill color
.fill("#1200ff")

// Draw Rectangle using drawRectangle function
.drawRectangle(10, 2, 130, 30, 1, 2)

//Invoke Charcoal function as factor 3
.charcoal(3)

// Process and Write the image
.write("charcoal2.png", function (err) {
  if (!err) console.log('done');
});
```

**Output:**
![](img/7c880310f4cb457ed42aa74a7fae40eb.png)

## References

*   [http://www.graphicsmagick.org/GraphicsMagick.html#details-charcoal](http://www.graphicsmagick.org/GraphicsMagick.html#details-charcoal)
*   [https://www.npmjs.com/package/gm](https://www.npmjs.com/package/gm)