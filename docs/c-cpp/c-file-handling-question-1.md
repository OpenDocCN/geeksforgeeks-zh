# C |文件处理|问题 1

> 原文:[https://www.geeksforgeeks.org/c-file-handling-question-1/](https://www.geeksforgeeks.org/c-file-handling-question-1/)

关于 FILE *fp
**(A)** FILE 是 C 语言中表示文件的关键字，fp 是 FILE 类型的变量，以下哪一项正确？
**(B)** FILE 是一个结构，fp 是一个指向 FILE 类型的结构的指针
**(C)** FILE 是一个流
**(D)** FILE 是一个缓冲流

**回答:****(B)**【T29】
**解释:** fp 是一个 FILE 类型的指针，FILE 是一个存储打开文件的以下信息的结构。

```cpp
typedef struct {
  int level; /* fill/empty level of buffer */
  unsigned flags; /* File status flags */
  char fd; /* File descriptor */
  unsigned char hold; /* Ungetc char if no buffer */
  int bsize; /* Buffer size */
  unsigned char *buffer; /* Data transfer buffer */
  unsigned char *curp; /* Current active pointer */
  unsigned istemp; /* Temporary file indicator */
  short token; /* Used for validity checking */
}FILE;
```

[本题小考](https://www.geeksforgeeks.org/c-language-2-gq/file-handling-gq/)