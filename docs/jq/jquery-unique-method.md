# JQuery | unique()方法

> 原文:[https://www.geeksforgeeks.org/jquery-unique-method/](https://www.geeksforgeeks.org/jquery-unique-method/)

jQuery 中的这个 **unique()** 方法用来对 DOM 元素的数组进行排序，去掉重复的元素。

**语法:**

```html
jQuery.unique( array )

```

**参数:**unique()方法只接受上面提到的一个参数，如下所述:

*   **数组:**这个参数是 DOM 元素的数组。

**返回值:**移除重复项后返回 DOM 元素的排序数组。

**示例 1:** 在本例中， **unique()方法**从 div 数组中移除重复元素。

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>JQuery | unique() method</title> 
  <script src="https://code.jquery.com/jquery-3.4.1.js">
</script>
<style>
    div {
        color: blue;
    }
</style>
</head>
<body style="text-align:center;"> 

    <h1 style="color: green"> 
        GeeksForGeeks 
    </h1> 

    <h3>JQuery | unique() method</h3>
    <div></div>
    <div class="geek"></div>
    <div class="geek"></div>
    <div class="geek"></div>
    <div></div>
    <script>
    $(function () { 

        var divs = $( "div" ).get();

        divs = divs.concat( $( ".geek" ).get() );
        $( "div:eq(1)" ).text( 
"Sorts an array of DOM elements " + divs.length +
 " with the duplicates removed" );

        divs = jQuery.unique( divs );
        $( "div:eq(2)" ).text( 
"Sorts an array of DOM elements " + divs.length +
 " with the duplicates removed" )
            .css( "color", "red" );
    })
    </script>

</body>
</html>                    
```

**输出:**
![](img/7b298d5e35f490048d78d4fa7c47bb86.png)

**示例 2:** 在本例中， **unique()方法**从 p 的数组中移除所有重复的元素。

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>JQuery | unique() method</title> 

<script src = 
"https://code.jquery.com/jquery-3.4.1.js"> 
    </script> 

</head>
<body style="text-align:center;"> 

    <h1 style="color: green"> 
        GeeksForGeeks 
    </h1> 

    <h3>JQuery | unique() method</h3>
    <p></p>
    <p class="geek"></p>
    <p></p>
    <script>
    $(function () { 

        var ps = $( "p" ).get();
        ps = jQuery.unique( ps );
        $ UniqueSort (document getElementsByTagName ( "p".));
        $( "p" ).text( 
"Sorts an array of DOM elements with the duplicates removed" )
            .css( "color", "red" );
    })
    </script>

</body>
</html>                    
```

**输出:**
![](img/f990c8025024de433c4ef66a6a6984b3.png)