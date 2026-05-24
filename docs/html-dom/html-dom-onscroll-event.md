# HTML | DOM on croll 事件

> 原文:[https://www.geeksforgeeks.org/html-dom-onscroll-event/](https://www.geeksforgeeks.org/html-dom-onscroll-event/)

当使用滚动条时，会发生滚动事件。CSS 溢出用于创建滚动条。
T3】支持的标签

*   ，
*   ，
*   ，
*   ，
*   ，
*   ，
*   ，
*   ，
*   ，
*   ，
*   ，
*   ，

    # 至

*   ，
*   ，

*   ，
*   ，<object>*   ，
        1.  ，
        2.  ，
        3.  ，<select>，，</select><textarea></li><li>，<tfoot/></li><li>，<thead/></li><li>，<ul/></li></ul><p><strong>语法:</strong> <br/></p><ul><li><strong>在 HTML 中:</strong> <br/></li></ul><pre><element onscroll="myScript"></pre><ul><li><strong>在 JavaScript 中:</strong> <br/></li></ul><pre>object.onscroll = function(){myScript};</pre><ul><li><strong>在 JavaScript 中，使用 addEventListener()方法:</strong> <br/></li></ul><pre>object.addEventListener("scroll", myScript);</pre><ul><li> </li></ul><p><strong>示例:</strong>使用 addEventListener()方法<br/></p><div class="responsive-tabs"><h2 class="tabtitle">超文本标记语言</h2><div class="tabcontent"><pre><!DOCTYPE html> <html>   <head>     <title>         HTML DOM onscroll Event     </title> </head>   <body>     <center>         <h1 style="color:green">           GeeksforGeeks       </h1>         <h2>HTML DOM onscroll Event</h2>         <textarea style="width:100%" id="tID">             HTML stands for Hyper Text Markup Language.           It is used to design web pages using markup language.           HTML is the combination of Hypertext and Markup language.           Hypertext defines the link between the web pages.           Markup language is used to define the text document           within tag which defines the structure of web pages.           HTML is a markup language which is used by the browser           to manipulate text, images and other content to           display it in required format.         </textarea>           <p id="try"></p>       </center>     <script>         document.getElementById(           "tID").addEventListener("scroll", GFGfun);           function GFGfun() {             document.getElementById(               "try").innerHTML = "Textarea scrolled.";         }     </script>   </body>   </html></pre></div></div><p><strong>输出:</strong> <br/></p><p><img src="img/49e1769d60767c57e29828a775a4c58f.png" alt=""/></p><p><strong>支持的浏览器:</strong><strong>HTML DOM onscroll 事件</strong>支持的浏览器如下:<br/></p><ul><li>谷歌 Chrome</li><li>微软公司出品的 web 浏览器</li><li>火狐浏览器</li><li>苹果 Safari</li><li>歌剧</li></ul><p> </p> </body></html></textarea></object>