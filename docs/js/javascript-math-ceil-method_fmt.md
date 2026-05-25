# JavaScript Math.ceil() 方法

> 原文: [https://www.geeksforgeeks.org/javascript-math-ceil-method/](https://www.geeksforgeeks.org/javascript-math-ceil-method/)

下面是 `Math.ceil()` 方法的例子。

*   **例:**

    ```html
    <script type="text/javascript">
        document.write("Result : " + Math.ceil(.89));
    </script>
    ```

*   **输出:**

    ```
    Result : 1
    ```

`Math.ceil()` 方法用于返回大于或等于给定数字的最小整数。`ceil()` 总是被用作 `Math.ceil()`，因为它是 `Math` 的静态方法。

**语法:**

```javascript
Math.ceil(value)
```

**参数:** 该方法接受上述和下述单个参数:

*   `value`: 要进行数学测试的值。

**返回值:** `Math.ceil()` 方法返回大于或等于给定数字的最小整数。

下面的例子说明了 JavaScript 中的 `Math.ceil()` 方法:

*   **例 1:**

    ```
    Input : Math.ceil(.89)
    Output: 1
    ```

*   **例 2:**

    ```
    Input : Math.ceil(-89.02)
    Output : -89
    ```

*   **例 3:**

    ```
    Input : Math.ceil(0)
    Output : 0
    ```

上述方法的更多代码如下:

**程序 1:** 当负数作为参数传递时。

```html
<script type="text/javascript">
    document.write("Result : " + Math.ceil(-89.02));
</script>
```

**输出:**

```
Result : -89
```

**程序 2:** 当零作为参数传递时。

```html
<script type="text/javascript">
    document.write("Result : " + Math.ceil(0));
</script>
```

**输出:**

```
Result : 0
```

**支持的浏览器:**

*   Google Chrome
*   Microsoft Edge
*   Firefox
*   Opera
*   Safari