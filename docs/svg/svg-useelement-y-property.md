# SVG UseElement.y Property

> 原文:[https://www.geeksforgeeks.org/svg-useelement-y-property/](https://www.geeksforgeeks.org/svg-useelement-y-property/)

**SVG UseElement.y 属性** 返回一个对应于给定 use 元素属性的 SVGAnimatedLength 对象。

**语法:**

```html
UseElement.y
```

**返回值:**这个属性返回 SVGAnimatedLength 对象，可以用来获取 use 元素的 y。

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html> 
<html> 

<body>
  <svg width="400" height="500"
        xmlns="http://www.w3.org/2000/svg">        
        <circle id="gfg" 
                cx="100" 
                cy="100" 
                r="70" 
                fill="green"/> 

        <use href="#gfg" x="110" y="320" id="useid"></use> 
        <script type="text/javascript">
          var u = document.getElementById("useid");
          console.log(u.y);
          console.log(u.y.animVal.value)
        </script>
    </svg> 
</body>
</html>
```

**输出:**

![](img/14b9dd661926f567bac89806bb17b5e9.png)

**例 2:**

## 超文本标记语言

```html
<!DOCTYPE html> 
<html> 

<body>
  <svg width="800" height="800"
        xmlns="http://www.w3.org/2000/svg">        
        <rect id="gfg" 
                x="100" 
                y="100" 
                height="150"
                width="150"
                fill="green"/> 

        <use href="#gfg" x="200" y="200" id="useid"></use> 
        <script type="text/javascript">
          var u = document.getElementById("useid");
          console.log(u.y);
          console.log(u.y.animVal.value)
        </script>
    </svg> 
</body>
</html>
```

**输出:**

![](img/c015a3ffb3e913e4beab21d52a05c8ae.png)