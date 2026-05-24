# 当 jQuery 与某个元素不匹配时，如何让 jQuery 抛出错误？

> 原文:[https://www . geesforgeks . org/how-to-make-jquery-当元素不匹配时抛出错误/](https://www.geeksforgeeks.org/how-to-make-jquery-throw-an-error-when-it-doesnt-match-an-element/)

在本文中，我们将学习如何在 jQuery 与元素不匹配时产生抛出错误。

**方法:**为了完成这个任务，我们创建一个函数，并使用元素的[长度](https://www.geeksforgeeks.org/javascript-function-length-property/)属性检查给定元素是否存在。如果元素存在，则元素的长度大于或等于 1，否则元素的长度为 0。所以如果元素存在，我们会显示一条消息，否则我们会抛出一个错误。我们在使用该元素之前调用该函数。如果元素不存在，那么我们会得到一个错误。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
  <head>

    <!-- JQuery CDN -->
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js">
    </script>

  </head>

  <body>    
      <h2 style="color:green">GeeksforGeeks</h2>
      <b>Check for element existence using jQuery</b><br/>
      <ul>
        <li class="gfg1">CSS</li>
        <li class="gfg3">HTML</li>
        <li class="gfg4">JQuery</li>
      </ul>

     <div id="resultID"></div>

    <script>
      // Create a function that checks if the element exists or not.
      $.fn.check = function(){
        if(this.length === 0){

          $("#resultID").show().html("This element does not exist!");
        }
        else
        {
          $("#resultID").show().html("This element exist!");
        }
      }
      // Call check() function for li element having class gfg2.
      $('li.gfg2').check();
    </script>
  </body>
</html>
```

**输出:**

*   当我们使用带有列表项的函数 check()时，上面代码中不存在“gfg 2”类。
    T3】
*   当我们使用带有列表项的函数 check()时，上面代码中存在*“gfg 3”*类。
    T3】