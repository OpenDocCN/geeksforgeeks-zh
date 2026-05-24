# HTML href 属性

> 原文:[https://www.geeksforgeeks.org/html-href-attribute/](https://www.geeksforgeeks.org/html-href-attribute/)

**示例:**在本例中，我们只需通过单击文本重定向到 geeksforgeeks 页面。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
  <head>
    <title>HTML href attribute</title>
  </head>
  <body>
    <h1>
      <a href="https://www.geeksforgeeks.org/">
       GeeksforGeeks
      </a>
    </h1>
    <strong>HTML href Attribute</strong>
  </body>
</html>
```

**Output:**
![](img/dde2180fe3aed0d96a0d6140e8b1a027.png)

**HTML href 属性:**用于指定文档的 URL。它包含用户请求的页面的完整地址。它用于将一个文档链接或连接到另一个文档。

**支持的标签:**

*   [**HTML < a > href 属性**T3】](https://www.geeksforgeeks.org/html-a-tag/)
*   [**HTML <基础> href 属性**T3】](https://www.geeksforgeeks.org/html-base-href-attribute/)
*   [**HTML <区> href 属性**](https://www.geeksforgeeks.org/html-area-href-attribute/)
*   [**HTML <链接> href 属性**](https://www.geeksforgeeks.org/html-link-href-attribute/)

[**HTML < a > href 属性**](https://www.geeksforgeeks.org/html-a-tag/) **:** 用于指定链接所到页面的 URL。当< a >中不存在 *href* 属性时，则该元素不是超链接。

**语法:**

```html
<a href="URL">
```

**示例:**下面的代码说明了< a >元素中的 *href* 属性。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
  <head>
    <title>HTML href attribute</title>
  </head>
  <body>
    <h1>GeeksforGeeks</h1>
    <h2>HTML a href Attribute</h2>
    <a href="https://ide.geeksforgeeks.org/">
      Click to open in the same tab
    </a>
    <br />
    <a href="https://ide.geeksforgeeks.org/" 
       target="_blank">
      Click to open in a different tab
    </a>
  </body>
</html>
```

**输出:**

![](img/940adce83f3f8cb2b41cdadc08bcc190.png)

[**HTML < base > href 属性:**](https://www.geeksforgeeks.org/html-base-href-attribute/)**HTML<base>href 属性用于为一个页面的所有相对 URL 指定基本 URL。**

****语法:****

```html
<base href="URL">
```

****示例:**下面的代码说明了<基地>标签中的 *href* 。**

## **超文本标记语言**

```html
<!DOCTYPE html>
<html>
  <head>
    <title>HTML href Attribute</title>

    <!-- Declaring the base URL -->
    <base href="geeksforgeeks.org" 
          target="_blank" />
  </head>
  <h2>GeeksforGeeks</h2>
  <h3>HTML base href Attribute</h3>

  <body>
    <img 
       src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20210908192254/logo2.png"
       width="200"
       height="200" />
  </body>
</html>
```

****输出:****

**![](img/eb87333ccaa3a68fee4d5abd92da17cd.png)**

**[**HTML <区域> href 属性:**](https://www.geeksforgeeks.org/html-area-href-attribute/)****<区域> href** 属性用于指定目标页面的 URL。当<区域>中不存在 *href* 属性时，该元素将不是超链接。****

******语法:******

```html
**<area href="URL">**
```

******示例:**下面的代码说明了<区域>标签中 *href* 属性的使用。****

## ****超文本标记语言****

```html
**<!DOCTYPE html>
<html>
  <head>
    <title>HTML href Attribute</title>
  </head>
  <body style="text-align: center">
    <img
      src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190227165729/area11.png"
      alt="alt_attribute"
      width="300"
      height="119"
      class="aligncenter"
      usemap="#shapemap"/>

    <map name="shapemap">
      <!-- area tag contained image. -->
      <area
        shape="poly"
        coords="59, 31, 28, 83, 91, 83"
        href=
"https://media.geeksforgeeks.org/wp-content/uploads/20190227165802/area2.png"
        alt="Triangle"/>

      <area
        shape="circle"
        coords="155, 56, 26"
        href=
"https://media.geeksforgeeks.org/wp-content/uploads/20190227165934/area3.png"
        alt="Circle"/>

      <area
        shape="rect"
        coords="224, 30, 276, 82"
        href=
"https://media.geeksforgeeks.org/wp-content/uploads/20190227170021/area4.png"
        alt="Square"/>
    </map>
  </body>
</html>    **
```

******输出:******

****![](img/95dd87ba81295a14cba4fa40902719aa.png)****

****[**HTML <链接> href 属性:**](https://www.geeksforgeeks.org/html-link-href-attribute/)**HTML<链接> href 属性用于指定链接文档的 URL。它主要包含样式表文件的网址。******

******语法:******

```html
**<link href = "url">**
```

******示例:**下面的代码说明了<链接>标签中 *href* 属性的使用。****

## ****超文本标记语言****

```html
**<<!DOCTYPE html>
<html>
  <head>
    <title>HTML href Attribute</title>
    <link
      id="linkid"
      rel="stylesheet"
      type="text/css"
      href="style.css"
      sizes="16*16"
      hreflang="en-us"/>
  </head>
  <body style="text-align: center">
    <h2>GeeksforGeeks</h2>
    <b>link href Attribute</b>
  </body>
</html>**
```

******输出:******

****![](img/8bf2106505e2ccb62c50aad53d2c603a.png)

如何使用链接属性**** 

******支持的浏览器:******

*   ****谷歌 Chrome****
*   ****微软公司出品的 web 浏览器****
*   ****火狐浏览器****
*   ****歌剧****
*   ****旅行队****