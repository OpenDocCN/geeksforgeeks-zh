# jQuery show()方法

> 原文: [https://www.geeksforgeeks.org/jquery-effect-show-method/](https://www.geeksforgeeks.org/jquery-effect-show-method/)

jQuery 中的 `show()` 方法用于显示隐藏和选中的元素。

**注意:** 此方法显示使用 CSS `display: none` 属性隐藏的元素。使用 `visibility: hidden` 隐藏的元素不可见。

## 语法

```html
$(selector).show( speed, easing, callback )
```

## 参数

该方法接受三个参数，如下所述:

*   **speed:** 为可选参数，用于指定淡入淡出效果的速度。速度的默认值是 400 毫秒。速度的可能值有:
    *   毫秒
    *   `"slow"`
    *   `"fast"`
*   **easing:** 是可选参数，用于指定元素到动画不同点的速度。easing 的默认值是 `"swing"`。easing 的可能值是:
    *   `"swing"`
    *   `"linear"`
*   **callback:** 为可选参数。在 `show()` 方法完成后执行回调函数。

## 示例

以下示例说明了 jQuery 中的 `show()` 方法:

### 示例 1

该示例显示 `display: none` 的内容，未给定速度。

```html
<!DOCTYPE html>  
<html>

<head> 
    <title> 
        jQuery Effect show() Method
    </title>

<style>
        #Outer {
          border: 1px solid black;
          padding-top: 40px;
          height: 140px;
          background: green;
          display: none;
        }
    </style>

<script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
</head>

<body style = "text-align:center;">

<div id= "Outer">
        <h1 style = "color:white;" >  
            GeeksForGeeks  
        </h1>  
    </div><br>

<button id = "btn"> 
        Show
    </button>

<!-- Script to show display:none content -->       
    <script> 
        $(document).ready(function() {
            $("#btn").click(function() {
                $("#Outer").show(1000);
            });
        });
    </script> 
</body>

</html> 
```

**输出:**

*   **点击按钮前:**
    ![](img/e914e57f34719b8f99155e6203c5f5cd.png)
*   **点击按钮后:**
    ![](img/6ea3526e9ea58e52dcefe795195c9ca2.png)

### 示例 2

该示例显示 `display: none` 的内容，使用 `"swing"` easing 值。

```html
<!DOCTYPE html>  
<html>

<head> 
    <title> 
        jQuery Effect show() Method
    </title>

<style>
        #Outer {
          border: 1px solid black;
          padding-top: 40px;
          height: 140px;
          background: green;
          display: none;
        }
    </style>

<script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
</head>

<body style = "text-align:center;">

<div id= "Outer">
        <h1 style = "color:white;" >  
            GeeksForGeeks  
        </h1>  
    </div><br>

<button id = "btn"> 
        Show
    </button>

<!-- Script to show display: none content
            with swing easing -->     
    <script> 
        $(document).ready(function() {
            $("#btn").click(function() {
                $("#Outer").show("swing");
            });
        });
    </script> 
</body>

</html> 
```

**输出:**

*   **点击按钮前:**
    ![](img/e914e57f34719b8f99155e6203c5f5cd.png)
*   **点击按钮后:**
    ![](img/6ea3526e9ea58e52dcefe795195c9ca2.png)