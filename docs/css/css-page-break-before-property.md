# CSS 分页前属性

> 原文:[https://www . geesforgeks . org/CSS-page-break-before-property/](https://www.geeksforgeeks.org/css-page-break-before-property/)

CSS 中的分页符属性用于在指定元素之前添加分页符。

此属性有助于定义文档打印时的行为。类似地，前分页符、后分页符和内分页符这三个属性都有助于确定并定义打印结果文档的方式。

**注意:**分页符属性不能用于绝对定位的元素或空元素。

**语法:**

```html
page-break-before: auto|always|avoid|left|right|initial|inherit;

```

**值**:

*   **自动:**指自动分页。

    ```html
    page-break-before: auto;

    ```

    ```html
    <!DOCTYPE html> 
    <html> 
    <head> 
        <title> 
            page-break-before: auto;
        </title> 
    </head> 

    <body> 
        <p style= "page-break-before:auto;"> 
            The oldest classical Greek and Latin 
            writing had little or no space between
            words and could be written in boustrophedon
            (alternating directions). Over time, text
            direction (left to right) became standardized,
            and word dividers and terminal punctuation 
            became common. 
        </p> 

        <p> 
            The oldest classical Greek and Latin 
            writing had little or no space between
            words and could be written in boustrophedon
            (alternating directions). Over time, text
            direction (left to right) became standardized,
            and word dividers and terminal punctuation 
            became common. 
        </p> 

        Text credits :https://en.wikipedia.org/wiki/Paragraph 
    </body> 
    </html>                     
    ```

*   **始终:**分页符始终插入指定元素框之后。

    ```html
    page-break-before:always;

    ```

    ```html
    <!DOCTYPE html> 
    <html> 
    <head> 
        <title> 
            page-break-before: always;
        </title> 
    </head> 

    <body> 
        <p style= "page-break-before:always;"> 
            The oldest classical Greek and Latin 
            writing had little or no space between
            words and could be written in boustrophedon
            (alternating directions).
        </p> 

        <p> 
            The oldest classical Greek and Latin 
            writing had little or no space between
            words and could be written in boustrophedon
            (alternating directions). Over time, text
            direction (left to right) became standardized,
            and word dividers and terminal punctuation 
            became common. 
        </p> 

        Text credits :https://en.wikipedia.org/wiki/Paragraph 
    </body> 
    </html>                     
    ```

*   **避免:**尽可能避免分页符。

    ```html
    page-break-before:avoid;

    ```

    ```html
    <!DOCTYPE html> 
    <html> 
    <head> 
        <title> 
            page-break-before: avoid;
        </title> 
    </head> 

    <body> 
        <p style= "page-break-before:avoid;"> 
            The oldest classical Greek and Latin 
            writing had little or no space between
            words and could be written in boustrophedon
            (alternating directions). Over time, text
            direction (left to right) became standardized,
            and word dividers and terminal punctuation 
            became common. 
        </p> 

        <p> 
            The oldest classical Greek and Latin 
            writing had little or no space between
            words and could be written in boustrophedon
            (alternating directions). Over time, text
            direction (left to right) became standardized,
            and word dividers and terminal punctuation 
            became common. 
        </p> 

        Text credits :https://en.wikipedia.org/wiki/Paragraph 
    </body> 
    </html>                     
    ```

*   **左:**插入分页符，使得下一页被描绘为左页。

    ```html
    page-break-before:left;

    ```

    ```html
    <!DOCTYPE html> 
    <html> 
    <head> 
        <title> 
            page-break-before: left;
        </title> 
    </head> 

    <body> 
        <p style= "page-break-before:left;"> 
            The oldest classical Greek and Latin 
            writing had little or no space between
            words and could be written in boustrophedon
            (alternating directions). Over time, text
            direction (left to right) became standardized,
            and word dividers and terminal punctuation 
            became common. 
        </p> 

        <p> 
            The oldest classical Greek and Latin 
            writing had little or no space between
            words and could be written in boustrophedon
            (alternating directions). Over time, text
            direction (left to right) became standardized,
            and word dividers and terminal punctuation 
            became common. 
        </p> 

        Text credits :https://en.wikipedia.org/wiki/Paragraph 
    </body> 
    </html>                     
    ```

*   **右:**插入分页符，使得下一页被描绘为右页。

    ```html
    page-break-before:right;

    ```

    ```html
    <!DOCTYPE html> 
    <html> 
    <head> 
        <title> 
            page-break-before: right;
        </title> 
    </head> 

    <body> 
        <p style= "page-break-before:right;"> 
            The oldest classical Greek and Latin 
            writing had little or no space between
            words and could be written in boustrophedon
            (alternating directions). Over time, text
            direction (left to right) became standardized,
            and word dividers and terminal punctuation 
            became common. 
        </p> 

        <p> 
            The oldest classical Greek and Latin 
            writing had little or no space between
            words and could be written in boustrophedon
            (alternating directions). Over time, text
            direction (left to right) became standardized,
            and word dividers and terminal punctuation 
            became common. 
        </p> 

        Text credits :https://en.wikipedia.org/wiki/Paragraph 
    </body> 
    </html>                     
    ```

*   **初始:**属性设为默认

    ```html
    page-break-before:initial

    ```

    ```html
    <!DOCTYPE html> 
    <html> 
    <head> 
        <title> 
            page-break-before:initial;
        </title> 
    </head> 

    <body> 
        <p style= "page-break-before:initial;"> 
            The oldest classical Greek and Latin 
            writing had little or no space between
            words and could be written in boustrophedon
            (alternating directions). Over time, text
            direction (left to right) became standardized,
            and word dividers and terminal punctuation 
            became common.  
        </p> 

        <p> 
            The oldest classical Greek and Latin 
            writing had little or no space between
            words and could be written in boustrophedon
            (alternating directions). Over time, text
            direction (left to right) became standardized,
            and word dividers and terminal punctuation 
            became common. 
        </p> 

        Text credits :https://en.wikipedia.org/wiki/Paragraph 
    </body> 
    </html>                     
    ```

*   **继承:**属性继承自父元素

    ```html
    page-break-before:inherit;

    ```

    ```html
    <!DOCTYPE html> 
    <html> 
    <head> 
        <title>css_page_break_before</title> 
        <style> 
            p { 
                page-break-before:always; 
            } 

            div{ 
                page-break-before:default; 
            } 

            #c1{ 
                page-break-before:left; 
            } 

            #c2{ 
                page-break-before:inherit; 
            } 
        </style> 
    </head> 

    <body> 
        <p> 
            The oldest classical Greek and Latin writing had little or 
            no space between words and could be written in boustrophedon 
            (alternating directions). Over time, text direction (left to 
            right) became standardized, and word dividers and terminal 
            punctuation became common. The first way to divide sentences 
            into groups was the original paragraphos, similar to an 
            underscore at the beginning of the new group.
        </p> 
        <div> 
            <p id="c2"> 
            Indented paragraphs demonstrated in the US Constitution 
            In ancient manuscripts, another means to divide sentences 
            into paragraphs was a line break (newline) followed by an 
            initial at the beginning of the next paragraph. An initial 
            is an oversized capital letter, sometimes outdented beyond 
            the margin of the text. This style can be seen, for example, 
            in the original Old English manuscript of Beowulf. 
            </p> 
        </div> 

        <p id="c1"> 
            A second common modern English style is to use no indenting, 
            but add vertical white space to create "block paragraphs." On 
            a typewriter, a double carriage return produces a blank line 
            for this purpose; professional typesetters (or word processing 
            software) may put in an arbitrary vertical space by adjusting 
            leading. 
        </p> 

        Text credits :https://en.wikipedia.org/wiki/Paragraph 
    </body> 
    </html>            
    ```

**注意:**分页前属性的结果最好通过选择给定 HTML 代码的网页打印预览来查看。在你的文本编辑器上创建一个类似的代码，比如记事本++并选择打印预览所创建的网页。为了更好的理解，一定要试一试。

**支持的浏览器:***CSS 断页属性*支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队