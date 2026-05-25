# fabric.js easeInCubic()方法

> 原文: [https://www.geeksforgeeks.org/fabric-js-easeincubic-method/](https://www.geeksforgeeks.org/fabric-js-easeincubic-method/)

在游戏或动画中，有许多移动对象可以以线性方式将它们从 A 点移动到 B 点，但是在应用了缓动功能后，可以使其看起来更自然。一个缓动功能描述了动画如何进展。这样，直线运动可以呈现出有趣的形状。

**缓动函数**描述参数随时间的变化率。正是它的方程式使某物在开始时缓慢移动，在接近结束时加速或减速。参考罗伯特·彭纳的书和网页，了解缓动功能。

## easeInCubic()方法

该方法用于实现立方缓动。这个函数的曲线开始慢，结束快。

## 语法

```
easeInCubic(t, b, c, d)
```

## 参数

该方法接受上述四参数，描述如下:

*   `t`: 此参数保存动画开始的指定时间。例如，如果 `t` 的值为 0，则表示动画刚刚开始。
*   `b`: 此参数保存对象在 x 轴上的指定起始位置。例如，如果 `b` 的值为 10，则意味着对象在 x 坐标上的起始位置为 10。
*   `c`: 此参数保存对象的指定值变化。例如，如果 `c` 的值是 30，这意味着对象必须向右移动 30°，以 40°结束。
*   `d`: 此参数保存整个过程的指定持续时间。例如，如果 `d` 的值为 2，则意味着对象有 2 秒的时间来执行从 10 到 40 的这个运动。

## 返回值

该方法返回物体的缓动位置，即物体在特定时间的位置。

## 示例 1

### HTML

```html
<!DOCTYPE html>
<html>

<head>
  <!-- Adding the FabricJS library -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/fabric.js/3.6.2/fabric.min.js">
  </script>
</head>

<body>
<script type="text/javascript">

// Initializing easeInCubic() function
 function easeInCubic (t, b, c, d) {
    return c * (t /= d) * t * t + b;
}

// Calling the easeInCubic() function over
// the specified parameter values
console.log(fabric.util.ease.easeInCubic(1, 2, 3, 4)); 
</script>

</body>

</html>
```

### 输出

```
2.046875
```

## 示例 2

### HTML

```html
<!DOCTYPE html>
<html>

<head>
  <!-- Adding the FabricJS library -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/fabric.js/3.6.2/fabric.min.js">
  </script>
</head>

<body>
<script type="text/javascript">

// Initializing easeInCubic() function
 function easeInCubic (t, b, c, d) {
    return c * (t /= d) * t * t + b;
}

// Initializing the parameters with its values
var t = 5;
var b = 10;
var c = 40;
var d = 12;

// Calling the easeInCubic() function over
// the specified parameter values
console.log(fabric.util.ease.easeInCubic(t, b, c, d)); 
</script>

</body>

</html>
```

### 输出

```
12.893518518518519
```