# 在 JavaScript 中传递函数作为参数

> 原文：[https://www.geeksforgeeks.org/passing-a-function-as-a-parameter-in-javascript/](https://www.geeksforgeeks.org/passing-a-function-as-a-parameter-in-javascript/)

将函数作为参数传递给函数与将变量作为参数传递给函数非常相似。下面的例子描述了如何将一个函数作为参数传递给另一个函数。

**示例 1：** 本示例将函数 `geeks_inner` 传递给函数 `geeks_outer` 作为参数。

```
<!DOCTYPE html>
<html>
    <head>
        <title>
            JavaScript | Pass a function as parameter
        </title>
    </head>

<body style = "text-align:center;">

<h1 style = "color:green;" >
            GeeksForGeeks
        </h1>

<p>
            Passing function as arguments.
        </p>

<!-- Function call after clicking the button -->
        <button onclick = "geeks_outer(geeks_inner)">
            Click Here
        </button>

<script>
            function geeks_inner(value){
                return 'hello User!';
            }
            function geeks_outer(func){
                alert(func());
            }
        </script>
    </body>
</html>
```

**输出：**

*   **点击按钮前：**
    ![](img/afc731f4d4b1a13a8887961227fd8cb3.png)
*   **点击按钮后：**
    ![](img/22a720c71aec6a70e5f4e7e4a42588ac.png)

**示例 2：** 这个示例传递了一个函数 `geeks_inner` 以及一个参数 `'Geeks!'` 以功能 `geeks_outer` 为论据。

```
<!DOCTYPE html>
<html>
    <head>
        <title>
            JavaScript | Pass a function as parameter
        </title>
    </head>

<body style = "text-align:center;">

<h1 style = "color:green;" >
            GeeksForGeeks
        </h1>

<p>
            Passing function as arguments.
        </p>

<button onclick = "geeks_outer('Geeks!', geeks_inner)">
            Click Here
        </button>

<!-- Script to uses function call using
            function as argument -->
        <script>
            function geeks_inner(value){
                return 'hello '+value;
            }
            function geeks_outer(a, func){
                alert(func(a));
        }
        </script>
    </body>
</html>
```

**输出：**

*   **点击按钮前：**
    ![](img/afc731f4d4b1a13a8887961227fd8cb3.png)
*   **点击按钮后：**
    ![](img/0c60b9d07314c21630b4235670584083.png)