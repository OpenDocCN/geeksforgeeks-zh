# 解释 Doctype 在 HTML 中的重要性？

> 原文:[https://www . geeksforgeeks . org/explain-of-doctype-in-html/](https://www.geeksforgeeks.org/explain-the-importance-of-doctype-in-html/)

**HTML 中的 Doctype:**[HTML Doctype](https://www.geeksforgeeks.org/html-doctypes/)最常写在整个 HTML 文档的第一个元素。它仍然包装在尖括号内，但它不是一个标签。它是一个声明或宣言。文档类型代表文档类型。这是一个声明文档类型的语句。借助这个语句，开发人员让浏览器知道下面的文档是一个 HTML 文档。

**Doctype 的含义:**Doctype 或文档类型声明(DTD)是一种指令，它告诉网络浏览器当前页面所用的标记语言。Doctype 不是一个元素或标签，它让浏览器知道文档中使用的 HTML 或任何其他标记语言的版本或标准。

**语法:**在 HTML5 中，声明 doctype 的语法非常简单，但在 HTML4.0.1 或 XHTML 1.1 等旧版本中，它稍微复杂一点。

**HTML 5 及以上版本:**

```html
<!DOCTYPE html>
```

**在 HTML 4.0.1 中严格:**在 HTML 4.01 严格文档类型定义(DTD)中，所有那些没有出现在框架集文档中或没有被否决的元素和属性都包括在内。

```html
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN"  
             "http://www.w3.org/TR/html4/strict.dtd">
```

**在 HTML 4.0.1 中 Transitional:** 在 HTML 4.01 中 Transitional 文档类型定义(DTD)允许一些已经被弃用的旧 PUBLIC 属性。

```html
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" 
                     "http://www.w3.org/TR/html4/loose.dtd">
```

**在 HTML 4.01 框架集中:**在 HTML 4.01 框架集文档类型定义(DTD)中，可以使用框架。

```html
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Frameset//EN" 
                   "http://www.w3.org/TR/html4/frameset.dtd">
```

**在 XHTML 1.1 中:**在 XHTML 1.1 严格文档类型定义(DTD)中，不支持不推荐使用的标签，代码必须按照 XML 规范编写。

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.1//EN"  
                  "http://www.w3.org/TR/xhtml11/DTD/xhtml11.dtd">
```

**在 XHTML 1.0 中:**

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" 
             "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
```

**注意:**XHTML 1.1 和 XHTML 1.0 也有各自的严格、过渡和框架集类型声明。

**有用提示:**

*   In HTML5, if developers skip adding doctype declarations, the system will automatically add them at runtime.
*   Doctype declarations are case insensitive.

```html
<!-- All of them are correct conventions-->

<!DOCTYPE html>
<!DocType html>
<!Doctype html>
<!doctype html>
```

**Doctype 声明的意义:**

*   Doctype forces browsers to do their best to follow the exact specifications in HTML documents when rendering.
*   Prevent the browser from switching to quirk mode (nonstandard behavior of layout in Navigator 4 and Internet Explorer 5)