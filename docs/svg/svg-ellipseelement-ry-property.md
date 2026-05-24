# SVG 椭球体。ry property

> 原文:[https://www . geesforgeks . org/SVG-ellipselement-ry-property/](https://www.geeksforgeeks.org/svg-ellipseelement-ry-property/)

**SVG ellipselement . ry 属性**返回对应于给定椭圆元素属性的 SVGAnimatedLength 对象

**语法:**

```html
EllipseElement.ry
```

**返回值:**该属性返回可用于获取椭圆元素的长度的 SVGAnimatedLength 对象

**例 1:**

```html
<!DOCTYPE html>
<html>

<body>
    <svg width="300" height="300" xmlns="http://www.w3.org/2000/svg">
  <ellipse cx="100" cy="100" rx="100" ry="60" id="ellipse"
      onclick="outputSize();"/>
          <script>
              var g = document.getElementById("ellipse");
              console.log(g.ry)
          </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/68eefbf381773edd04b7d6a4f586ba3d.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<body>
    <svg width="300" height="300" xmlns="http://www.w3.org/2000/svg">
  <ellipse cx="100" cy="100" rx="100" ry="100" id="ellipse"
      onclick="outputSize();"/>
          <script>
              var g = document.getElementById("ellipse");
              console.log(g.ry)
          </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/29af569a00bc9ecc64eb68ae0445c0c6.png)