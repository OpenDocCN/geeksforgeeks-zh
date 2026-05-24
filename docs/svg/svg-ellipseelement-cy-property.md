# SVG 椭球体。cy property

> 原文:[https://www . geesforgeks . org/SVG-ellipselement-cy-property/](https://www.geeksforgeeks.org/svg-ellipseelement-cy-property/)

属性返回一个对应于给定椭圆元素属性的对象

**语法:**

```html
EllipseElement.cy
```

**返回值:**该属性返回可用于获取椭圆元素 cy 的 SVGAnimatedLength 对象

**例 1:**

```html
<!DOCTYPE html>
<html>

<body>
    <svg width="300" height="200" xmlns="http://www.w3.org/2000/svg">
  <ellipse cx="100" cy="100" rx="100" ry="60" id="ellipse"
      onclick="outputSize();"/>
          <script>
              var g = document.getElementById("ellipse");
              console.log(g.cy)
          </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/452f7533938ca4adf998bf09da5e8fea.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<body>
    <svg width="300" height="200" xmlns="http://www.w3.org/2000/svg">
  <ellipse cx="100" cy="150" rx="100" ry="60" id="ellipse"
      onclick="outputSize();"/>
          <script>
              var g = document.getElementById("ellipse");
              console.log(g.cy)
          </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/dbf07db877d98ca7568c36ffb1a9a273.png)