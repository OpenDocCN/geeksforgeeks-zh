# C |字符串|问题 7

> 原文:[https://www.geeksforgeeks.org/c-string-question-7/](https://www.geeksforgeeks.org/c-string-question-7/)

在下面的程序中，你会用什么来代替“？”打印“测验”？

```cpp
#include <stdio.h>
int main() 
{ 
  char arr[] = "GeeksQuiz"; 
  printf("%s", ?); 
  return 0; 
}
```

**(A)**arr
**(B)**(arr+5)
**(C)**(arr+4)
**(D)**不可能

**回答:****(B)**

**解释:**由于使用了%s，printf 语句将打印从 arr+5 开始的所有内容，直到找到“\0”