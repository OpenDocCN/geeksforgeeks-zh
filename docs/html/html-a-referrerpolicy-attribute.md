# HTML a 参考策略属性

> 原文:[https://www . geesforgeks . org/html-a-referer policy-attribute/](https://www.geeksforgeeks.org/html-a-referrerpolicy-attribute/)

**HTML<a>referer policy 属性**用于指定当用户单击超链接时将发送到服务器的参考信息。

**语法:**

```html
<a referrerpolicy="no-referrer|no-referrer-when-downgrade|origin|
         origin-when-cross-origin|same-origin|
         strict-origin-when-cross-origin|unsafe-url"> 
```

**属性值:**

*   **无引用者:**指定不会随请求发送引用信息。
*   **降级时无推荐人**:有默认值。它指定该引用头将不会发送到没有 HTTPS 的源。
*   **来源:**指定在所有情况下只发送文档的来源作为推荐人。
*   **原点-当-跨原点**:执行同原点请求时发送原点、路径、查询字符串，其他情况只发送单据的原点。
*   **同源:**指定将为同站点源发送推荐人，但跨源请求将不发送推荐人信息。
*   **严格起源时跨起源**:执行同起源请求时发送起源、路径、查询字符串，执行跨起源请求时仅在协议安全级别不变时发送起源(HTTPS/HTTPS)，不发送报头到任何不太安全的目的地(HTTPS/HTTP)。
*   **unsafe-url:** 它发送一个源、路径和查询字符串作为一条参考信息，但不包括密码和用户名。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>HTML a referrerpolicy Attribute</title>
</head>

<body> 
   <h2>
    GeeksForGeeks
   </h2>
  <h2>
      HTML Anchor referrerpolicy Attribute
  </h2>
    <p>Welcome to
        <a rel="noopener"
           href="https://ide.geeksforgeeks.org/"
           referrerpolicy="no-referrer">
            GeeksforGeeks
        </a>
     </p>

</body>

</html>                    
```

**输出:**

![](img/236ec1c1e6cd30ad41b08f3b355a894d.png)

**支持的浏览器:**

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧