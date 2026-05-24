# HTTP 头|内容处理

> 原文:[https://www . geesforgeks . org/http-headers-content-disposition/](https://www.geeksforgeeks.org/http-headers-content-disposition/)

**HTTP** **内容处置**是一个响应类型的头字段，它提供了如何处理响应有效负载的信息，以及用户在本地保存时的附加信息，如*文件名*。在 MIME(多用途互联网邮件扩展)的较大上下文中，此响应头字段包含许多值和参数。但是，在 HTTP 表单和 POST 请求下，它会缩减为一组固定的参数和值。

**内容处置**标题字段采用不同的值，同时作为包含在内容主体、表单或多个部分中的数据的响应标题。它可以选择在本地提供数据或在浏览器中显示数据，同时处理浏览器主体中的内容。它可以提供关于特定数据字段的信息，这些信息作为子部分存储在多部分/表单数据中。

**语法:**

*   **Syntax for processing data in the main body:**

```html
Content Disposition : inline 
Content Disposition : attachment
Content Disposition : attachment ; filename = "file_name.html"

```

*   **Syntax for handling multi-part/form data:**

```html
Content-Disposition : form-data
Content-Disposition : form-data; name="field_value"
Content-Disposition : form-data; name="field_value"; filename="file_name.html"

```

**指令:**

1.**内容处置类型:**

*   **内联:**表示数据应在浏览器提示时自动显示。
*   **附件:**这表示用户应该收到提示(通常是*另存为*对话框)将文件本地保存在磁盘上进行访问。
*   **文件名:**它是一个可选参数，包含发送给收件人的文件的原始名称。接收者完全有权更改保存文件的名称或建议目录。此参数也可用于内联式处置。RFC 5987 提供了一个带有新编码的变体文件名*，但执行类似的功能。当两者都由一个标题使用时，这个参数现在比传统的文件名更受欢迎。

2.**内容处置参数:**

*   **Name:** Contains the name or value of the HTML field referenced by the form subsection.
*   **Form-data:** This means that the data is divided into parts, and each part is separated by a boundary.

3.**内容配置和多部分的工作:**

*   When using the content configuration header on multiple parts, it is applied to the whole collection as a whole, without consulting the configuration type of the sub-parts. However, when displaying the contents under "Multi-part", the disposal of each sub-part should be respected.
*   When using the embedded configuration, many parts should be displayed normally, and if there are any attachment sub-parts, user action is required.
*   User operation is required when accessories are used for disposal on multiple parts as a whole.

**示例:**以下示例摘自 RFC 6266 和 RFC 7578。

```html
content-disposition: form-data; name="field1"

```

```html
 content-disposition: form-data; name="_charset_"

```

```html
Content-Disposition: attachment;
filename="EURO rates";
filename*=utf-8''%e2%82%ac%20rates

```

```html
 Content-Disposition: inline ; filename=example.html

```

**支持的浏览器:**以下列出了 **HTTP 头|内容-配置**支持的浏览器: