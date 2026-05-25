
# 理解 HTML 表单编码：URL 编码和多部分表单

> 原文: [https://www.geeksforgeeks.org/understanding-html-form-encoding-url-encoded-and-multipart-forms/](https://www.geeksforgeeks.org/understanding-html-form-encoding-url-encoded-and-multipart-forms/)

HTML 表单包含两种编码，[*URL 编码表单*](https://www.geeksforgeeks.org/html-url-encoding/) 和 *多部分表单*。HTML 格式的编码由名为 *“enctype”* 的属性决定。这个属性可以有三个值:

*   **Application/x-www-form-urlencoded:** 这个值表示通过 [URL](https://www.geeksforgeeks.org/url-full-form/) (统一资源定位符) 编码的表单。默认情况下，它被分配给 *enctype* 属性。
*   **Multi-part/form-data:** 这个值表示 *多部分* 表单。它被用户用于上传文件。
*   **Text/Normal:** 这个值表示最新 HTML5 中引入的新表单，用于发送未编码的数据。

**URL 编码表单:** 使用这种类型的表单编码提交的数据是 URL 编码的，从它的名称就可以非常清楚。

**示例:**

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <title>URL Encoded Forms</title>
  </head>
  <body>
    <form
      action="/urlencoded?firstname=Geeks&lastname=forGeeks"
      method="POST"
      enctype="application/x-www-form-urlencoded">
      <input type="text" name="username" value="GeeksforGeeks" />
      <input type="text" name="password" value="GFG@123" />
      <input type="submit" value="Submit" />
    </form>
  </body>
</html>
```
