# jQuery |语法

> 原文:[https://www.geeksforgeeks.org/jquery-syntax/](https://www.geeksforgeeks.org/jquery-syntax/)

它用于选择 HTML 中的元素并对这些元素执行操作。

**语法:**

```html
$(selector).action()
```

*   **$ sign: It grants access to jQuery.** *   ****(选择器):******It is used to find HTML elements.
 ***   jQuery action():**It is used to perform actions on the elements.

1.  **用于隐藏当前元素。**

    ```html
    $(this).hide()
    ```

2.  **用于隐藏所有< p >元素。**

    ```html
    $("p").hide()
    ```

3.  **用于隐藏所有带有 class =“test”的元素。**

    ```html
    $(".test").hide()
    ```

4.  **用于隐藏 id =“test”的元素。**

    ```html
    $("#test").hide()
    ```

**文件准备事件:**

*   **jQuery Methods are inside a Document ready event for easy reading of code.**

    ```html
    $(document).ready(function(){

      // jQuery Method

    });
    ```

    这是为了在文档加载完成之前检查并停止 jquery。该方法还允许您在文档正文之前的标题部分使用 JavaScript 代码。

    **在加载文档之前运行方法可能会失败的一些动作:**
    获取未加载的图像大小或隐藏尚未创建的元素。

*   **文件准备的较短方法:**

    ```html
    $(function(){

      // jQuery Method

    });
    ```**