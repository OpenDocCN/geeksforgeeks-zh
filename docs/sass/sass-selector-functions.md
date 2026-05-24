# SASS |选择器功能

> 原文:[https://www.geeksforgeeks.org/sass-selector-functions/](https://www.geeksforgeeks.org/sass-selector-functions/)

选择器函数有助于检查和更改样式表中的 CSS 选择器。除了 selector-nest()之外，所有函数都禁止使用父选择器。

1.  **selector-nest($ selecters…):**这个方法根据给定的列表返回一个包含 CSS 选择器嵌套列表的新选择器。
    *   **例:**

        ```html
        selector-nest(".warning", "alert", "div")
        ```

    *   **输出:**

        ```html
        .warning div, alert div
        ```

2.  **selector-parse($ selector):**该方法使用与父选择器相同的格式返回包含在“selector”中的字符串列表。
    *   **例:**

        ```html
        selector-parse("h1 .myInput .warning")
        ```

    *   **输出:**

        ```html
        ('h1' '.myInput' '.warning')
        ```

3.  **选择器-unify($selector1，$selector2):** 这个方法返回一个新的选择器，它只匹配由 selector1 和 selector2 匹配的元素。
    *   **例 1:**

        ```html
        selector-unify("myInput", ".disabled")
        ```

    *   **输出:**

        ```html
        myInput.disabled
        ```

    *   **例 2:**

        ```html
        selector-unify("p", "h1")
        ```

    *   **输出:**

        ```html
        NULL
        ```

4.  **简单选择器($selector):** 这个方法返回“selector”中存在的单个选择器的列表，它应该是一个复合选择器。
    *   **例:**

        ```html
        simple-selectors("div.myInput")
        ```

    *   **输出:**

        ```html
        div, .myInput
        ```

5.  **是-superselector($super，$sub):** 这个方法返回一个布尔值，告诉“super”中给出的选择器是否匹配“sub”中给出的所有元素。
    *   **例 1:**

        ```html
        is-superselector("div", "div.myInput")
        ```

    *   **输出:**

        ```html
        true
        ```

    *   **例 2:**

        ```html
        is-superselector("div.myInput", "div")
        ```

    *   **输出:**

        ```html
        false
        ```

6.  **选择器-替换($selector，$original，$replacement):** 这个方法返回一个新的选择器，用“replacement”中给出的选择器代替“original”中给出的选择器。
    *   **例:**

        ```html
        selector-replace("p.hello", "p", "q")
        ```

    *   **输出:**

        ```html
        q.hello
        ```

7.  **selector-append($ selecters):**这个方法返回一个新的选择器，第二个和下一个选择器被附加到第一个选择器上，没有任何空格。
    *   **例 1:**

        ```html
        selector-append("div", ".myInput")
        ```

    *   **输出:**

        ```html
        div.myInput
        ```

    *   **例 2:**

        ```html
        selector-append(".warning", "__a")
        ```

    *   **输出:**

        ```html
        warning__a
        ```

8.  **selector-extend($selector，$extendee，$extender):** 这个方法将$selector 扩展为@extend 规则。它返回用以下@extend 规则修改的$selector 的副本:

    ```html
    #{$extender} {
        @extend #{$extendee};
    }
    ```