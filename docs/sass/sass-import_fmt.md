# SASS | @导入

> 原文: [https://www.geeksforgeeks.org/sass-import/](https://www.geeksforgeeks.org/sass-import/)

使用`@import`我们可以在我们的主文件中导入`SCSS`或`CSS`文件，所以基本上我们可以将多个文件组合在一起。

## 语法:

```html
@import 'Relative path to the file1', 'Relative path to the file2', ...;
```

我们不必包括路径中文件名后的`.scss`或`.css`扩展名。您可以导入任意多的文件。要了解相对路径，请浏览[这篇文章](https://www.geeksforgeeks.org/html-file-paths/)。

### 1. 将 SCSS 文件导入 SCSS 文件

这里我们在`.scss`文件名前加上`_`，这告诉`SASS`编译器该文件不应自行编译。

#### 优势:
这样做的主要优势是，我们可以使用`@import`组合多个文件，然后编译主文件。因此，我们将只有一个`CSS`文件，因此浏览器不必发出多个`HTTP`请求来加载不同的`CSS`文件。

```html
#aside_list {
  list-style-type: none;

  li {
    color: grey;
    text-align: center;
    width: 40px;
    height: 80px;
    background-color: lightpink;

    // Here & is parent selector
    &:hover {
      background-color: pink;
    }
  }
}
```

你可以省略导入的`.scss`文件的扩展名。

**输入 SCSS:**

```scss
@import "aside_list";
```

**输入 SCSS 编译后的输出 CSS:**

```css
#aside_list {
  list-style-type: none;
}

#aside_list li {
  color: grey;
  text-align: center;
  width: 40px;
  height: 80px;
  background-color: lightpink;
}

#aside_list li:hover {
  background-color: pink;
}
```

### 2. 将 CSS 文件导入 SCSS 文件

导入`CSS`文件与导入`.scss`文件类似，但你不能包含`.css`作为`CSS`文件的扩展名。主要原因是：`CSS`也有`@import`规则，其语法需要`.css`扩展名。

**段落 CSS:**

```css
p {
  color: red;
  font-size: 20px;
}
```

**输入 SCSS:**

```scss
@import 'paragraph';
```

**输入 SCSS 编译后的输出 CSS:**

```css
p {
  color: red;
  font-size: 20px;
}
```