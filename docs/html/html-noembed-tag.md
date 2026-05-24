# HTML | noembed 标签

> 原文:[https://www.geeksforgeeks.org/html-noembed-tag/](https://www.geeksforgeeks.org/html-noembed-tag/)

**< noembed >** 标签用于表示**不支持浏览器< embed >** 标签。这个 **<无嵌入>** 标签会告知用户在用户浏览器中缺少什么。

**语法:**

```html
<noembed> Element </noembed>
```

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>embed Tag</title>
    <style>
        q {
            color: #00cc00;
            font-style: italic;
        }
    </style>
</head>

<body>
    <center>
        <br>
        <embed src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190825000042/geeks-221.png">
        <noembed>
          <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190821123122/gfgsm.png" 
               alt="Alternative Media">
      </noembed>
        </embed>
    </center>
</body>

</html>
```

**输出:**

*   **<支持的 IF 浏览器嵌入>** :
    ![](img/407a1f00c04c81c69d0315e5dd88d7be.png)
*   如果 **<不支持浏览器嵌入>** ，则 **<不嵌入>** 激活:
    ![](img/23c8523da541ebb40cc57712107a6366.png)

**支持的浏览器**:不嵌入> 标签的 **<支持的浏览器如下:**

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧