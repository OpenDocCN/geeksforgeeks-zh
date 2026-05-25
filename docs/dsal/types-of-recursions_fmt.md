# 递归类型

> 原文：[https://www.geeksforgeeks.org/types-of-recursions/](https://www.geeksforgeeks.org/types-of-recursions/)

## 什么是递归？

函数直接或间接调用自身的过程称为递归，对应的函数称为递归函数。使用递归算法，某些问题可以很容易地解决。此类问题的示例有河内（TOH）塔、[有序/前序/后序树遍历](https://www.geeksforgeeks.org/tree-traversals-inorder-preorder-and-postorder/)、[图的 DFS](https://www.geeksforgeeks.org/depth-first-traversal-for-a-graph/)等。

## 递归的类型

递归主要有两种类型，这取决于一个函数是从自身内部调用自身还是多个函数相互调用。第一个叫直接递归，另一个叫间接递归。因此，递归的两种类型是：

### 1. 直接递归

可以进一步分为四种类型：

#### 尾部递归

如果一个递归函数调用自己，并且这个递归调用是函数中的最后一个语句，那么它被称为尾部递归。调用后，递归函数不执行任何操作。该函数必须在调用时处理或执行任何操作，并且在返回时不执行任何操作。

**例：**

```cpp
// Code Showing Tail Recursion
#include <iostream>
using namespace std;

// Recursion function
void fun(int n)
{
    if (n > 0) {
        cout << n << " ";

        // Last statement in the function
        fun(n - 1);
    }
}

// Driver Code
int main()
{
    int x = 3;
    fun(x);
    return 0;
}

// This code is contributed by shubhamsingh10
```

```c
// Code Showing Tail Recursion

#include <stdio.h>

// Recursion function
void fun(int n)
{
    if (n > 0) {
        printf("%d ", n);

        // Last statement in the function
        fun(n - 1);
    }
}

// Driver Code
int main()
{
    int x = 3;
    fun(x);
    return 0;
}
```

```java
// Java code Showing Tail Recursion
class GFG {

  // Recursion function
  static void fun(int n)
  {
    if (n > 0)
    {
      System.out.print(n + " ");

      // Last statement in the function
      fun(n - 1);
    }
  }

  // Driver Code
  public static void main(String[] args)
  {
    int x = 3;
    fun(x);
  }
}

// This code is contributed by pratham76.
```

```python
# Code Showing Tail Recursion

# Recursion function
def fun(n):
    if (n > 0):
        print(n, end=" ")
        # Last statement in the function
        fun(n - 1)

# Driver Code
x = 3
fun(x)

# This code is contributed by Shubhamsingh10
```

```csharp
// C# code Showing Tail Recursion
using System;

class GFG
{

  // Recursion function
  static void fun(int n)
  {
    if (n > 0)
    {
      Console.Write(n + " ");

      // Last statement in the function
      fun(n - 1);
    }
  }

  // Driver Code
  public static void Main(string[] args)
  {
    int x = 3;
    fun(x);
  }
}

// This code is contributed by rutvik_56
```

```javascript
<script>
// Javascript code Showing Tail Recursion
  // Recursion function
   function fun(n)
  {
    if (n > 0)
    {
      document.write(n + " ");

      // Last statement in the function
      fun(n - 1);
    }
  }

  // Driver Code

    var x = 3;
    fun(x);

// This code is contributed by shivanisinghss2110
</script>
```

**Output:**

```
3 2 1
```