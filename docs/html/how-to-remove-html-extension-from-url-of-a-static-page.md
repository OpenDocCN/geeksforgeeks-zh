# 如何去除。静态页面网址的 html 扩展？

> 原文:[https://www . geesforgeks . org/如何从静态页面的 url 中删除 html 扩展/](https://www.geeksforgeeks.org/how-to-remove-html-extension-from-url-of-a-static-page/)

网站上的所有页面都有一个由 HTML 给出的结构。HTML 为网页上的内容、文本、表格、标题和列表提供了结构，使网页易于阅读。当保存一个 html 文档时，它有一个扩展名为. HTML。因此，网站的网址有一个**。html** 扩展。那个。通过编辑**，可以轻松移除 html 扩展。htaccess 文件**。

**。htaccess 文件:***。htaccess 文件*是用记事本这样的文本编辑器创建的。这是一个简单的 ASCII 文件，让服务器知道每个目录下要进行哪些配置更改。

> **注:**该。htaccess 是文件的全名。不是**文件访问**，只是**。htaccess** 。

**去除。html 扩展:**删除。来自网址的 html 扩展。例如:
从

```html
example.com/content.html
```

到

```html
example.com/content
```

**你要按照这些步骤:**

*   登录 cPanel 帐户。
*   在 ***文件*** 部分，点击 ***文件管理器*** 图标。
*   点击右上角 ***设置*** 按钮。
*   如果您想在主域中进行更改，请单击 ***网络根*** 旁边的单选按钮。如果要在其他域上进行更改，请单击下拉菜单并找到要进行更改的域。
*   记得勾选 ***【显示隐藏文件】*** 旁边的复选框。现在点击 ***保存*** 按钮返回文件管理器窗口。
*   现在你已经在你选择进行更改的域的 ***根文件夹*** 中了。搜索 ***。htaccess 文件*** 并右击它。点击菜单中的 ***编辑*** 选项。现在，您可以将代码添加到。htaccess 文件。
*   在**内添加以下代码。htaccess 文件**:

## 超文本标记语言

```html
#remove html file extension https://example.com/page.html
# to https://example.com/page
RewriteEngine On
RewriteCond %{REQUEST_FILENAME} !-d
RewriteCond %{REQUEST_FILENAME} !-f
RewriteRule ^([^\.]+)$ $1.html [NC, L]
```

*   点击 ***保存更改*** 按钮，然后点击 ***关闭*** 按钮。

您现在可以链接 HTML 文档中的任何页面，而不需要添加页面的扩展名，因为现在在网站的网址中看不到扩展名。

**示例:**

```html
<a href="http://example.com/image" title="image">image</a>
```

搜索引擎可以将这些页面索引为重复内容，为了克服这一点，在 HTML 文件中添加一个<canonical>元标签。</canonical>

**示例:**

```html
<link rel="canonical" href="https://example.com/blog/first-blog" />
```