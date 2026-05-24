# jQuery 用户界面对话框创建事件

> 原文:[https://www . geesforgeks . org/jquery-ui-dialog-create-event/](https://www.geeksforgeeks.org/jquery-ui-dialog-create-event/)

创建对话框时会触发 jQuery UI 创建事件。

在这里 了解更多 jQuery 选择器和事件 [。](https://www.geeksforgeeks.org/jquery-selectors-and-event-methods/)

**语法:**

```html
$(".selector").dialog (
   create: function( event, ui ) {
       console.log('created')
   },
```

**进场:**

*   首先，添加项目所需的 jQuery Mobile 脚本。

```html
<link href = 
"https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css"
    rel = "stylesheet">
<script src = "https://code.jquery.com/jquery-1.10.2.js"></script>
<script src = "https://code.jquery.com/ui/1.10.4/jquery-ui.js">
</script>
```

*   “打开对话框”按钮将触发点击功能(#gfg)，该功能将进一步打开对话框(#gfg2)中的<textarea>。</textarea>
*   创建(事件，用户界面) :对话框创建时触发。这个创建附加了一个回调函数，它在对话框创建后被触发。
    *   事件:类型->事件
    *   用户界面:类型->对象
    *   回调函数:函数(事件，ui ) { console.log('created')}

**例 1:**

## 超文本标记语言

```html
<!doctype html>
<html lang = "en">
   <head>
      <meta charset = "utf-8">
      <link href = 
"https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css"
         rel = "stylesheet">
      <script src = "https://code.jquery.com/jquery-1.10.2.js">
        </script>
      <script src = "https://code.jquery.com/ui/1.10.4/jquery-ui.js">
        </script>

      <script type = "text/javascript">
         $(function() {
            $( "#gfg2" ).dialog({
          autoOpen: false, 
               create: function( event, ui ) {
                  console.log('created')
               },
            });
            $( "#gfg" ).click(function() {
               $( "#gfg2" ).dialog( "open" );
            });
         });
      </script>
   </head>

   <body>
      <div id = "gfg2" title="GeeksforGeeks">
         <textarea>jQuery UI | create(event, ui) Event</textarea>
      </div>
      <button id = "gfg">Open Dialog</button>
   </body>
</html>
```

**输出:**

![](img/d91f28ffe584bac2caa3bfa9e2e23871.png)