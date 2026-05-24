# 内嵌 HTML 助手–ASP.NET MVC 中的 HTML 助手

> 原文:[https://www . geesforgeks . org/inline-html-helper-html-helper-in-ASP-net-MVC/](https://www.geeksforgeeks.org/inline-html-helper-html-helpers-in-asp-net-mvc/)

HTML 助手是返回 HTML 字符串的方法。这些在视图中使用。简单来说，这些是用来返回 HTML 的 C#方法。使用 HTML 助手，您可以渲染文本框、区域、图像标签等。在 MVC 中，我们有许多内置的 HTML 助手，我们也可以创建自定义助手。使用 HTML 助手，视图可以显示模型属性，并且可以根据属性的类型生成 HTML。

**HTML 助手的类型:**

1.  内联 HTML 帮助器
2.  内置的 HTML 帮助程序
    *   标准 HTML 帮助程序
    *   强类型的 HTML 帮助程序
    *   模板 html 帮助器
3.  自定义 HTML 帮助器

**内联 HTML 帮助器**
这些是在单个视图上使用并且在同一页面上使用的帮助器类型。可以使用 **@helper 标签创建内联 HTML 助手。**

```html

You can create your own HTML Helper with the following syntax.
@helper HelperName(parameters)
{
    // code
}
To use the above-created helper we use the following syntax
@HelperName(parameters)

```

**示例:**

```html
@{
    Layout = null;
}

<!--created a inline HTMl Helper 
    with a single string type parameter-->
@helper MyInlineHelper(string[] words)
{
    <ol>
        <!--Used a foreach loop inside HTML.
 similarly we can use any conditional statement
          or any logic like 
            we use in normal C# code.-->
        @foreach (string word in words)
        {
            <li>@word</li>

        }
    </ol>
}
<!DOCTYPE html>

<html>
<head>
    <meta name="viewport" content="width=device-width" />
    <title>Inline HTML Helper</title>
</head>
<body>
    <div>
        <!--called it inside this 
            div and to get the output-->
        @MyInlineHelper(new string[] {
                  "Delhi", "Punjab", "Assam", "Bihar" })

    </div>
</body>
</html>  
```

**输出:**
![](img/c153ff67aa80e882d1abd1a0b28f6ef9.png)

**内嵌 HTML 助手的缺点**

*   这些助手只能用于单个视图。不能在多个视图中使用它。

**参考:** [在 Visual Studio](https://www.geeksforgeeks.org/how-to-install-and-setup-visual-studio-for-asp-net/) 中设置并运行代码