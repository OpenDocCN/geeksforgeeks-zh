# Fabric.js ActiveSelection complexity() 方法

> 原文：[https://www.geeksforgeeks.org/fabric-js-activeselection-complexity-method/](https://www.geeksforgeeks.org/fabric-js-activeselection-complexity-method/)

在本文中，我们将看到如何使用 `complexity()` 方法在画布中使用 `ActiveSelection`。`ActiveSelection` 意味着它是可移动的，并且可以根据需要拉伸。此外，当涉及到初始笔画颜色、高度、宽度、填充颜色或笔画宽度时，可以自定义动态选择。

`complexity()` 方法用于获取对象的复杂度。

## 方法

首先导入 `fabric.js` 库。导入库后，在 `body` 标签中创建一个包含动态选择的画布块。之后，初始化一个由 Fabric.js 提供的 `Canvas` 和 `ActiveSelection` 类的实例，并使用 `complexity()` 方法。

## 语法

```
ActiveSelection.complexity()
```

## 参数

该函数不接受任何参数。

## 返回值

该方法返回包含对象复杂度的数值。

## 示例

本示例使用 FabricJS 设置画布 `ActiveSelection` 的 `complexity()` 方法，如下例所示。

### HTML

```html
<!DOCTYPE html> 
<html>

<head>
    <!-- FabricJS CDN -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/fabric.js/3.6.2/fabric.min.js"> 
    </script> 
  </head>

<body> 
    <div style="text-align: center;width: 400px;"> 
      <h1 style="color: green;"> 
        GeeksforGeeks 
      </h1>
      <b> 
        Fabric.js | ActiveSelection complexity() method 
      </b>
    </div>

    <div style="text-align: center;"> 
      <canvas id="canvas" width="500" height="500"
              style="border:1px solid green;"> 
      </canvas> 
    </div> 
    <img src="https://media.geeksforgeeks.org/wp-content/uploads/20200327230544/g4gicon.png"
         width="100" height="100" id="my-image"
         style="display: none;">
    <script> 
      var canvas = new fabric.Canvas("canvas");

      // Getting the image 
      var img = document.getElementById('my-image');

      // Creating the image instance 
      var geek = new fabric.Image(img, {
      });

      canvas.add(geek);

      var geek = new fabric.IText('GeeksforGeeks', {
      });
      canvas.add(geek);
      canvas.centerObject(geek);

      var gfg = new fabric.ActiveSelection(canvas.getObjects(), {
      });
      canvas.setActiveObject(gfg);
      canvas.requestRenderAll();
      canvas.centerObject(gfg);
      console.log(gfg.complexity())
    </script> 
  </body>

</html>
```

## 输出

![](img/f53d0288ecb7bdd91e9eb372ff067b56.png)

## 参考

[http://fabricjs.com/docs/fabric.ActiveSelection.html#complexity](http://fabricjs.com/docs/fabric.ActiveSelection.html#complexity)