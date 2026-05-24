# HTML | DOM 输入单选对象

> 原文:[https://www.geeksforgeeks.org/html-dom-input-radio-object/](https://www.geeksforgeeks.org/html-dom-input-radio-object/)

**输入无线电对象**用于**访问**或**使用 **type="radio"** 创建**输入元素。

**语法:**

*   要访问输入元素，请键入“radio”。

    ```html
    document.getElementById("ID");
    ```

*   创建输入元素。

    ```html
    var GFG = document.createElement("INPUT");
    x.setAttribute("type", "radio");

    ```

**属性值:**

| 价值 | 描述 |
| 自（动）调焦装置 | 它说明当页面加载时，单选按钮是否应该自动获得焦点。 |
| 检查 | 它返回单选按钮的选中状态。 |
| 默认已检查 | 它返回选中属性的默认值。 |
| 缺省值 | 它返回单选按钮的默认值。 |
| 有缺陷的 | 如果单选按钮被禁用或未被禁用，它将返回。 |
| 形式 | 它返回对包含单选按钮的窗体的引用。 |
| 名字 | 它返回单选按钮的名称属性值。 |
| 需要 | 如果在提交表单之前必须选中单选按钮，则返回。 |
| 类型 | 它返回单选按钮是哪种类型的表单元素。 |
| 价值 | 它返回单选按钮的 value 属性值。 |

**示例-1:** 访问输入对象类型=“无线电”

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        body {
            text-align: center;
        }

        h1 {
            color: green;
        }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>

    <h2>HTML DOM Input Radio Object</h2>

    <h3>An example access a Radio Button</h3> 
  Radio Button:
    <input type="radio" 
           checked=true
           id="radioID">

    <p>Click the button to uncheck it.</p>
    <button onclick="GFG()">
      Click!
  </button>

    <script>
        function GFG() {

            // Accessing input element
            // type="radio"
            var x = 
            document.getElementById("radioID");
            x.checked = false;
        }
    </script>

</body>

</html>
```

**输出:**

**点击前:**
![](img/3453d729a78f14520ad92e2bf05e1a2c.png)

**点击后:**
![](img/b2f994c2601b3fc7c858fc4d77a6ed49.png)

**示例-2:** 创建输入元素类型=“单选”。

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        body {
            text-align: center;
        }

        h1 {
            color: green;
        }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>

    <h2>HTML DOM Input Radio Object
  </h2>
    <p>Click to create a Radio Button.
  </p>

    <button onclick="myFunction()">
      Create
  </button>
    <br>
    <script>
        function myFunction() {

            // Creating input element
            // type="radio"
            var x = 
            document.createElement("INPUT");
            x.setAttribute("type", "radio");
            document.body.appendChild(x);
        }
    </script>

</body>

</html>
```

**输出:**

**点击前:**
![](img/f7966c11c9da43436e4780ff0c67da63.png)

**点击后:**
![](img/7368a6ea3fa410c942bc5407ebfe8c3e.png)

**支持的浏览器:**

*   谷歌 Chrome
*   Mozilla Firefox
*   边缘
*   旅行队
*   歌剧