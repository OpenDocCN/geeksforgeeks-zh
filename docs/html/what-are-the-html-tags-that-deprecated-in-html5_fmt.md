# HTML 5 中有哪些不推荐使用的 HTML 标签？

> 原文：[https://www.geeksforgeeks.org/what-are-the-html-tags-that-deprecated-in-html5/](https://www.geeksforgeeks.org/what-are-the-html-tags-that-deprecated-in-html5/)

在本文中，我们将看到各种不推荐使用的 Html 标签及其在 HTML5 中的替代标签。不推荐使用的标签是那些允许使用但不推荐使用的标签，并且正在被更新的标签所取代。当以其他方式实现相同的属性时，标记或属性会贬值。被丢弃的几个原因及使用较新的一个：

*   有几个标签可以帮助完成同样的任务。由于这个原因，源代码的长度也减少了，因此提高了整体性能。
*   管理大尺寸代码将是困难的，修改这样的源代码不可能一蹴而就。这可能会增加开发时间以及代码的模糊性。
*   有时，如果我们需要使用特定的代码块来执行特定的任务，那么我们可能需要重新编写代码，这种情况可能会发生。所有这些因素都有助于增加复杂性以及不值得开发过程的开发时间。

为此，在 HTML5 中引入了几个标签和属性。下面是不推荐使用的标签的完整列表，将在下面讨论。

## HTML 5 不推荐使用的标签

下面给出了不推荐使用的标签的完整列表。

| 标签 | 描述 | 替代标签 |
| --- | --- | --- |
| `<basefont>` | To specify a base font. | Font style sheet. |
| `<font>` | It specifies the text, size and color of the font. | Family, font size and color. |
| `<center>` | It specifies a centered text. | Text-Alignment: Center. |
| `<strike>` | It specifies a punch-through text. | Text-decoration. |
| `<big>` | Define Daimonji. | Use CSS attributes or title tags. |
| `<dir>` | It specifies a directory list. | Ul label. |
| `<isindex>` | It specifies a single-line input field. | Form a mark. |
| `<applet>` | It specifies an applet. | Object label. |
| `<acronym>` | Abbreviations are defined with this label. | Use abbreviations |
| `<noframes>` | It is used to define the noframe section. | Or use iframe and CSS instead, or use server-side include to generate a complete page with various invariant parts. |
| `<xmp>` | Render the text between the opening and closing tags, without interpreting the middle HTML and using a constant-width font. | Use pre and code instead. |
| `<noembed>` | A tag can easily provide alternative content and tell users what they are missing. | When rollback is needed, use objects instead of embedding. |
| `<plaintext>` | Used to present all the text in the document exactly as it was typed. | Use "text/normal" MIME type instead. |
| `<frameset>` | It specifies a set of frames. | Or use iframe and CSS instead, or use server-side include to generate a complete page with various invariant parts. |
| `<frame>` | It specifies a frame. | Either use iframe and CSS instead, or use server-side include to generate a complete page with various invariant parts. |
| `<u>` | It specifies an underlined text. | Text-decoration. |
| `<tt>` | Define telex text. | Use CSS properties. |
| `<s>` | Specify a crossing text. | Text-decoration. |

## HTML 弃用属性

几个标签属性也被移除。下面的表格已经删除了属性和它们相应的受影响的标签(元素)。这些属性已被永久移除的元素。

| 移除属性 | 标签 | 替代品 |
| --- | --- | --- |
| `启` | `a` | Use rel attribute. |
| `长desc` | `img`，`iframe` | 使用常规元素来链接到描述。 |
| `version` | `html` | 不必要，不要求提及。 |
| `Character set` | `a`，`link` | 改为在链接的资源上使用 HTTP Content-Type 头。 |
| `Name` | `a`，`img` | 使用 id 属性代替。 |
| `nohref` | `area` | 省略了 `href` 属性就足够了。`nohref` 属性是不必要的，不需要提及。 |
| `Use the map` | `input` | 使用 `img` 代替 `input` 进行影像地图。 |
| `Target` | `a` | 不必要，不要求提及。 |
| `Scheme` | `meta` | 每个字段只使用一个方案，或者使方案声明部分取值。 |
| `code type` | `object` | 使用 `data` 和 `type` 属性来调用插件。 |
| `Declaration` | `object` | 每次要重用资源时，完全重复 `object` 元素。 |
| `value` | `param` | 不声明值类型，使用 `name` 和 `value` 属性。 |
| `Language` | `script` | 使用了 `type` 属性。 |
| `Abbreviation` | `td`，`th` | 使用以明确简洁的方式开始的文本，并包括其后任何更详细的文本。 |
| `axis` | `td`，`th` | 应使用 `scope` 属性。 |