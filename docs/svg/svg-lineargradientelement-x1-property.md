# SVG 线性梯度元素. x1 属性

> 原文:[https://www . geesforgeks . org/SVG-linear gradient element-x1-property/](https://www.geeksforgeeks.org/svg-lineargradientelement-x1-property/)

属性返回一个对应于给定线性渐变元素属性的对象

**语法:**

```html
LinearGradientElement.x1 
```

**返回值:**该属性返回一个可用于获取线性渐变元素 x1 的对象。

**例 1:**

```html
<!DOCTYPE html>
<html>

<body>
    <svg viewBox="0 0 200 200" 
         xmlns=
            "http://www.w3.org/2000/svg"
     xmlns:xlink="http://www.w3.org/1999/xlink">
  <defs>
    <linearGradient id="gfg" 
                    gradientTransform="rotate(70)" 
                    x1="20%" x2="0%" 
                    y1="20%" y2="0%">
      <stop offset="10%"  stop-color="blue" />
      <stop offset="90%" stop-color="green" />
    </linearGradient>
  </defs>

  <circle cx="20" cy="20" r="20" fill="url('#gfg')" />
      <script>
          var a=document.getElementById("gfg");
          console.log(a.x1);
      </script>
</svg>
</body>

</html>
```

**输出:**

![](img/6f7bd19276a804e4a9f2a73248a3c1cc.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<body>
    <svg viewBox="0 0 500 500" 
         xmlns="http://www.w3.org/2000/svg"
     xmlns:xlink="http://www.w3.org/1999/xlink">
  <defs>
    <linearGradient id="gfg" 
                    gradientTransform="rotate(70)" 
                    x1="20%" x2="0%" 
                    y1="20%" y2="0%">
      <stop offset="10%"  stop-color="blue" />
      <stop offset="90%" stop-color="green" />
    </linearGradient>
  </defs>

  <ellipse cx="100" cy="70" rx="80" 
           ry="50" fill="url('#gfg')" />
      <script>
          var a=document.getElementById("gfg");
          console.log(a.x1);
      </script>
</svg>
</body>

</html>
```

**输出:**

![](img/042915ece5fd98d798f82537cc8b0b35.png)

**例 3:**

```html
<!DOCTYPE html>
<html>

<body>
    <svg viewBox="0 0 500 500" 
         xmlns="http://www.w3.org/2000/svg"
     xmlns:xlink="http://www.w3.org/1999/xlink">
  <defs>
    <linearGradient id="gfg" 
                    gradientTransform="rotate(70)" 
                    x1="20%" x2="0%" 
                    y1="20%" y2="0%">
      <stop offset="10%"  stop-color="blue" />
      <stop offset="90%" stop-color="green" />
    </linearGradient>
  </defs>

  <rect height="80" width="80" x="30"
        y="30" fill="url('#gfg')" />
      <script>
          var a=document.getElementById("gfg");
          console.log(a.x1);
      </script>
</svg>
</body>

</html>
```

**输出:**

![](img/73bd529a3175e32425c6dcbf1d36e8c0.png)