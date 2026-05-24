# C |文件处理|问题 4

> 原文:[https://www.geeksforgeeks.org/c-file-handling-question-4/](https://www.geeksforgeeks.org/c-file-handling-question-4/)

在 fopen()中，打开模式“wx”有时是首选“w”，因为。

1)wx 的使用效率更高。
2)如果使用 w，文件的旧内容将被擦除，并创建一个新的空文件。当使用 wx 时，如果文件已经存在，fopen()将返回空值。
**(A)** 只有 1
**(B)** 只有 2
**(C)** 既有 1 又有 2
**(D)** 既没有 1 也没有 2

**回答:****(B)**

**解释:**参见[https://www . geekesforgeeks . org/fopen-1](https://www.geeksforgeeks.org/fopen-for-an-existing-file-in-write-mode/)