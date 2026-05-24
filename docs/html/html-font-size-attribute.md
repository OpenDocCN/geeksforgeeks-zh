# HTML font 大小属性

> 原文:[https://www.geeksforgeeks.org/html-font-size-attribute/](https://www.geeksforgeeks.org/html-font-size-attribute/)

**示例:**此示例说明了*字体大小*属性的使用，该属性在 HTML 中的值范围为 1 到 7。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
    <title>HTML font size Attribute</title>
</head>

<body> 
    <font size="1">GeeksforGeeks!</font><br />
    <font size="2">GeeksforGeeks!</font><br />
    <font size="3">GeeksforGeeks!</font><br />
    <font size="4">GeeksforGeeks!</font><br />
    <font size="5">GeeksforGeeks!</font><br />
    <font size="6">GeeksforGeeks!</font><br />
    <font size="7">GeeksforGeeks!</font> 
</body>
</html>
```

**输出:**

![](img/2d7b6da2b801f0666523b02cce0a28f9.png)

**HTML <字体>大小属性**用于指定*存在于 *<字体>* 元素中的文本大小*。

**语法:**

```html
<font size="number">
```

**属性值:**它包含一个指定文本大小的单值**数字**。字体大小介于 1 到 7 之间。字体大小的默认值是 3。

**注意:**HTML 5 不支持<字体>大小属性。

**示例 1:** 该示例说明了在 HTML 中使用<字体>标签内的大小属性。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
    <title>HTML font size Attribute</title>
</head>

<body> 
    <font size="7" 
          face="verdana" 
          color="green">
            GeeksforGeeks!
    </font>
    <br>
    <hr> 
    <font size="6" 
          face="arial" 
          color="#008000">
            GeeksforGeeks!
    </font>
    <br>
    <hr> 
    <font size="5" 
          face="sans-serif" 
          color="rgb(128, 128, 0)">
            GeeksforGeeks!
    </font>
    <br>
    <hr> 
    <font size="4" 
          face="times new roman" 
          color="#008000">
            GeeksforGeeks!
    </font>
</body>
</html>
```

**输出:**

![](img/89ecbebfb6a0adcd781e0cfee0f0c7b0.png)

**示例 2:** 在本例中，我们使用了字体*大小*属性&将其设置为不同的值，以便显示类似于使用 HTML 标题&的段落。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<body> 
    <font size="6" 
          face="sans-serif" 
          color="green">
              GeeksforGeeks
    </font>
    <br>
      <hr>
    <font size="3" 
          face="Comic sans MS">
       Learn Data Structures Online At Your Own Pace With 
       The Best Of Faculty In The Industry. The Best 
       Data Structures Course Available Online From 
       Skilled And Experienced Faculty.
    </font> 
</body>
</html>
```

**输出:**

![](img/612e3b12fc302acc1a096e29f04169da.png)

**支持的浏览器:**

*   谷歌 Chrome 93.0
*   Internet Explorer 11.0
*   微软边缘 93.0
*   Firefox 92.0
*   Safari 14.1
*   Opera 79.0