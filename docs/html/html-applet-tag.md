# HTML 小程序标签

> 原文:[https://www.geeksforgeeks.org/html-applet-tag/](https://www.geeksforgeeks.org/html-applet-tag/)

HTML 中的 **<小程序>** 标签被用来*将 Java 小程序嵌入到任何 HTML 文档*中。 **<小程序>** 标签在 HTML 4.01 中被弃用，它的支持从 HTML 5 开始已经完全停止。HTML 5 中可用的替代项是 [**<嵌入>**](https://www.geeksforgeeks.org/html-embed-tag/) 和 [**<对象>**](https://www.geeksforgeeks.org/html-object-tag/) 标签。仍然有一些浏览器在一些附加插件/安装的帮助下支持<小程序>标签。Internet Explorer 11 和更早版本在插件的帮助下。
html 5 不支持小程序标签。<小程序>标签有许多属性，其中最重要的是**代码**属性。这个**代码**属性用于将一个 Java 小程序链接到相关的 HTML 文档。它指定了 Java 小程序的文件名。

**属性:**该标签接受以下属性:

*   [对齐](https://www.geeksforgeeks.org/html-align-attribute/):指定小程序的对齐方式。
*   [alt](https://www.geeksforgeeks.org/html-alt-attribute/) :指定小程序的替代文本。
*   存档:指定存档文件的位置。
*   [边框](https://www.geeksforgeeks.org/html-border-attribute/):指定小程序面板周围的边框。
*   代码库:为代码属性中指定的小程序指定一个相对的基本 URL。
*   [高度](https://www.geeksforgeeks.org/html-height-attribute/):指定小程序的高度。
*   [hs space](https://www.geeksforgeeks.org/html-applet-hspace-attribute/):定义小程序周围的水平间距。
*   mayscript:指示是否允许 Java 小程序访问网页的脚本对象。
*   [名称](https://www.geeksforgeeks.org/html-name-attribute/):定义小程序的名称(在脚本中使用)
*   [vspace:](https://www.geeksforgeeks.org/html-img-vspace-attribute/) 定义小程序周围的垂直间距。
*   [宽度:](https://www.geeksforgeeks.org/html-img-width-attribute/)指定小程序的宽度。

**语法:**

```html
<applet *attribute1 attribute2....*>
   <param *parameter1*>
   <param *parameter2*>
   ....
</applet>
```

以下示例解释了小程序标签:

**例 1:** 这里， **HelloWorld** 是类文件，里面包含小程序。**宽度**和**高度**属性决定了小程序在浏览器中打开时的宽度和高度(以像素为单位)。
可与 **<小程序>** 标签结合使用的属性如下:

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<!-- applet code starts here -->
    <applet code="HelloWorld">
<!-- applet code ends here -->
    </applet>
</html>                                  
```

**参数:**参数非常类似于命令行参数，因为它们提供了一种在小程序启动后向其传递信息的方式。小程序在启动前所有可用的信息都被称为硬编码，即嵌入其中。参数使得在小程序运行期间生成和使用数据成为可能。

**语法:**

```html
<param name=*parameter_name* value=*parameter_value*>
```

小程序代码使用分配给**参数**标签的**名称**属性的名称作为变量来访问在**值**属性中指定的参数值。通过这种方式，小程序能够与嵌入它的 HTML 页面进行交互，并且能够在运行时处理页面提供给它的值。

**例 2:** 在这段代码中，小程序文件 HelloWorld 可以使用名为**的变量 message** 来访问其中存储的值，即**“hello world”**。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<!-- applet code starts here -->
<applet code="HelloWorld">
    <param name="message" value="HelloWorld">
<!-- applet code ends here -->
</applet>

</html>
```

**支持的浏览器:**

*   火狐浏览器
*   旅行队