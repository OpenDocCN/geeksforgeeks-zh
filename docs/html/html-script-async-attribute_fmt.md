
# HTML `<script>` 标签的 `async` 属性

> **参考链接**：[HTML `<script>` async 属性](https://www.geeksforgeeks.org/html-script-async-attribute/)

<p><strong>HTML `<script>` async 属性</strong> 是一个布尔属性。如果存在，它指定脚本在可用时异步执行。此属性仅适用于外部脚本（并且仅在存在 `src` 属性时使用）。</p>

<p><strong>注意：</strong>执行外部脚本的方式有很多：</p>

<ul>
  <li>存在 `async` 时：
    <ul>
      <li>脚本与页面的其余部分异步执行（脚本将在页面继续解析时执行）</li>
      <li>当 `async` 不存在且 `defer` 存在时：当页面解析完毕时执行脚本</li>
      <li>如果 `async` 或 `defer` 都不存在：在浏览器继续解析页面之前立即提取并执行脚本</li>
    </ul>
  </li>
</ul>

<p><strong>语法：</strong></p>

<pre>&lt;script async&gt;</pre>

<p><strong>示例：</strong></p>

<div class="responsive-tab">
  <h2 class="tab title">HTML</h2>
  <div class="tab content">
    ```html
    <!DOCTYPE html>
    <html>
    <body>
    <center>
    <h1 style="color: green;">geeksforgeeks</h1>
    <p id="P1">你好 GFG</p>
    <script src="geeks.js" async></script>
    </center>
    </body>
    </html>
    ```
  </div>
</div>

<p><strong>geeks.js</strong></p>

<div class="responsive-tab">
  <h2 class="tab title">JavaScript</h2>
  <div class="tab content">
    ```javascript
    alert("你好，GFG");
    ```
  </div>
</div>

<p><strong>输出：</strong></p>
<p><img src="img/03771a97aceb574eee6fedff9ab889bc.png" alt></p>

<p><strong>支持的浏览器：</strong></p>
<p><strong>支持 `<script>` async 属性的浏览器</strong> 如下所列：</p>

<ul>
  <li>Google Chrome 4.0</li>
  <li>Firefox 4.0</li>
  <li>Apple Safari 4.0</li>
  <li>Opera 10.5</li>
</ul>
</body>
</html>
