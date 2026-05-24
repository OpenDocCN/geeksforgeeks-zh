# HTTP 头|源图

> 原文:[https://www.geeksforgeeks.org/http-headers-sourcemap/](https://www.geeksforgeeks.org/http-headers-sourcemap/)

**HTTP 源映射头**是一个响应类型的头，用于从转换后的源映射原始源。例如，在执行时，浏览器会将 Javascript 资源从其原始来源转换为其他来源。在调试过程中，调试一个转换后的源代码太难了。另一方面，原始源代码很容易调试。因此，SourceMap 头用于获取原始源。SourceMap 头使浏览器能够从转换后的源代码重建原始源代码，并将其呈现在调试器中。它将生成的代码与源代码链接起来。

**语法:**

```html
SourceMap: <url>
```

**指令:**HTTP SourceMap 头接受上面提到的单个指令，如下所述:

*   **< URL >:** This instruction indicates the location of the source map file where the original file is to be obtained.

**示例:**

*   In this example, the URL mentioned points to the SourceMap file, that is, the transformation source whose reconstructed original source is to be obtained.

    ```html
    SourceMap: /geeks/gfg/file.js.map
    ```

*   In this example, you may not see it, because this **x-SourceMap** has been abandoned, and the URL mentioned refers to the sourcemap file, that is, the transformation source whose reconstructed original source is to be obtained.

    ```html
    X-SourceMap: /geeks/g4g/main.js.map
    ```

**支持的浏览器:**浏览器兼容 **HTTP SourceMap Header** 列表如下: