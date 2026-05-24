# 删除 C++ 中的关键字

> 原文:[https://www.geeksforgeeks.org/delete-in-c/](https://www.geeksforgeeks.org/delete-in-c/)

Delete 是一个 ***运算符*** ，用于**破坏新表达式创建的数组**和**非数组**(指针)**对象**。

*   可以通过使用 ***删除操作符*** 或 ***删除操作符*** 来删除
*   新操作符用于动态内存分配，将变量放在堆内存中。
*   这意味着删除操作符从堆中释放内存。
*   指向对象的指针不会被破坏，指针指向的值或内存块会被破坏。
*   删除运算符有 **void** 返回类型不返回值。

这里，下面是我们可以应用删除操作符的例子:
**1。删除** ***数组对象*** :我们用[]括号删除一个数组。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// Program to illustrate deletion of array
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Allocate Heap memory
    int* array = new int[10];

    // Deallocate Heap memory
    delete[] array;

    return 0;
}
```

**2。删除** [***空值***](https://www.geeksforgeeks.org/understanding-nullptr-c/) **指针**:删除空值不会导致任何变化，也不会出错。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to deleting
// NULLL pointer
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // ptr is NULL pointer
    int* ptr = NULL;

    // deleting ptr
    delete ptr;

    return 0;
}
```

**3。删除** ***指针*** **带值或不带值**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Creating int pointer
    int* ptr1 = new int;

    // Initializing pointer with value 20
    int* ptr2 = new int(20);

    cout << "Value of ptr1 = " << *ptr1 << "\n";
    cout << "Value of ptr2 = " << *ptr2 << "\n";

    delete ptr1; // Destroying ptr1
    delete ptr2; // Destroying ptr2

    return 0;
}
```

**输出:**

```cpp
Value of ptr1 = 0
Value of ptr2 = 20
```

**4。删除一** ***作废*** **指针**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <bits/stdc++.h>
using namespace std;
int main()
{
    void* ptr; // Creating void pointer

    delete ptr; // Destroying void pointer

    cout << "ptr deleted successfully";
    return 0;
}
```

**输出**:

```cpp
ptr deleted successfully
```

**5。删除由****动态分配的内存**

## **卡片打印处理机（Card Print Processor 的缩写）**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Dynamic memory allocated by using malloc
    int* ptr2 = (int*)malloc(sizeof(int));

    delete ptr2;

    cout << "ptr2 deleted successfully";

    return 0;
}
```

****输出**:**

```cpp
ptr2 deleted successfully
```

**虽然以上程序在 GCC 上运行良好。不建议对 malloc()使用 delete。
**6。删除** ***自定义数据类型*** 的变量:**

## **卡片打印处理机（Card Print Processor 的缩写）**

```cpp
#include <bits/stdc++.h>
using namespace std;

struct P {
    static void operator delete(void* ptr, std::size_t sz)
    {
        cout << "custom delete for size " << sz <<endl;
        delete (ptr); // ::operator delete(ptr) can also be used
    }
    static void operator delete[](void* ptr, std::size_t sz)
    {
        cout << "custom delete for size " << sz <<endl;
        delete (ptr); // ::operator delete(ptr) can also be used
    }
};

int main()
{
    P* var1 = new P;
    delete var1;

    P* var2 = new P[10];
    delete[] var2;
}
```

****输出**:**

```cpp
custom delete for size 1
custom delete for size 18
```

****例外**:
T3】1。试图删除非指针对象**

## **卡片打印处理机（Card Print Processor 的缩写）**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    int x;

    // Delete operator always
    // requires pointer as input
    delete x;

    return 0;
}
```

****输出**:**

```cpp
error: type ‘int’ argument given to ‘delete’, expected pointer
```

****2。试图删除指向本地堆栈分配变量的指针。****

## **卡片打印处理机（Card Print Processor 的缩写）**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    int x;
    int* ptr1 = &x;

    // x is present on stack frame as
    // local variable, only dynamically
    // allocated variables can be destroyed
    // using delete operator
    delete ptr1;

    return 0;
}
```

****输出**:**

```cpp
Runtime error
```