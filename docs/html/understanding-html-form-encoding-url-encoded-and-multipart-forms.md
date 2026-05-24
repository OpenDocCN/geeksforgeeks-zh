# 理解 HTML 表单编码:URL 编码和多部分表单

> 原文:[https://www . geesforgeks . org/understanding-html-form-encoding-URL-encoded-and-multipart-forms/](https://www.geeksforgeeks.org/understanding-html-form-encoding-url-encoded-and-multipart-forms/)

HTML 表单包含两种编码， [*URL 编码表单*](https://www.geeksforgeeks.org/html-url-encoding/) 和*多部分表单*。HTML 格式的编码由名为*“enctype*”的属性决定。这个属性可以有三个值:

*   **Application/x-www-form-URL encoded:** This value represents a form encoded by [URL](https://www.geeksforgeeks.org/url-full-form/) (Uniform Resource Locator). By default, it is assigned to the *enctype* attribute.
*   **Multi-part/form data:** This value represents the M *multi-part* form. It is used by users to upload files.
*   **Text/Normal:** This value represents the newly introduced form in the latest HTML5, which is used to send data without any encoding.

**URL 编码表单:**使用这种类型的表单编码提交的数据是 URL 编码的，从它的名称就可以非常清楚。

**示例:**

## HTML

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