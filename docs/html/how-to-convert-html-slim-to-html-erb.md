# 如何将 html.slim 转换成 html.erb？

> 原文:[https://www . geesforgeks . org/how-convert-html-slim-to-html-erb/](https://www.geeksforgeeks.org/how-to-convert-html-slim-to-html-erb/)

**Slim 和 erb 介绍:** Slim 文件和工具用于使代码更加轻便，将有助于使用它来代替特定的代码。erb 也用于做类似的事情，但是如果你想在代码中进行更改，那么用户应该分别熟悉 slim/erb。

如果你必须把一个超文本标记语言文档转换成超文本标记语言的小文件，那么你可以去*https://html2slim.herokuapp.com/*

**将 html.slim 转换为 html.erb:** 这里我们来看看如何将 slim 文件改为 erb 文件。在命令行界面中，您可以在 slim 文件中使用内置命令来转换这些文件。

您可以在命令行界面中遵循下面给出的语法:

```html
slimrb --erb html.slim
```

slimrb 是一个命令行工具，意味着 convert 和–erb 表示文件将被转换为 erb 格式。然后按照命令给出瘦文件名<file name="">。</file>

**语法:**

```html
slimrb --erb <slim file name>
```

这个命令可以在 slim 实用程序中找到。使用以上说明后，用户将能够将 slim 文件转换为 erb 文件。