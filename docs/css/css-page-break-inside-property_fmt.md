# CSS | 分页符-内部属性

> 原文: [https://www.geeksforgeeks.org/css-page-break-inside-property/](https://www.geeksforgeeks.org/css-page-break-inside-property/)

CSS 中的 `page-break-inside` 属性用于指定打印时如何在应用它的元素内分页。它插入一个分页符，或者有时它用于在打印时避免元素内出现分页符。

## 语法

```html
page-break-inside: auto|avoid|initial|inherit
```

## 属性值

### auto
它是默认值。此值表示自动分页。

**语法:**

```html
page-break-inside: auto;
```

### avoid
避免元素内部出现分页符。

**语法:**

```html
page-break-inside: avoid;
```

### initial
它将 `page-break-inside` 属性设置为默认值。

**语法:**

```html
page-break-inside: initial;
```

### inherit
`page-break-inside` 属性是从其父级继承的。

**语法:**

```html
page-break-inside: inherits;
```

## 注意
该属性主要用于打印文档。

## 打印媒体查询

```html
@media print {
    img {
        display: block;
        page-break-inside: avoid;
    }
}
```

## 示例 1
本示例使用 `page-break-inside` 属性值来避免。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        CSS page-break-inside property
    </title>

<style type="text/css">
        @media print {
            ul {
              page-break-inside: avoid;
            }
        }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>

<h2>CSS page-break-inside property</h2>

<br><br><br>

<img src = 
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-logo.png" 
    alt = "" />

<br><br><br><br>

<p>
        Prepare for the Recruitment drive of product based
        companies like Microsoft, Amazon, Adobe etc with a
        free online placement preparation course. The course
        focuses on various MCQ's & Coding question likely to
        be asked in the interviews & make your upcoming 
        placement season efficient and successful. 
    </p>

<br><br><br>

<img src = 
"https://media.geeksforgeeks.org/wp-content/uploads/interview-preparation-2.png"
    alt = "" />

<ul>
        <li>Data Structure</li>
        <li>Algorithms</li>
        <li>C Programming</li>
        <li>C++ Programming</li>
        <li>Java Programming</li>
        <li>Python Programming</li>
        <li>PHP Programming</li>
        <li>Operating System</li>
        <li>Computer Networks</li>
        <li>DBMS</li>
        <li>SQL</li>
        <li>TOC</li>
    </ul>
</body>

</html>
```

## 输出
### 打印预览
![](img/a96dad74bb93e9b78311d9d0c049fde0.png)

## 示例 2
此示例将 `page-break-inside` 属性值设置为 `none`。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        CSS page-break-inside property
    </title>

<style type="text/css">
        @media print {
            ul {
              page-break-inside: none;
            }
        }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>

<h2>CSS page-break-inside property</h2>

<br><br><br>

<img src = 
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-logo.png" 
    alt = "" />

<br><br><br><br>

<p>
        Prepare for the Recruitment drive of product based
        companies like Microsoft, Amazon, Adobe etc with a
        free online placement preparation course. The course
        focuses on various MCQ's & Coding question likely to
        be asked in the interviews & make your upcoming 
        placement season efficient and successful. 
    </p>

<br><br><br>

<img src = 
"https://media.geeksforgeeks.org/wp-content/uploads/interview-preparation-2.png"
    alt = "" />

<ul>
        <li>Data Structure</li>
        <li>Algorithms</li>
        <li>C Programming</li>
        <li>C++ Programming</li>
        <li>Java Programming</li>
        <li>Python Programming</li>
        <li>PHP Programming</li>
        <li>Operating System</li>
        <li>Computer Networks</li>
        <li>DBMS</li>
        <li>SQL</li>
        <li>TOC</li>
    </ul>
</body>

</html>
```

## 输出
### 打印预览
![](img/0ec39a9a531edda66c8d2ee51bb03c5c.png)

## 支持的浏览器
`page-break-inside` 属性支持的浏览器如下:

*   Google Chrome 1.0
*   Internet Explorer 8.0
*   Firefox 19.0
*   Safari 1.3
*   Opera 7.0