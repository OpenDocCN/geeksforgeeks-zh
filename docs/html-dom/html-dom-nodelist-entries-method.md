# HTML DOM NodeList.entries()方法

> 原文:[https://www . geesforgeks . org/html-DOM-nodelist-entries-method/](https://www.geeksforgeeks.org/html-dom-nodelist-entries-method/)

**NodeList entries()** 方法返回一个迭代器，允许您遍历 NodeList 对象中包含的所有键/值对。这些值是节点对象。

**语法:**

```html
NodeList.entries();
```

**参数:**该方法不取参数。

**返回值:**这个方法返回一个迭代器。

**示例:**在本例中，我们将创建一个节点列表，因此将获得一个迭代器来获取节点列表中的所有值。

```html
<!DOCTYPE HTML> 
<html>  
<head>
    <meta charset="UTF-8">
    <title>NodeList.entries() method</title>
</head>   

<body style="text-align:center;">
    <h1 style="color:green;">  
     GeeksforGeeks
    </h1> 
    <p> 
    HTML |DOM NodeList.entries() method
    </p>

    <button onclick = "Geeks()">
    Click Here
    </button>
    <p id="a"></p>
    <script> 
        var a = document.getElementById("a");
        a.innerHTML = "elements are : "
        function Geeks(){
            var parentNode = document.createElement("div"); 
            var c1 = document.createElement("p"); 
            var c2 = document.createElement("span"); 
            var c3 = document.createElement("h1"); 
            parentNode.appendChild(c1); 
            parentNode.appendChild(c2); 
            parentNode.appendChild(c3); 
            var nodelist = parentNode.childNodes;
            for(var e of nodelist.entries()) { 
                a.innerHTML += "<li>"+e[1].localName + `</li>`;
                console.log(e);
            }
}
</script>
</body>   
</html>
```

**输出:**

**点击按钮前:**

![](img/03c4f2161341354693f13024526bbbc1.png)

**点击按钮后:**使用迭代器调用元素。

![](img/c2fbd1a4c6aa41026ff1544e291c575d.png)

**在控制台:**可以看到迭代器条目。

![](img/2c6a4f63e72c554b2811608290fcd63f.png)

**支持的浏览器:**

*   谷歌 Chrome
*   边缘
*   火狐浏览器
*   旅行队
*   歌剧