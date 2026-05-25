# HTML DOM Style orphans 属性

> 原文：[https://www.geeksforgeeks.org/html-dom-style-orphans-property/](https://www.geeksforgeeks.org/html-dom-style-orphans-property/)

DOM `style.orphans` 属性控制在旧页面上段落拆分时，一页或一列末尾可以留下的最小行数。`orphans` 的默认值是 `inherit` 或 `2`（这意味着如果一个段落将被拆分，页面上至少会留下 2 行）。

## 语法

- 获取 `orphans` 属性：
```html
object.style.orphans
```

- 设置 `orphans` 属性：
```html
object.style.orphans = "number|initial|inherit"
```

## 属性值

- **number**：一个整数，它指定一页或一列末尾可以留下的行数。不允许负值。默认值为 `2`。
- **initial**：将元素设置为初始值。
- **inherit**：元素从父元素继承其 `orphans` 属性。

## 示例：设置 `orphans` 属性的行数

```html
<!DOCTYPE html>
<html>
<head>
    <title>
        HTML | DOM Style orphans Property
    </title>
    <div id="element">
        <p>
          Cascading Style Sheets (CSS) is a style
          sheet language used for describing the 
          presentation of a document written in a
          markup language like HTML.[1] CSS is a 
          cornerstone technology of the World Wide 
          Web, alongside HTML and JavaScript.
        </p>
        <p> 
          <span style="color: red; font-weight: bold">
            CSS is designed to enable the separation 
            of presentation and content, including 
            layout,colors, and fonts.CSS has a simple
            syntax and uses a number of English keywords
            to specify the names of various style 
            properties.A style sheet consists of a list 
            of rules. Each rule or rule-set consists of
            one or more selectors,and a declaration block.
          </span>
        </p>
        <p>
          This separation can improve content accessibility,
          provide more flexibility and control in the 
          specification of presentation characteristics,
          enable multiple web pages to share formatting 
          by specifying the relevant CSS in a separate .css 
          file, and reduce complexity and repetition in 
          the structural content.
        </p>
        <p>
          Separation of formatting and content also makes
          it feasible to present the same markup page in 
          different styles for different rendering methods, 
          such as on-screen, in print, by voice 
          (via speech-based browser or screen reader), 
          and on Braille-based tactile devices. CSS also
          has rules for alternate formatting if the content
          is accessed on a mobile device.
        </p>
        <p>
          The name cascading comes from the specified 
          priority scheme to determine which style rule
          applies if more than one rule matches a particular
          element. This cascading priority scheme is predictable.
        </p>
    </div>
    <style>
        #element {
            columns: 12em 3;
            column-gap: 3em;
        }
    </style>
    <script>
        function myFunction() {
            // Number of lines that can be left at the end 
            // of a page or column.
            document.getElementById("element").style.orphans = "5";
        }
        myFunction()
    </script>
</head>
</html>
```

**输出**：根据 `orphans` 属性，如果一个段落要拆分，页面或列上至少会留下 5 行（正如我们在代码中设置 `orphans` 属性为 `"5"`）。

![](img/d03c2f13473e3643f3ad8b8278069fa9.png)

## 支持的浏览器

以下是支持 *HTML DOM Style orphans 属性* 的浏览器：

- Google Chrome 25+
- Internet Explorer 8+
- Opera 9.2+