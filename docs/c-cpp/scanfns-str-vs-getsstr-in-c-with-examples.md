# scanf("%[^\n]s，str)vs get(str)用 c 举例

> 原文:[https://www . geesforgeks . org/scan fns-str-vs-getsstr-in-c-with-examples/](https://www.geeksforgeeks.org/scanfns-str-vs-getsstr-in-c-with-examples/)

### [<u>大干()</u>](https://www.geeksforgeeks.org/fgets-gets-c-language/)

*   get 是读取包含空格的文本字符串的更方便的方法。
*   与 scanf()不同，它不跳过空格。
*   它用于读取输入，直到遇到换行符。

### <u>%[^\n]</u>

*   这是一个编辑转换代码。
*   编辑转换代码%[^\n]可以用作 get 的替代。
*   c 语言通过 scanf()函数支持这种格式规范。
*   这个编辑转换代码可以用来读取包含变量甚至空格等字符的行。
*   一般来说，格式规范为%s，字段宽度为%ws 的 scanf()函数可以是只读字符串，直到非空白部分。
*   这意味着它们不能用于阅读包含多个单词的文本，尤其是空白。

### 【gets()和%[^\n 之间的异同表]

<figure class="table">终止

| 获取() | %[^\n] |
| --- | --- |
| get()用于读取字符串 | %[^\n】是一个编辑转换代码，用于读取字符串 |
| 与 scanf()不同，get()读取字符串时即使带有空格 | %[^\n】也读取带有空格的字符串 |
| 当它读取一个换行符时那么 get()函数将被终止 | %[^\n】也以换行符 |

</figure>