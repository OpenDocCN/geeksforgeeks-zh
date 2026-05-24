# SASS | @导入

> 原文:[https://www.geeksforgeeks.org/sass-import/](https://www.geeksforgeeks.org/sass-import/)

使用@import 我们可以在我们的主文件中导入 SCSS 或 CSS 文件，所以基本上我们可以将多个文件组合在一起。

**语法:**

```html
 @import 'Relative path to the file1', 'Relative path to the file2', ...; 
```

我们不必包括。SCS 或。路径中文件名后的 css 扩展名。您可以导入任意多的文件。要了解相对路径，请浏览[这篇文章](https://www.geeksforgeeks.org/html-file-paths/)。

1.  **Importing SCSS file into SCSS file:**
    Here we put **_** before the name of the **.scss file** which tells the SASS compiler that the file should not compile on its own.

    **优势:**
    这样做的主要优势是，我们可以使用@import 组合多个文件，然后编译主文件。因此，我们将只有一个 CSS 文件，因此浏览器不必发出多个 HTTP 请求来加载不同的 CSS 文件。
    T4

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

    你可以离开。导入。scss 文件。

    **输入. SCS**

    ```html
    @import "aside_list";

    ```

    **输入. scss:输出. css 的编译文件**

    ```html
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

2.  **Importing CSS file into SCSS file:**
    Importing CSS file is similar to importing .scss file but you must not include .css as the extension of CSS file. The main reason for this is: CSS also have @import rule which has .css extension syntax.

    **段落. css**

    ```html
    p {
      color: red;
      font-size: 20px;
    }
    ```

    **输入. SCS**

    ```html
    @import 'paragraph';
    ```

    **输入. scss:输出. css 的编译文件**

    ```html
    p {
      color: red;
      font-size: 20px;
    }

    ```