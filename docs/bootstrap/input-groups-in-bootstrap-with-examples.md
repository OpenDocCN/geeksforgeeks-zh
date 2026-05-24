# 带示例的引导中的输入组

> 原文:[https://www . geesforgeks . org/input-group-in-bootstrap-with-examples/](https://www.geeksforgeeks.org/input-groups-in-bootstrap-with-examples/)

Bootstrap 中的输入组用于通过在文本输入、自定义文件选择器或自定义输入的两侧添加文本或按钮来扩展默认表单控件。
**基本输入组**:以下类是用于将组添加到输入框两侧的基类。

*   **。input-group-prepend** 类用于将组添加到输入的前面。
*   **。输入-分组-追加**类用于将其添加到输入后面。
*   **。输入-组-文本**类用于设置组内显示的文本的样式。

以下示例演示了这些输入组:

## 超文本标记语言

```html
<!DOCTYPE html>

<html>
<head>
    <!-- Include Bootstrap CSS -->
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css">
    <title>Input Groups in Bootstrap</title>
</head>
<body>
    <div class="container">
        <h3>Prepend Group Example</h3>

        <!-- Declare an input group -->
        <div class="input-group">

            <!-- Prepend the following content to the input box -->
            <div class="input-group-prepend">

                <!-- Define the text content of the group -->
                <span class="input-group-text" id="username">@</span>
            </div>

            <!-- Declare an input box -->
            <input type="text" class="form-control" placeholder="Username">
        </div>

        <h3>Append Group Example</h3>

        <!-- Declare an input group -->
        <div class="input-group">

        <!-- Declare an input group -->
            <input type="text" class="form-control" placeholder="Email">

            <!-- Prepend the following content to the input box -->
            <div class="input-group-append">

                <!-- Define the text content of the group -->
                <span class="input-group-text" id="email">@example.com</span>
            </div>
        </div>

        <h3>Prepend and Append Together</h3>

        <!-- Declare an input group -->
        <div class="input-group">

            <!-- Prepend the following content to the input box -->
            <div class="input-group-prepend">

                <!-- Define the text content of the group -->
                <span class="input-group-text">https://</span>
            </div>

            <!-- Declare an input group -->
            <input type="text" class="form-control" placeholder="Your domain name here">

            <!-- Append the following content to the input box -->
            <div class="input-group-append">

                <!-- Define the text content of the group -->
                <span class="input-group-text">.com</span>
            </div>
        </div>
    </div>
</body>
</html>
```

**输出:**

![Prepend and Append](img/dcd6417fc6f5bbf54ff8746ba89f2481.png)

**输入组的大小**
输入组可以通过附加类变大或变小。输入组有 3 种可能的大小:

*   **。输入组 sm** 类用于较小的尺寸。
*   **。输入组 lg** 类用于更大的尺寸。
*   **。输入-组**类是默认大小。

**注意:**当前不支持对单个输入组元素进行调整。
**例:**

## 超文本标记语言

```html
<!DOCTYPE html>

<html>
<head>
    <!-- Include Bootstrap CSS -->
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css">
    <title>Input Groups in Bootstrap</title>
</head>
<body>
    <div class="container">
        <h1>Sizing</h1>

        <!-- Declare the small input group -->
        <div class="input-group input-group-sm mb-3">

            <!-- Prepend the following content to the input box -->
            <div class="input-group-prepend">

                <!-- Define the text content of the group -->
                <span class="input-group-text" id="small">Small</span>
            </div>

            <!-- Declare an input box -->
            <input type="text" class="form-control">
        </div>

        <!-- Declare the normal input group -->
        <div class="input-group mb-3">

            <!-- Prepend the following content to the input box -->
            <div class="input-group-prepend">

                <!-- Define the text content of the group -->
                <span class="input-group-text" id="medium">Default</span>
            </div>

            <!-- Declare an input box -->
            <input type="text" class="form-control">
        </div>

        <!-- Declare the large input group -->
        <div class="input-group input-group-lg">

            <!-- Prepend the following content to the input box -->
            <div class="input-group-prepend">

                <!-- Define the text content of the group -->
                <span class="input-group-text" id="large">Large</span>
            </div>

            <!-- Declare an input box -->
            <input type="text" class="form-control">
        </div>
    </div>
</body>
</html>
```

**输出:**

![Sizing of input groups](img/f84c545be54535a9a366e9fcea3bd298.png)

**使用多输入**:输入组可以使用多输入。
**例:**

## 超文本标记语言

```html
<!DOCTYPE html>

<html>
<head>
    <!-- Include Bootstrap CSS -->
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css">

    <title>Input Groups in Bootstrap</title>
</head>
<body>
    <div class="container">
        <h3>Multiple inputs</h3>

        <!-- Declare an input group -->
        <div class="input-group">

            <!-- Prepend the following content to the input box -->
            <div class="input-group-prepend">

                <!-- Define the text content of the group -->
                <span class="input-group-text" id="">First & Last name</span>
            </div>

            <!-- Declare two input boxes -->
            <input type="text" class="form-control">
            <input type="text" class="form-control">
        </div>
    </div>
</body>
</html>
```

**输出:**

![Multiple Inputs](img/669040ac81b48ba6effa1b9353a5901a.png)

**使用多个插件**:多个插件可以与其他类型堆叠或混合在一起，包括复选框和单选按钮。
**例:**

## 超文本标记语言

```html
<!DOCTYPE html>

<html>
<head>
    <!-- Include Bootstrap CSS -->
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css">

    <title>Input Groups in Bootstrap</title>
</head>
<body>
    <div class="container">
        <h1>Multiple addons</h1>

        <!-- Declare an input group -->
        <div class="input-group mb-3">

            <!-- Prepend the following content to the input box -->
            <div class="input-group-prepend">

                <!-- Declare two input groups -->
                <span class="input-group-text">{content}lt;/span>
                <span class="input-group-text">0.00</span>

            </div>
            <!-- Declare an input box -->
            <input type="text" class="form-control">
        </div>

        <!-- Declare an input group -->
        <div class="input-group">

            <!-- Declare an input box -->
            <input type="text" class="form-control">

            <!-- Append the following content to the input box -->
            <div class="input-group-append">

                <!-- Declare two input texts -->
                <span class="input-group-text">{content}lt;/span>
                <span class="input-group-text">0.00</span>
            </div>
        </div>
    </div>
</body>
</html>
```

**输出:**

![Multiple Addons](img/1a79bf909230df7b6ab5bf7b7d69b943.png)

**使用按钮插件**:按钮也可以添加到输入框中。
**例:**

## 超文本标记语言

```html
<!DOCTYPE html>

<html>
<head>
    <!-- Include Bootstrap CSS -->
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css">

    <title>Input Groups in Bootstrap</title>
</head>
<body>
    <div class="container">
        <h1>Button addons</h1>

        <!-- Declare an input group -->
        <div class="input-group mb-3">

            <!-- Prepend the following content to the input box -->
            <div class="input-group-prepend">

                <!-- Declare a button-->
                <button class="btn btn-outline-secondary" type="button">Button</button>
            </div>

            <!-- Declare an input box -->
            <input type="text" class="form-control">
        </div>

        <!-- Declare an input group -->
        <div class="input-group mb-3">

            <!-- Declare an input box -->           
            <input type="text" class="form-control">

            <!-- Append the following content to the input box -->
            <div class="input-group-append">

                <!-- Declare a button -->
                <button class="btn btn-outline-secondary" type="button">Button</button>
            </div>
        </div>

        <!-- Declare an input group -->       
        <div class="input-group mb-3">

            <!-- Prepend the following content to the input box -->           
            <div class="input-group-prepend">

                <!-- Declare two buttons -->
                <button class="btn btn-outline-secondary" type="button">Button 1</button>
                <button class="btn btn-outline-secondary" type="button">Button 2</button>
            </div>

            <!-- Declare an input box -->
            <input type="text" class="form-control">
        </div>

        <!-- Declare an input group -->            
        <div class="input-group mb-3">

            <!-- Declare an input box -->           
            <input type="text" class="form-control">

            <!-- Append the following content to the input box -->      
            <div class="input-group-append">

                <!-- Declare two buttons -->
                <button class="btn btn-outline-secondary" type="button">Button 1</button>
                <button class="btn btn-outline-secondary" type="button">Button 2</button>
            </div>
        </div>
    </div>
</body>
</html>
```

**输出:**

![Multiple Buttons](img/f0915c5a7b1b8eb84982e2de34d3b14e.png)

**使用自定义选择**:输入组可以与自定义选择一起使用。
**注意:**不支持浏览器默认版本的自定义选择。
**例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <!-- Include Bootstrap CSS -->
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css">
    <title>Input Groups in Bootstrap</title>
</head>

<body>
    <div class="container">
        <h3>Custom select</h3>

        <div class="input-group mb-3">
            <div class="input-group-prepend">
                <label class="input-group-text" for="select01">Options</label>
            </div>
            <select class="custom-select" id="select01">
                <option selected>Choose...</option>
                <option value="1">One</option>
                <option value="2">Two</option>
                <option value="3">Three</option>
            </select>
        </div>

        <div class="input-group mb-3">
            <select class="custom-select" id="select02">
                <option selected>Choose...</option>
                <option value="1">One</option>
                <option value="2">Two</option>
                <option value="3">Three</option>
            </select>
            <div class="input-group-append">
                <label class="input-group-text" for="select02">Options</label>
            </div>
        </div>
    </div>

    <script src="https://code.jquery.com/jquery-3.2.1.slim.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.9/umd/popper.min.js"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/js/bootstrap.min.js"></script>
</body>
</html>
```

**输出:**

![Custom Select](img/8b8b715f53f4abc91e59e0e5e9fe34a7.png)

**使用自定义文件输入**:输入组可以与自定义文件输入一起使用。
**注意:**不支持浏览器默认版本的文件输入。
**例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <!-- Include Bootstrap CSS -->
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css">
    <title>Input Groups in Bootstrap</title>
</head>

<body>
    <div class="container">
        <h3>Custom file input</h3>
        <div class="input-group mb-3">
            <div class="input-group-prepend">
                <span class="input-group-text">Upload</span>
            </div>
            <div class="custom-file">
                <input type="file" class="custom-file-input" id="file01">
                <label class="custom-file-label" for="file01">Choose file</label>
            </div>
        </div>

        <div class="input-group mb-3">
            <div class="custom-file">
                <input type="file" class="custom-file-input" id="file02">
                <label class="custom-file-label" for="file02">Choose file</label>
            </div>
            <div class="input-group-append">
                <span class="input-group-text" id="">Upload</span>
            </div>
        </div>
    </div>

    <script src="https://code.jquery.com/jquery-3.2.1.slim.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.9/umd/popper.min.js"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/js/bootstrap.min.js"></script>
</body>
</html>
```

**输出:**

![Custom File](img/6170b6693d349254e283e9d5674bf1d8.png)