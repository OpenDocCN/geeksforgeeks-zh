# HTML DOM `createDocument()` 方法

> 原文：[https://www.geeksforgeeks.org/html-dom-createdocument-method/](https://www.geeksforgeeks.org/html-dom-createdocument-method/)

## 方法实现

`createDocument()` 方法用于创建并返回一个文档。

## 语法

```javascript
var doc = document.implementation.createDocument(namespaceURI, qualifiedNameStr, docType);
```

## 参数

*   `namespaceURI`：一个包含要创建的文档的命名空间 URI 的 `DOMString`，如果文档不属于某个命名空间，则为 `null`。
*   `qualifiedNameStr`：一个包含限定名的 `DOMString`。
*   `docType`（可选）：要创建的文档的文档类型，默认值为 `null`。

## 返回值

该函数成功时返回一个文档对象。

## 示例

在本例中，我们将使用此方法创建文档。

```html
<!DOCTYPE HTML> 
<html>  
<head>
    <meta charset="UTF-8">
    <title>createDocument() method</title>
</head>

<body style="text-align:center;">
    <h1 style="color:green;">  
     GeeksforGeeks
    </h1> 
    <p id="a"> 
    HTML | DOM createDocument() method
    </p>

<button onclick = "Geeks()">
    Click Here
    </button>
    <script> 
        function Geeks(){
            var doc = document.implementation.createDocument (
'http://www.w3.org/1999/xhtml', 'html', null);
            var head = document.createElementNS(
'http://www.w3.org/1999/xhtml', 'head');
            head.setAttribute('id', 'headDoc');
            doc.documentElement.appendChild(head);
            var body = document.createElementNS(
'http://www.w3.org/1999/xhtml', 'body');
            body.setAttribute('id', 'bodyDoc');
            doc.documentElement.appendChild(body);
            console.log(doc)
        }
  </script> 
</body>   
</html>
```

## 输出

**按钮点击前：**

![](img/2490804fd403b3aa6492b1cec6967a4c.png)

**按钮点击后：**

![](img/0574ef025fd4659ffcbbb3313aca39bd.png)

## 支持的浏览器

*   Google Chrome
*   Edge
*   Firefox
*   Safari
*   Opera
*   Internet Explorer