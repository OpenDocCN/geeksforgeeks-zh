# ASP 二进制编写方法

> 原文:[https://www.geeksforgeeks.org/asp-binarywrite-method/](https://www.geeksforgeeks.org/asp-binarywrite-method/)

**ASP BinaryWrite 方法**用于指定将数据写入当前 HTTP 输出。没有任何字符转换。此方法用于写入图像所需的非字符串信息，如二进制数据。这是**响应**类型对象的预定义方法。

**语法:**

```vb
response.BinaryWrite data 
```

**参数值:**

*   **数据:**指定将要发送的二进制信息

**返回值:**这个方法没有返回值。
**示例:**如果您有一个生成字节数组的对象，您可以使用以下对 BinaryWrite 的调用将字节发送到自定义应用程序:

## java 描述语言

```vb
<%
   Set objBinaryGen=Server.CreateObject("MyComponents.BinaryGenerator")
   pic = objBinaryGen.MakePicture
   response.BinaryWrite pic
 %>
```

**参考文献:**

https://docs.microsoft.com/en-us/previous-versions/iis/6.0-sdk/ms524861(v=vs.90)