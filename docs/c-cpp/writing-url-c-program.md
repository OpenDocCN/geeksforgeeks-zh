# 在 C++ 程序中写一个 URL

> 原文:[https://www.geeksforgeeks.org/writing-url-c-program/](https://www.geeksforgeeks.org/writing-url-c-program/)

用编程代码写 URL 不会影响程序，编译器也不会抛出任何错误。

## C++

```cpp
// C++ program to demonstrate URL in code
#include <iostream>
using namespace std;

int main()
{
    https://www.geeksforgeeks.org/

    for (int i = 0; i < 5; i++)
    {
        cout << "This code is error free" << endl ;

        // Uncommenting below goto statement causes 
        // infinite loop
        // goto http;
    }

    return 0;
}
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```cpp
<?php
// PHP program to demonstrate
// URL in code

https://www.geeksforgeeks.org/

for ($i = 0; $i < 5; $i++)
{
    echo "This code is error " . 
                 "free" , "\n" ;

    // Uncommenting below 
    // goto statement causes 
    // infinite loop

    // goto https;
}

// This code is contributed
// by m_kit
?>
```

**Output:**

```cpp
This code is error free
This code is error free
This code is error free
This code is error free
This code is error free

```

**说明:**

1.  在程序中，任何后跟:的标识符都成为(转到)[标签。](https://www.geeksforgeeks.org/local-labels-in-c/)
2.  单行注释在 https://www.geeksforgeeks.org/以//等开头，因此它是一个注释。因此:

    ```cpp
    label- http:

    comment- www.geeksforgeeks.org/

    ```

本文由 **MAZHAR IMAM KHAN** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。