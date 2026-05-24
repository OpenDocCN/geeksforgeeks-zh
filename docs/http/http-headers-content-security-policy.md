# HTTP 头|内容-安全-策略

> 原文:[https://www . geesforgeks . org/http-headers-content-security-policy/](https://www.geeksforgeeks.org/http-headers-content-security-policy/)

**内容安全策略**响应头字段是一种工具，用于实施深度防御机制，以保护数据免受内容注入漏洞(如跨脚本攻击)的影响。它提供了一种策略机制，允许开发人员检测其应用程序中存在的缺陷并降低应用程序权限。它为开发人员提供了对应用程序的细粒度控制，以防止各种攻击并保持内容完整性。

**语法:**

> 内容安全策略:指令-值；指令指令值

上面有*指令*和*指令值*。在一行中可以使用多个策略指令，用分号分隔。

**带有示例的指令:**

1.**提取指令:**这些指令用于控制某个资源可以被访问或加载到系统中的点。

*   **child-src:** 它控制嵌套浏览上下文和请求的创建，这些内容和请求填充了工作人员的框架。

    ```html
    Content-Security-Policy: child-src https://example.com/
    ```

*   **default-src:** 考虑到输入的值，它用作策略的默认源列表，并作为其他提取指令的后备。

    ```html
    Content-Security-Policy: default-src 'self'
    ```

*   **frame-src:** 限制为嵌套浏览上下文加载的 URL。

    ```html
    Content-Security-Policy: frame-src https://example.com/
    ```

*   **manifest-src:** 它控制资源的各种元素可能被加载的网址。

    ```html
    Content-Security-Policy: manifest-src https://example.com/
    ```

*   **对象-src:** 用于限制可以将插件内容加载到应用程序中的网址。

    ```html
    Content-Security-Policy: object-src https://example.com/
    ```

*   **connect-src:** 用于控制可以使用脚本接口加载到应用程序中的 URL。

    ```html
    Content-Security-Policy: connect-src https://example.com/
    ```

*   **字体-src:** 它控制可以将字体加载到应用程序中的网址。

    ```html
    Content-Security-Policy: font-src https://example.com/
    ```

*   **img-src:** 它控制可以将图像加载到应用程序中的网址。

    ```html
    Content-Security-Policy: img-src https://example.com/
    ```

*   **media-src:** 它控制可以将音频、视频和相关文本轨道资源加载到应用程序中的 URL。

    ```html
    Content-Security-Policy: media-src https://example.com/
    ```

*   **style-src:** 它控制可以向应用程序应用加载和应用样式表的源。
*   **script-src:** 它控制可以将 JavaScript 实现到应用程序中的源。
*   很少有提取指令是实验性的应用程序编程接口，例如**预取-src、脚本-src-elem、脚本-src-attr、style-src-elem、style-src-attr 和 worker-src。**

2.**文档指令:**这些指令控制 CSP 管理下的所有文档和工作环境的属性实现。

*   **插件类型:**它限制加载的资源，以限制插件嵌入文档的可能性。

    ```html
    Content-Security-Policy: plugin-types application/pdf
    ```

*   **基本 uri:** 它控制可以加载到文档中存在的*基本*元素中的 URL。
*   **沙盒:**HTML 沙盒策略可以通过本指令的规范由用户代理应用。

3.**导航指令**包含**形式动作、框架祖先和导航到**指令。*表单操作*指令控制可用于表单提交的网址。*框架祖先*指令限制可以使用*框架、iframe、object、embed* 或*小程序*元素嵌入资源的 URL。*导航至*指令指定了文档可以通过任何方法遍历的网址。

4.**报告指令**包含**报告至**，其指定发送违规报告的终点。先前使用的*报告-uri* 现在已被否决。

**再举几个例子:**

文章中的所有例子都取自万维网联盟的 CSP 三级草案。

```html
Content-Security-Policy: script-src https://cdn.example.com/scripts/; object-src 'none'
Content-Security-Policy: script-src 'self'; report-to csp-reporting-endpoint
Content-Security-Policy: prefetch-src https://example.com/
Content-Security-Policy: worker-src https://example.com/
Content-Security-Policy: navigate-to example.com

```

**浏览器兼容性:**

CSP Level 3 提供了 Chrome 59+、Firefox 58+和 Edge 79+版本的部分支持。
CSP Level 2 提供 Chrome 40+、Safari 10+、Edge 76+版本的完全支持，火狐 31+和 Edge 15+版本的部分支持。
CSP Level 1 提供了 Chrome 25+、Firefox 23+、Edge 12+和 Safari 7+版本的完整支持。