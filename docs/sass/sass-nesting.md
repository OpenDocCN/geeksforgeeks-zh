# SASS |嵌套

> 原文:[https://www.geeksforgeeks.org/sass-nesting/](https://www.geeksforgeeks.org/sass-nesting/)

SASS 嵌套使我们的工作非常高效，我们不必一次又一次地重复外部选择器。我们可以按照嵌套选择器在 HTML 文件中出现的顺序编写嵌套选择器(即父-外和子-内选择器形式)。SASS 会自动做合并的工作。

见下例:
**SASS 文件:**

```html
ul {
    list-style-type: none;

    li {
        display: inline-block;

        a {
            text-decoration: none;
            display: inline-block;
            padding: 10px 15px; 
            color: blue;
        }
    }
}

```

**编译后的 CSS 文件:**

```html
ul {
    list-style-type: none;
}

ul li {
   display: inline-block;
}

ul li a {
    text-decoration: none;
    display: inline-block;
    padding: 10px 15px;
    color: blue;
}

```

SASS 还允许选择器嵌套不同的组合符。您可以将组合符放在内部选择器的开始处、外部选择器的末端或两者的中间。

见下例:
**SASS 文件:**

```html
ul { 
    + li {
        display: inline-block;
    }
}

li {
    > {
        a {
            text-decoration: none;
        }   
    }
}

p ~ {
    span {
        text-decoration-line: underline;
        text-decoration-style: double;
    }
}

```

**编译后的 CSS 文件:**

```html

ul + li {
    display: inline-block;
}

li > a {
    text-decoration: none;
}

p ~ span {
    text-decoration-line: underline;
    text-decoration-style: double;
}

```