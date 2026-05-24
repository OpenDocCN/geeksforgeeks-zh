# HTML | DOM 对话框 showModal()方法

> 原文:[https://www . geesforgeks . org/html-DOM-dialog-show modal-method/](https://www.geeksforgeeks.org/html-dom-dialog-showmodal-method/)

DOM Dialog showModal()方法用于显示对话框。对话元素由 getElementById()访问。它用在 HTML5 中。
使用此方法时，用户无法与页面上的其他元素进行交互。要使用户与其他元素交互，请使用 show()方法。

**语法:**

```html
dialogObject.showModal()
```

**示例:**本示例展示了 Dialog showModal()方法的工作原理:

```html
<!DOCTYPE html>
<html>
<body>

<h3> HTML | DOM Dialog showModal() Method</h3>
<p>Click on the below buttons to show the dialog window.</p>

<button onclick="showDialog()">Show dialog box</button>

<dialog id="showDialog" style= "color:green">
            Welcome to GeeksforGeeks</dialog>

<script>
var gfg = document.getElementById("showDialog"); 

function showDialog() { 
gfg.showModal(); 
} 
</script>

</body>
</html>                    

```

**输出:**
点击按钮前:
![](img/32ec9653c630e2b990675e63d185dd54.png)

点击按钮后:
![](img/871c2bb8e3d9c704cdaba16bec95e233.png)

**支持的浏览器:**

*   谷歌 Chrome 37.0
*   Opera 24.0
*   Safari 6.0