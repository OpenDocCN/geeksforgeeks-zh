# 使用 Python 解析 HTML 文档并将其转换为 XML 格式

> 原文: [https://www.geeksforgeeks.org/parsing-and-converting-html-documents-to-xml-format-using-python/](https://www.geeksforgeeks.org/parsing-and-converting-html-documents-to-xml-format-using-python/)

在本文中，我们将看到如何使用 Python 解析 HTML 文档并将其转换为 XML 格式。

可以通过以下方式完成：

*   使用 `lxml` 模块。
*   使用 `BeautifulSoup` 模块。

## 方法 1: 使用 Python lxml 库

在这种方法中，我们将使用 Python 的 `lxml` 库来解析 HTML 文档，并将其写入 XML 树的编码字符串表示。`lxml` XML 工具包是 C 库 `libxml2` 和 `libxslt` 的 Pythonic 绑定。它的独特之处在于，它将这些库的速度和 XML 特性的完整性与本机 Python 应用编程接口的简单性结合在一起，大多数兼容但优于众所周知的 `ElementTree` 应用编程接口。

**安装:**

```py
pip install lxml
```

我们需要提供打开 HTML 文档的路径，使用 `HTML.fromstring(*str*)` 函数进行读取和解析，返回单个元素/文档树。这个函数从给定的字符串中分析文档。这总是会创建一个正确的 HTML 文档，这意味着父节点是 `<html>`，有一个主体，可能还有一个头部。

```py
htmldoc = html.fromstring(inp.read())
```

并使用 `etree.tostring()` 函数将解析后的 HTML 元素/文档树写入其 XML 树的编码字符串表示中。

```py
out.write(etree.tostring(htmldoc))
```

使用的 HTML 文件: [input](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20210819194859/input.html)。

**代码:**

```py
# Import the required library
from lxml import html, etree

# Main Function
if __name__ == '__main__':

    # Provide the path of the html file
    file = "input.html"

    # Open the html file and Parse it, 
    # returning a single element/document.
    with open(file, 'r', encoding='utf-8') as inp:
        htmldoc = html.fromstring(inp.read())

    # Open a output.xml file and write the 
    # element/document to an encoded string 
    # representation of its XML tree.
    with open("output.xml", 'wb') as out:
        out.write(etree.tostring(htmldoc))
```