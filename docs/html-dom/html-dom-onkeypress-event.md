# html \ DOM 是一个新闻事件

> 原文:[https://www.geeksforgeeks.org/html-dom-onkeypress-event/](https://www.geeksforgeeks.org/html-dom-onkeypress-event/)

HTML 中的 **DOM onkeypress 事件**发生在用户按下某个键时。

与 onkeypress 事件相关的事件顺序:

*   叔叔家
*   按键
*   上基乌普

**支持的 HTML 标签:**所有 HTML 元素，除了:

*   <iframe></li><li><meta/></li><li><param/></li><li><script/></li><li><style/></li><li><title/></li></ul><p><strong>语法:</strong></p><ul><li><strong>在 HTML 中:</strong> <pre>&lt;element onkeypress="myScript"&gt;</pre></li><li><strong>在 JavaScript 中:</strong> <pre>object.onkeypress = function(){myScript};</pre></li><li><strong>在 JavaScript 中，使用 addEventListener()方法:</strong> <pre>object.addEventListener("keypress", myScript);</pre></li></ul><p><strong>示例:</strong>使用 addEventListener()方法在按键事件上</p><pre>&lt;!DOCTYPE html&gt; &lt;html&gt;    &lt;head&gt;     &lt;title&gt;       DOM onkeypress event   &lt;/title&gt; &lt;/head&gt;    &lt;body&gt;     &lt;center&gt;         &lt;h1 style="color:green"&gt;           GeekforGeeks       &lt;/h1&gt;         &lt;p&gt;Press any key inside            the input field&lt;/p&gt;            &lt;input type="text"                id="inputField"                style="background-color:green"&gt;            &lt;script&gt;             document.getElementById(               "inputField").addEventListener("keypress", GFGFun);                function GFGFun() {                 document.getElementById(                   "inputField").style.backgroundColor =                    "yellow";                }         &lt;/script&gt;     &lt;/center&gt; &lt;/body&gt;    &lt;/html&gt;</pre><p><strong>输出:</strong> <br/> <strong>前:</strong> <br/> <img src="img/9a9464954eecb8726278816caf85804e.png" alt="" class="aligncenter size-medium wp-image-1176725"/> <br/> <strong>后:</strong> <br/> <img src="img/d6e6cf974cc0e4114160d04f0e21ec92.png" alt="" class="aligncenter size-medium wp-image-1176726"/></p><p><strong>支持的浏览器:</strong>按键事件上<strong> HTML DOM 支持的浏览器如下:</strong></p><ul><li>谷歌 Chrome</li><li>微软公司出品的 web 浏览器</li><li>火狐浏览器</li><li>苹果 Safari</li><li>歌剧</li></ul><br/><br/><br/> </body></html></iframe>