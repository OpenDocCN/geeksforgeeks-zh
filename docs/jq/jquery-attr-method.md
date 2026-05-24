# jQuery | attr()方法

> 原文:[https://www.geeksforgeeks.org/jquery-attr-method/](https://www.geeksforgeeks.org/jquery-attr-method/)

jQuery 中的 **attr()方法**用于**设置**或**返回**所选元素的属性和值。

**语法:**

*   要返回属性值:

    ```html
    $(selector).attr(attribute)
    ```

*   设置属性和值:

    ```html
    $(selector).attr(attribute, value)
    ```

*   使用函数设置属性和值:

    ```html
    $(selector).attr(attribute, function(index, currentvalue))
    ```

*   要设置多个属性和值:

    ```html
    $(selector).attr({attribute:value, attribute:value, ...})
    ```

**参数**

*   **属性:**此参数用于指定属性的名称
*   **值:**用于指定属性的值
*   **函数(index，currentvalue):** 用于指定返回要设置的属性值的函数
*   **索引:**借助此参数接收的元素的索引位置。
*   **当前值:**用于接收所选元素的当前属性值。

**示例-1:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>jQuery attr() Method
  </title>

    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
  </script>
</head>

<body>
    <center>
        <h1 style="color:green;">  
            GeeksForGeeks</h1>
        <h2> jQuery attr() Method</h2>
        <h3 style="color:lightgreen;">
      </h3>
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190221153831/1132-120x300.png"
             alt="" 
             width="120" 
             height="300" 
             class="alignnone size-medium wp-image-915678" />
        <br>
        <br>
        <button>Click</button>
        <script>
            $(document).ready(function() {
                $("button").click(function() {
                    $("img").attr("width", "300");
                });
            });
        </script>
    </center>
</body>

</html>
```

**输出:**
**之前点击按钮:**
![](img/ec931cfdfce8aeea5d739db31d7e85a0.png)

**点击按钮后:**
![](img/7d998459b1b7ba885b6a3be117d58068.png)

**示例-2:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>jQuery attr() Method</title>
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
  </script>
</head>

<body>
    <center>
        <h1 style="color:green;">  
            GeeksForGeeks</h1>
        <h2> jQuery attr() Method</h2>
        <h3 style="color:lightgreen;"></h3>
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190221153831/1132-120x300.png"
             alt=""
             width="120"
             height="300" 
             class=
             "alignnone size-medium wp-image-915678" />
        <br>
        <br>
        <button>Click</button>
        <script>
            $(document).ready(function() {
             $("button").click(function() {
               alert("Image width: " + 
                     $("img").attr("width"));
                });
            });
        </script>
    </center>
</body>

</html>
```

**输出:**

**之前点击按钮:**
![](img/ec931cfdfce8aeea5d739db31d7e85a0.png)

**点击按钮后:**
![](img/675e43a4a65a029b7f5e962644601ff4.png)

**示例-3:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>jQuery attr() Method</title>
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
  </script>
</head>

<body>
    <center>
        <h1 style="color:green;">  
            GeeksForGeeks</h1>
        <h2> jQuery attr() Method</h2>
        <h3 style="color:lightgreen;">
      </h3>
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190221153831/1132.png" 
             alt="" 
             width="120"
             height="300" 
             class=
             "alignnone size-medium wp-image-915678" />
        <br>
        <br>
        <button>Click</button>
        <script>
            $(document).ready(function() {
             $("button").click(function() {
              $("img").attr("width", function(n, v) {
                return v - 50;
                    });
                });
            });
        </script>
    </center>
</body>

</html>
```

**输出:**

**之前点击按钮:**
![](img/ec931cfdfce8aeea5d739db31d7e85a0.png)

**点击按钮后:**
![](img/8e750b04402cfbbc458c3fe18dcd27e4.png)

**示例-4:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>jQuery attr() Method
  </title>

    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
  </script>
</head>

<body>
    <center>
        <h1 style=
            "color:green;">  
            GeeksForGeeks</h1>

        <h2> jQuery attr() Method</h2>
        <h3 style="color:lightgreen;"></h3>
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190221153831/1132.png" 
             alt="" 
             width="120"
             height="300" 
             class=
             "alignnone size-medium wp-image-915678" />
        <br>
        <br>
        <button>Click</button>

        <script>
            $(document).ready(function() {
             $("button").click(function() {
              $("img").attr({
                   width: "150",
                   height: "100"
                    });
                });
            });
        </script>
    </center>
</body>

</html>
```

**输出:**

**之前点击按钮:**
![](img/ec931cfdfce8aeea5d739db31d7e85a0.png)

**点击按钮后:**
![](img/a1a57a815f7843d665273db44fb11d38.png)