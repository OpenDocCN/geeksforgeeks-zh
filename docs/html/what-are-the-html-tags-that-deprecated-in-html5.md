# HTML 5 中有哪些不推荐使用的 HTML 标签？

> 原文:[https://www . geeksforgeeks . org/html 5 中不推荐使用的 html 标记是什么/](https://www.geeksforgeeks.org/what-are-the-html-tags-that-deprecated-in-html5/)

在本文中，我们将看到各种不推荐使用的 Html 标签&它们在 HTML5 中的替代标签。不推荐使用的标签是那些允许使用但不推荐使用的标签，并且正在被更新的标签所取代。当以其他方式实现相同的属性时，标记或属性会贬值。被丢弃的几个原因&使用较新的一个:

*   有几个标签可以帮助完成同样的任务。由于这个原因，源代码的长度也减少了&因此提高了整体性能。
*   管理大尺寸代码将是困难的&修改这样的源代码不可能一蹴而就。这可能会增加开发时间以及代码的模糊性。
*   有时，如果我们需要使用特定的代码块来执行特定的任务，那么我们可能需要重新编写代码，这种情况可能会发生。所有这些因素都有助于增加复杂性以及不值得开发过程的开发时间。

为此，在 HTML5 中引入了几个标签和属性。下面是不推荐使用的标签的完整列表，将在下面讨论。
**HTML 5 不推荐使用的标签:**下面给出了不推荐使用的标签的完整列表。

<figure class="table">[**<basefont>**](https://www.geeksforgeeks.org/html-basefont-tag/)

| 

#### **标签**

 | 

#### **描述**

 | 

#### 替代标签

 |
| --- | --- | --- |
| To specify a base font. | Font style sheet. |
| [**<字体>**](https://www.geeksforgeeks.org/html-font-tag/#:~:text=HTML%20Tag,-Difficulty%20Level%20%3A%20Basic&text=The%20tag%20plays%20an,same%20size%2C%20color%20and%20face.) | It specifies the text, size and color of the font. | Family, font size and color. |
| [**<居中>**](https://www.geeksforgeeks.org/html-center-tag/#:~:text=HTML%20Tag,-Difficulty%20Level%20%3A%20Basic&text=The%20tag%20in%20HTML,the%20center%20tag%20in%20HTML5.) | It specifies a centered text. | Text-Alignment: Center. |
| [**<击>**](https://www.geeksforgeeks.org/html-strike-tag/#:~:text=HTML%20Tag,-Difficulty%20Level%20%3A%20Basic&text=It%20defines%20a%20strike%20or,cut%20line%20in%20the%20text.) | It specifies a punch-through text. | Text-decoration. |
| [**<大>**](https://www.geeksforgeeks.org/html-big-tag/#:~:text=The%20tag%20in%20HTML,can%20be%20used%20by%20CSS.) | Define Daimonji. | Use CSS attributes or title tags. |
| [**< 说 >**](https://www.geeksforgeeks.org/html-dir-tag/#:~:text=HTML%20Tag,-Difficulty%20Level%20%3A%20Basic&text=It%20is%20used%20to%20make,instead%20of%20tag.) | It specifies a directory list. | Ul label. |
| [**<是指数>**T3】](https://www.geeksforgeeks.org/html-isindex-tag/) | It specifies a single-line input field. | Form a mark. |
| [**< applet >**](https://www.geeksforgeeks.org/html-applet-tag/) | It specifies an applet. | Object label. |
| [**< Abbreviations >**](https://www.geeksforgeeks.org/html-acronym-tag/#:~:text=The%20tag%20in%20HTML,systems%2C%20and%20search%2Dengines.&text=title%3A%20It%20is%20used%20to%20specify%20extra%20information%20about%20the%20element.) | Abbreviations are defined with this label. | Use abbreviations |
| [**<无框>**T3】](https://www.geeksforgeeks.org/html-noframes-tag/) | It is used to define the noframe section. | Or use iframe and CSS instead, or use server-side include to generate a complete page with various invariant parts. |
| [**<【xmp】>**](https://www.geeksforgeeks.org/html-xmp-tag/) | Render the text between the opening and closing tags, without interpreting the middle HTML and using a constant-width font. | Use pre and code instead. |
| [**<无嵌入>**T3】](https://www.geeksforgeeks.org/html-noembed-tag/) | A tag can easily provide alternative content and tell users what they are missing. | When rollback is needed, use objects instead of embedding. |
| **< Plain text >** | Used to present all the text in the document exactly as it was typed. | Use "text/normal" MIME type instead. |
| [**< Frame set >**](https://www.geeksforgeeks.org/html-frameset-tag/#:~:text=The%20tag%20in%20HTML,can%20hold%20a%20separate%20document.) | It specifies a set of frames. | Or use iframe and CSS instead, or use server-side include to generate a complete page with various invariant parts. |
| [**<框架>**](https://www.geeksforgeeks.org/html-frame-tag/) | It specifies a frame. | Either use iframe and CSS instead, or use server-side include to generate a complete page with various invariant parts. |
| [**<u>**T3】](https://www.geeksforgeeks.org/html-u-tag/#:~:text=The%20tag%20in%20HTML,used%20to%20underline%20misspelled%20words.) | It specifies an underlined text. | Text-decoration. |
| [**<【TT】>**](https://www.geeksforgeeks.org/html-tt-tag/#:~:text=The%20tag%20is%20the,mainly%20used%20for%20formatting%20purposes.) | Define telex text. | Use CSS properties. |
| [**<s>**T3】](https://www.geeksforgeeks.org/html-s-tag/) | Specify a crossing text. | Text-decoration. |

</figure>

**HTML 弃用属性** : 几个标签属性也被移除。下面的表格已经删除了属性和它们相应的受影响的标签(元素)。这些属性已被永久移除的元素。

<figure class="table">

| 

#### 移除属性

 | 

#### 标签压印

 | 

#### 替代品

 |
| --- | --- | --- |
| [**启**](https://www.geeksforgeeks.org/html-s-tag/) | 伊林克 | Use rel attribute.

 |
| [T1】长 descT3】](https://www.geeksforgeeks.org/html-iframe-longdesc-attribute/) | img，iframe | 使用常规元素来链接到描述。 |
| **version** | 超文本标记语言 | 不必要，不要求提及。 |
| [**Character set**](https://www.geeksforgeeks.org/html-charsets/) | I. Link | 改为在链接的资源上使用 HTTP Content-Type 头。 |
| [**Name**](https://www.geeksforgeeks.org/html-name-attribute/) | 一、img | 使用 id 属性代替。 |
| **nohref** | district | 省略了 href 属性就足够了。nohref 属性是不必要的，不需要提及。 |
| [**Use the map**](https://www.geeksforgeeks.org/html-usemap-attribute/) | input | 使用 img 代替输入进行影像地图。 |
| [**Target**](https://www.geeksforgeeks.org/html-target-attribute/) | interlinkage | 不必要，不要求提及。 |
| [**Scheme**](https://www.geeksforgeeks.org/html-meta-scheme-attribute/) | Yuan Dynasty (1206-1368) | 每个字段只使用一个方案，或者使方案声明部分取值。

 |
| **code type** | target | 使用数据和类型属性来调用插件。 |
| **Declaration** | target | 每次要重用资源时，完全重复对象元素。 |
|  | target | 优化链接的资源，使其快速加载，或者至少增量加载。 |
| **值类型** | 参数 | 不声明值类型，使用名称和值属性。 |
| [**Language**](https://www.geeksforgeeks.org/html-lang-attribute/#:~:text=This%20attribute%20is%20used%20to,%2C%20es%20for%20Spanish%2C%20etc.&text=Attribute%20Value%3A%20This%20attribute%20contains,specify%20the%20language%20of%20content.) | script | 使用了类型属性。 |
| [**Abbreviation**](https://www.geeksforgeeks.org/html-abbr-tag/#:~:text=The%20tag(Abbreviation,systems%2C%20and%20search%2Dengines.) | td，th | 使用以明确简洁的方式开始的文本，并包括其后任何更详细的文本。 |
| **axis** | td，th | 应使用范围属性。 |

</figure>