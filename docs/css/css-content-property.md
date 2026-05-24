# CSS 内容属性

> 原文:[https://www.geeksforgeeks.org/css-content-property/](https://www.geeksforgeeks.org/css-content-property/)

CSS 中的**内容** **属性**用于动态生成内容(在运行时)即。，它用生成的内容值替换元素。用于生成内容:&之前:[伪元素](https://www.geeksforgeeks.org/css-pseudo-elements/)之后。

**语法:**

```html
content: normal|none|counter|attr|string|open-quote|close-quote|
no-open-quote|no-close-quote|url|initial|inherit;
```

**属性值:**下面的例子很好地描述了所有的属性。

**正常:**如果内容属性正常，则用于设置内容，也用于设置默认值。

**语法:**

```html
Element::before|after { 
    content: normal;
}
```

**示例:**本示例演示了使用**内容属性**来生成内容:&之前:【伪元素之后。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
    <title> CSS | content Property </title>
    <style>
    p::before {
        content: "Welcome ";
    }

    a::before {
        content: normal;
    }
    </style>
</head>

<body>
    <p>to GeeksforGeeks</p>

    <p id="a">you</p>

</body>
</html>
```

**输出:**

```html
Welcome to GeeksforGeeks
Welcome you
```

**无:**不设置伪元素前后的内容。

**语法:**

```html
Element::before|after { 
    content: none;
}
```

**示例:**本示例演示了**内容属性**的使用，其中< p >标签内的内容将以不同的值动态显示。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
    <title> CSS | content Property </title>
    <style>
    p::before {
        content: "Hello";
    }

    p#a::before {
        content: none;
    }
    </style>
</head>

<body>
    <p> GeeksforGeeks!</p>

    <p id="a">Welcomes to GeeksforGeeks!</p>

</body>
</html>
```

**输出:**

```html
Hello GeeksforGeeks!
Welcome to GeeksforGeeks!
```

**初始值:**将属性设置为默认值。

**语法:**

```html
Element::before|after {
    content: initial;
}
```

**示例:**本示例演示了**内容属性**的使用，其中内容显示为其初始值。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
    <title> CSS | content Property </title>
    <style>
    p::before {
        content: "Welcome ";
    }

    a::before {
        content: initial;
    }
    </style>
</head>

<body>
    <p>to GeeksforGeeks</p>

    <p id="a">you</p>

</body>
</html>
```

**输出:**

```html
Hello GeeksforGeeks!
Hello Welcomes to GeeksforGeeks!
```

**属性:**设置包含指定值的属性值。

**语法:**

```html
Element::before|after { 
    content:attr(href); 
}
```

**示例:**本示例演示了**内容属性**的使用，其中属性值被设置为指定值。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
    <title> CSS | content Property </title>
    <style>
      a::after {
          content: attr(href);
      }
    </style>
</head>

<body> 
  <a href=
"https://www.geeksforgeeks.org/html-style-attribute/">
        Click Here!
  </a> 
</body>
</html>
```

**输出:**

```html
Click Here! https://www.geeksforgeeks.org/html-style-attribute/
```

**字符串:**用于生成 HTML 元素前后的任意字符串。

**语法:**

```html
Element::before|after { 
    content: string;
}
```

**示例:**该示例演示了**内容属性**的使用，其中字符串值将在 HTML 元素前后生成任何字符串。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS | content Property</title>
    <style>

        /* String value used here */
        p::before { 
            content: "Hello";
        }
    </style>
</head>

<body>
    <p> GeeksforGeeks!</p>

</body>
</html>
```

**输出:**

```html
Hello GeeksforGeeks!
```

**开盘价:**在元素前后生成开盘价。

**语法:**

```html
Element::before|after { 
    content: open-quote;
}
```

**示例:**本示例演示了**内容属性**的使用，其中内容的属性值设置为开引号。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
    <title> CSS | content Property </title>
    <style>
        p::before {
            content: open-quote;
        }
    </style>
</head>

<body> 
    <p>Welcome to GeeksforGeeks!</p>
</body>
</html>
```

**输出:**

```html
"Welcome to GeeksforGeeks!
```

**收盘报价:**在元素前后生成收盘报价。

**语法:**

```html
Element::before|after { 
    content: close-quote;
}
```

**示例:**该示例演示了**内容属性**的使用，其中内容的属性值被设置为闭引号。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
    <title> CSS | content Property </title>
    <style>
        p::after {
            content: close-quote;
        }
        p::before {
            content: open-quote;
        }
    </style>
</head>

<body>   
    <p>Welcome to GeeksforGeeks!</p>
</body>
</html>
```

**输出:**

```html
"Welcome to GeeksforGeeks!"
```

**不开引号:**如果指定了，则从内容中删除开引号。

**语法:**

```html
Element::before|after { 
    content: no-open-quote;
}
```

**示例:**此示例演示了**内容属性**的使用，其中内容的属性值设置为无开引号。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
    <title> CSS | content Property </title>
    <style>
        p::before {
            content: open-quote;
        }
        p::before {
            content: no-open-quote;
        }
    </style>
</head>

<body>
     <p>Welcome to GeeksforGeeks!</p>

</body>
</html>
```

**输出:**

```html
Welcome to GeeksforGeeks!
```

**无结束引用:**如果指定了结束引用，它将从内容中删除结束引用。

**语法:**

```html
Element::before|after { 
    content: no-close-quote;
}
```

**示例:**本示例演示了**内容属性**的使用，其中内容的属性值设置为无关闭引用。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
    <title> CSS | content Property </title>
    <style>
        p::before {
            content: open-quote;
        }
        p::after {
            content: no-close-quote;
        }
    </style>
</head>
<body>
    <p>Welcome to GeeksforGeeks!</p>
</body>
</html>
```

**输出:**

```html
"Welcome to GeeksforGeeks!
```

**inherit:** 该属性从其父元素继承而来。

**语法:**

```html
Element::before|after { 
    content: inherit;
}
```

**支持的浏览器:**由*内容属性*支持的浏览器如下:

*   谷歌 Chrome 1.0
*   Internet Explorer 8.0
*   微软边缘 12.0
*   Firefox 1.0
*   Opera 4.0
*   Safari 1.0