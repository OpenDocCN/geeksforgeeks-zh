# 在 JavaScript 中具有特定类的最近祖先元素

> 原文: [https://www.geeksforgeeks.org/closest-ancestor-element-that-has-a-specific-class-in-javascript/](https://www.geeksforgeeks.org/closest-ancestor-element-that-has-a-specific-class-in-javascript/)

任务是在纯 Javascript 的帮助下找到特定类的元素的最近祖先。下面讨论两种方法。

## 方法 1

使用 JavaScript 选择器选择元素。使用 `closest()` 方法获取特定类的最接近父类。

**示例:** 该示例实现了上述方法。

### 超文本标记语言

```html
<!DOCTYPE HTML>  
<html>  
    <head> 
        <title> 
            Find closest ancestor element that has a 
            specific class using pure JavaScript
        </title>        
    </head>
    <body style = "text-align:center;">  
        <h1 style = "color:green;" >  
            GeeksforGeeks  
        </h1>
        <p id = "GFG_UP">
        </p>

<div name = "parentDIV" class="parent">
          <div class="child">
          </div>
        </div>
        <button onclick = "myGFG()">
        click here
        </button>
        <p id = "GFG_DOWN">
        </p>

<script>     
            var up = document.getElementById("GFG_UP"); 
            up.innerHTML = "Click on button to see result";
            var down = document.getElementById("GFG_DOWN"); 
            function myGFG() {  
                var el = document.querySelector("div")
                .closest(".parent")
                down.innerHTML = "Element of name '"
                  + el.getAttribute("name") 
                  + "' is the parent element of specific class."; 
            } 
        </script> 
    </body>  
</html>
```

**输出:**

![](img/54a4bcd0e147a15e1bbe90c0224967f7.png)

## 方法 2

继续向元素的父元素移动，直到找到具体的类。使用 `element.className.indexOf()` 方法选择特定类的元素。

**示例:** 该示例实现了上述方法。

### 超文本标记语言

```html
<!DOCTYPE HTML>  
<html>  
    <head> 
        <title> 
            Find closest ancestor element that has a 
            specific class using pure JavaScript
        </title>        
    </head>
    <body style = "text-align:center;">  
        <h1 style = "color:green;" >  
            GeeksforGeeks  
        </h1>
        <p id = "GFG_UP">
        </p>

<div name = "parentDIV" class="parent">
          <div class="child">
          </div>
        </div>
        <button onclick = "myGFG()">
        click here
        </button>
        <p id = "GFG_DOWN">
        </p>

<script>     
            var up = document.getElementById("GFG_UP"); 
            up.innerHTML = "Click on button to see result";
            var down = document.getElementById("GFG_DOWN");
            function findParent(el, clas) {
                while ((el = el.parentNode) && 
                       el.className.indexOf(clas) < 0);
                return el;
            }
            function myGFG() {  
                var el = document.querySelector(".child");
                var el = findParent(el, 'parent');
                down.innerHTML = "Element of name '" 
                  + el.getAttribute("name") 
                  + "' is the parent element of specific class."; 
            } 
        </script> 
    </body>  
</html>
```

**输出:**

![](img/54a4bcd0e147a15e1bbe90c0224967f7.png)