# 类 CSS 中的通配符选择器(*、^和$)

> 原文: [https://www.geeksforgeeks.org/wildcard-selectors-and-in-css-for-classes/](https://www.geeksforgeeks.org/wildcard-selectors-and-in-css-for-classes/)

通配符选择器用于同时选择多个元素。它选择相似类型的类名或属性，并使用 CSS 属性。`*`通配符也称为包含通配符。

## 【`attribute*="value"`】选择器

【`attribute*="value"`】选择器用于选择属性值包含指定子字符串`value`的元素。这个例子展示了如何使用一个通配符来选择一个包含`str`的类的所有`div`。这可能是在课程的开始、结束或中途。

**语法:**

```html
[attribute*="value"] {
    // CSS property
}
```

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <style>
            /* Define styles of selected items, h1 and
               rest of the body */
            [class*="str"] {  /* WE USE * HERE */
                background: green;
                color: white;
            }
            h1 {
                color:green;
            }
            body {
                text-align:center;
                width:60%;
            }
        </style>
    </head>
    <body>
        <h1>GeeksforGeeks</h1>
        <!-- Since we have used * with str, all items with
             str in them are selected -->
        <div class="first_str">The first div element.</div>
        <div class="second">The second div element.</div>
        <div class="my-strt">The third div element.</div>
        <p class="mystr">Paragraph Text</p>
    </body>
</html>
```

**输出:**
![](img/b96eb9b6c782ce03ac3bc612df3ababf.png)

## 【`attribute^="value"`】选择器

【`attribute^="value"`】选择器用于选择属性值以指定值`value`开头的元素。此示例显示了如何使用通配符选择以`str`开头的类的所有`div`。

**语法:**

```html
[attribute^="str"] {
    // CSS property
}
```

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <style> 
            [class^="str"] { /*WE USE ^ HERE */
                background: green;
                color: white;
            }
            h1 {
                color:green;
            }
            body {
                text-align:center;
                width:60%;
            }
        </style>
    </head>
    <body>
        <h1>GeeksforGeeks</h1>
        <!-- All items beginning with str are highlighted -->
        <div class="strfirst">The first div element.</div>
        <div class="strsecond">The second div element.</div>
        <div class="str-start">The third div element.</div>
        <div class="end-str">The fourth div element.</div>
        <p class="my">Paragraph Text</p>
    </body>
</html>
```

**输出:**
![](img/594fd818b6daa9e5dde0f927f1898d44.png)

## 【`attribute$="value"`】选择器

【`attribute$="value"`】选择器用于选择那些属性值以指定值`value`结束的元素。以下示例选择类属性值以`str`结尾的所有元素。

**语法:**

```html
[attribute$="str"] {
    // CSS property
}
```

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <style> 
            [class$="str"] { /* WE USE $ HERE */
                background: green;
                color: white;
            }
            h1 {
                color:green;
            }
            body {
                text-align:center;
                width:60%;
            }
        </style>
    </head>
    <body>
        <h1>GeeksforGeeks</h1>
        <!-- All items ending with str are highlighted -->
        <div class="firststr">The first div element.</div>
        <div class="stsecondstr">The second div element.</div>
        <div class="start">The third div element.</div>
        <p class="mystr">This is some text in a paragraph.</p>
    </body>
</html>
```

**输出:**
![](img/5005f77e39eb471a873b835cf331fb96.png)

HTML 是网页的基础，通过构建网站和网络应用程序用于网页开发。您可以通过以下 [HTML 教程](https://www.geeksforgeeks.org/html-tutorials/)和 [HTML 示例](https://www.geeksforgeeks.org/html-examples/)从头开始学习 HTML。

CSS 是网页的基础，通过设计网站和网络应用程序用于网页开发。你可以通过以下 [CSS 教程](https://www.geeksforgeeks.org/css-tutorials/)和 [CSS 示例](https://www.geeksforgeeks.org/css-examples/)从头开始学习 CSS。