# HTML DOM NodeList.keys()方法

> 原文:[https://www . geesforgeks . org/html-DOM-nodelist-keys-method/](https://www.geeksforgeeks.org/html-dom-nodelist-keys-method/)

**NodeList keys()** 方法返回一个迭代器，允许您遍历该对象中包含的所有键。密钥是无符号整数。

**语法:**

```html
NodeList.keys();
```

**参数:**该方法不取参数。

**返回值:**这个方法返回一个迭代器。

**示例:**在这个示例中，我们将创建一个节点列表，因此将获得一个迭代器来使用这个方法从节点列表中获取所有键。

```html
<!DOCTYPE HTML> 
<html>  
<head>
    <meta charset="UTF-8">
    <title>HTML | DOM NodeList.keys() Method</title>
</head>   

<body style="text-align:center;">
    <h1 style="color:green;">  
     GeeksforGeeks
    </h1> 
    <p> 
HTML | DOM NodeList.keys() Method
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

            for(var key of nodelist.keys()) { 
               console.log(key); 
 a.innerHTML += "<li>"+nodelist[key].localName + `</li>`;
            }
            console.log(nodelist.keys())
        }
</script>
</body>   
</html>
```

**输出:**

**点击按钮前:**

![](img/853b43975bf2a52348bb4991d7cd5ebb.png)

**点击按钮后:**使用键迭代器调用元素。

![](img/40af91d444daed754ca801bc596e5489.png)

**在控制台:**可以看到迭代器键。

![](img/0c2cfd33bf54bb6076723eafe20954f7.png)

**支持的浏览器:**

*   谷歌 Chrome
*   边缘
*   火狐浏览器
*   旅行队
*   歌剧