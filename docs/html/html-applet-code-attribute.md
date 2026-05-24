# HTML | applet 代码属性

> 原文:[https://www.geeksforgeeks.org/html-applet-code-attribute/](https://www.geeksforgeeks.org/html-applet-code-attribute/)

**<小程序>代码属性**指定要加载和执行的小程序 java 文件的相对网址。它用于将一个 Java 小程序链接到相关的 HTML 文档。它指定了 Java 小程序的文件名。

**语法:**

```html
<applet code = *"file_name"*> 
....
</applet> 

```

**属性值:**它包含一个字符串值，代表嵌入在 HTML 文档中的 java 文件的名称。

**示例:**

```html
<!DOCTYPE html> 
<html> 
    <applet code="HelloWorld" 
                width=200 
                height=60> 
    </applet>
</html>
```

**解释:**
这里，HelloWorld 是类文件，里面包含了小程序。宽度和高度属性决定了小程序在浏览器中打开时的宽度和高度(以像素为单位)。

**支持的浏览器:**<小程序>标签支持的浏览器如下:

*   火狐浏览器
*   旅行队