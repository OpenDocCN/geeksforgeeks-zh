# HTML | DOM createAttribute()方法

> 原文:[https://www . geesforgeks . org/html-DOM-create attribute-method/](https://www.geeksforgeeks.org/html-dom-createattribute-method/)

这个 **createAttribute()** 方法用于创建一个指定名称的属性，并返回属性对象。attribute.value 属性用于设置属性的值，element.setAttribute()方法用于为元素创建新属性。此方法()包含创建的属性的名称作为参数值。

**语法:**

```html
document.createAttribute( attributename )
```

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>DOM createAttribute Method</title>
        <style>
            .gfg {
                color: green;
                font-weight:bold;
                font-size:50px;
            }
            body {
                text-align:center;
            }
        </style>
    </head>
    <body>
        <h1>GeeksforGeeks</h1>
        <h2>DOM createAttribute() Method</h2>
        <button onclick="geeks()">Submit</button>
        <script>
        function geeks() {
            var tag_name =
                document.getElementsByTagName("h1")[0];
            var attr = 
                document.createAttribute("class");
            attr.value = "gfg";
            tag_name.setAttributeNode(attr);
        }
        </script>
    </body>
</html>                    
```

**输出:**
![](img/eed3d7e7946d6e70e403d1bef58b0560.png)

**例 2:**

```html
<!DOCTYPE html>
<html>
    <head>
        <style>
            h1 {
                color:green;
            }
            body {
                text-align:center;
            }
        </style>
    </head>
    <body>
        <h1>GeeksforGeeks</h1>
        <h2>DOM createAttribute() Method</h2>
        <a id="gfg">Visit GeeksForGeeks...</a><br><br>
        <button onclick="geeks()">Submit</button>
        <script>
            function geeks() {
                var id= document.getElementById("gfg");
                var new_attr = document.createAttribute("href");
                new_attr.value = "#";
                id.setAttributeNode(new_attr);
            }
        </script>
    </body>
</html>                    
```

**输出:**
![](img/90a6bc3df84579d802d3323e9d6d0bf9.png)

**支持的浏览器:**下面列出了 *DOM createAttribute()方法*支持的浏览器:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队