# C |文件处理|问题 5

> 原文:[https://www.geeksforgeeks.org/c-file-handling-question-5/](https://www.geeksforgeeks.org/c-file-handling-question-5/)

fseek()应该优先于 rewind()主要是因为
**(A)** rewind()对于空文件
**(B)** rewind()对于大文件
**(C)** 可能会失败在 rewind 中，无法检查操作是否成功完成
**(D)** 以上所有的

**答案:****(C)**
【T29】