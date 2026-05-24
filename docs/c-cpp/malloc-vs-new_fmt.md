# malloc()与new的比较

> 原文：[https://www.geeksforgeeks.org/malloc-vs-new/](https://www.geeksforgeeks.org/malloc-vs-new/)

下面是 `malloc()` 和 `operator new` 之间的区别。

1.  **调用构造函数**：`new` 会调用构造函数，而 `malloc()` 不会。事实上，即使是基本数据类型（如 `char`、`int`、`float` 等）也可以用 `new` 进行初始化。例如，下面的程序会输出 10。

## CPP

```cpp
#include<iostream>
using namespace std;
int main()
{
    // 使用 new() 进行初始化
    int *n = new int(10);
    cout << *n;
    getchar();
    return 0;
}
```

**输出：**

（输出内容为空）

**2. 运算符 vs 函数**：`new` 是运算符，而 `malloc()` 是函数。

**3. 返回类型**：`new` 返回确切的数据类型，而 `malloc()` 返回 `void*`。

**4. 失败条件**：失败时，`malloc()` 返回 `NULL`，而 `new` 则抛出 `bad_alloc` 异常。

**5. 内存分配区域**：如果是 `new`，内存从自由存储区（free store）分配；在 `malloc()` 中，内存分配是从堆（heap）中完成的。

**6. 大小计算**：所需的内存大小由编译器为 `new` 自动计算，而我们必须为 `malloc()` 手动计算大小。

**7. 缓冲区大小调整**：`malloc()` 允许使用 `realloc()` 更改缓冲区大小，而 `new` 则不允许。

| `new` | `malloc()` |
| :--- | :--- |
| 调用构造函数。 | 不调用构造函数。 |
| 它是一个运算符。 | 它是一个函数。 |
| 返回确切的数据类型。 | 返回 `void*`。 |

如果你在上面的帖子中发现任何不正确的地方，或者你想分享更多关于上面讨论的主题的信息，请写评论。