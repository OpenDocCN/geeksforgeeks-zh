# 如何使用 bootstrap-select 进行下拉？

> 原文:[https://www . geesforgeks . org/使用方法-引导-选择用于下拉菜单/](https://www.geeksforgeeks.org/how-to-use-bootstrap-select-for-dropdown/)

Bootstrap Select 是一个表单控件，它显示了可以选择的不同值的可折叠列表。这可用于向用户显示表单或菜单。本文展示了在 Bootstrap 中使用**自定义样式**和 **bootstrap-select** 设置<select>元素样式的方法。</select>

**使用默认自定义样式:** Bootstrap 具有可应用于某些表单元素的自定义样式。自定义选择菜单只需要一个自定义类，即**。自定义-选择**触发自定义样式。但是，自定义样式仅限于**选择的**初始外观，由于浏览器限制，不能更改**选项的**。下面的例子展示了如何使用**设置默认的<选择>元素的样式。在引导程序中自定义选择**。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/css/bootstrap.min.css">
    <script src="https://kit.fontawesome.com/577845f6a5.js" 
        crossorigin="anonymous">
    </script>

    <!-- Optional JavaScript -->
    <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js">
    </script>
    <script src=
"https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js">
    </script>
    <script src=
"https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/js/bootstrap.min.js">
    </script>
</head>

<body>
    <h1 style="color: green">
        GeeksforGeeks
    </h1>

    <!-- Use the custom-select class -->
    <select class="custom-select" 
            style="width:150px;">
        <option>Pizzas</option>
        <option>Burger</option>
        <option>Ice Cream</option>
        <option>Fried Potatoes</option>
    </select>
</body>

</html>
```

**输出:**

![](img/854d0caacf201883eef8111d855ccaa1.png)

只有一些样式属性可以应用于 **<选项>** 组件。这是因为这种组件是“被替换组件”的一种情况。它们依赖于**操作系统**，而不是 HTML/浏览器的一部分。它不能通过 CSS 设置样式。除了**背景色**和**颜色**之外，通过 **<选项>** 组件的样式对象应用的样式设置被忽略。

选择选项是由操作系统而不是 HTML 设计的。因此，CSS 样式没有任何影响。

```html
option { 
    background-color: color; 
    border-radius: value; 
    font-size: value 
}
```

总的来说，上述值将会起作用。但是，我们不能自定义填充、边距和其他属性。

**Bootstrap-select:** 为解决上述问题， **bootstrap-select** 可用于样式化<选项><选择>标签。

**注意:**默认情况下， **bootstrap-select** 自然会识别正在使用的 bootstrap 版本。但是，在少数情况下，版本检测可能不起作用。

以下示例显示了如何将引导选择包含在页面中并进行初始化。选择组件中使用**选择选择器**类来自动初始化引导选择，如示例中所述:

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <link rel="stylesheet" href=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css">
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js">
    </script>
    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.9/umd/popper.min.js">
    </script>
    <script src=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/js/bootstrap.min.js">
    </script>

    <!-- CDN link used below is compatible with this example -->
    <link rel="stylesheet" href=
"https://cdnjs.cloudflare.com/ajax/libs/bootstrap-select/1.13.1/css/bootstrap-select.min.css">
    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/bootstrap-select/1.13.1/js/bootstrap-select.min.js">
    </script>
</head>

<body>
    <h1 style="color: green">
        GeeksforGeeks
    </h1>
    <select class="selectpicker" 
        data-style="btn-success">
        <option>Pizzas</option>
        <option>Burger</option>
        <option>Ice Cream</option>
        <option>Fried Potatoes</option>
    </select>
</body>

</html>
```

**输出:**

![](img/e422ad0a65c8891d3d7e5f93081f66ed.png)

以下是可用于设置<**选择>** 标签样式的一些属性:

*   **数据-直播-搜索:**它允许我们添加搜索输入。
*   **数据-代币:**它允许我们在选项中添加关键词，以提高它们的搜索能力。
*   **数据-最大值-选项:**它允许我们指定可以选择的选项数量的限制。它也适用于选项组。
*   **标题:**该属性允许我们在未选择任何内容时设置默认占位符文本。
*   **数据样式:**这个属性帮助我们设置按钮类的样式。
*   **显示-勾选:**该属性帮助我们在标准选择框上显示勾号图标。
*   **数据-宽度:**这个属性帮助我们设置选择的宽度。

以下是可用于设置 **<选项>** 标签样式的一些属性:

*   **数据图标:**用于为<选项>或<选项组>添加图标。
*   **数据内容:**用于将自定义 HTML 插入<选项>。
*   **数据-潜台词:**用于给<选项>或<选项组>元素添加潜台词。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <link rel="stylesheet" href=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css">
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js">
    </script>
    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.9/umd/popper.min.js">
    </script>
    <script src=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/js/bootstrap.min.js">
    </script>

    <!-- CDN link used below is compatible with this example -->
    <link rel="stylesheet" href=
"https://cdnjs.cloudflare.com/ajax/libs/bootstrap-select/1.13.1/css/bootstrap-select.min.css">
    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/bootstrap-select/1.13.1/js/bootstrap-select.min.js">
    </script>
</head>

<body>
    <h1 style="color: green">
        GeeksforGeeks
    </h1>

    <!-- Using the attributes to style the 
        <select> and <option> tag -->
    <select class="selectpicker">
        <option data-content=
"<span class='badge badge-danger'>Pizzas</span>">
            Pizzas
        </option>
        <option data-content=
"<span class='badge badge-success'>Burger</span>">
            Burger
        </option>
        <option data-content=
"<span class='badge badge-primary'>Ice Cream</span>">
            Ice Cream
        </option>
        <option data-content=
"<span class='badge badge-warning'>Fried Potatoes</span>">
            Fried Potatoes
        </option>
    </select>
</body>

</html>
```

**输出:**

![](img/60f931a67d444991c8cb53cab218ba6a.png)