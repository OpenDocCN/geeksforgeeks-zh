# 头文件名称中的注释？

> 原文:[https://www.geeksforgeeks.org/comment-in-header-file-name/](https://www.geeksforgeeks.org/comment-in-header-file-name/)

**如果头文件名称中有注释会怎么样？**
对“#include”的解析有点特殊，因为注释在中不被识别。因此，在`#include '中`/* '并不开始注释，该指令指定包含名为` x/*y '的系统头文件。当然，这样名称的头文件在 Unix 上不太可能存在，因为外壳通配符特性会使其难以操作。

以下是一些例子。

```cpp
#include <stdio.h>
int main()
{
  printf("This will compile");
  return 0;
}
```

输出:

```cpp
This will compile
```

```cpp
#include <stdio.h/*comment*/>
int main()
{
  printf("This will not compile");
  return 0;
}
```

输出:

```cpp
Error: stdio.h/*comment*/: No such file or directory
```

```cpp
#include <std/*comment*/io.h>
int main()
{
  printf("This will not compile either");
  return 0;
}
```

输出:

```cpp
Error: std/*comment*/io.h: No such file or directory
```

本文由 **Pankaj Boola** 供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论