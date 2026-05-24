# 程序按相反顺序从 N 到 1 打印数字

> 原文：[https://www.geeksforgeeks.org/program-to-print-numbers-from-n-to-1-in-reverse-order/](https://www.geeksforgeeks.org/program-to-print-numbers-from-n-to-1-in-reverse-order/)

给定一个数字 `N`，任务是打印从 `N` 到 `1` 的数字。

## 示例

> **输入：** `N = 10`
> **输出：** `10 9 8 7 6 5 4 3 2 1`
>
> **输入：** `N = 7`
> **输出：** `7 6 5 4 3 2 1`

## 方法 1

运行从 `N` 到 `1` 的循环，并打印每次迭代的 `N` 值。每次迭代后，将 `N` 的值减 `1`。
以下是上述办法的实施情况。

### C++

```cpp
// C++ program to print all numbers between 1
// to N in reverse order

#include <bits/stdc++.h>
using namespace std;

// Recursive function to print from N to 1
void PrintReverseOrder(int N)
{

    for (int i = N; i > 0; i--)
        cout << i << " ";

}

// Driven Code
int main()
{
    int N = 5;

    PrintReverseOrder(N);

    return 0;
}
```

### Java

```java
// Java program to print all numbers between 1
// to N in reverse order
import java.util.*;

class GFG {

// Recursive function to print from N to 1
static void PrintReverseOrder(int N)
{

    for (int i = N; i > 0; i--)
        System.out.print(i + " ");
}

// Driver code
public static void main(String[] args)
{
    int N = 5;

    PrintReverseOrder(N);
}
}

// This code is contributed by shivanisinghss2110
```

### Python 3

```python
# Python3 program to print all numbers
# between 1 to N in reverse order

# Recursive function to print
# from N to 1
def PrintReverseOrder(N):

    for i in range(N, 0, -1):
        print(i, end = " ");

# Driver code
if __name__ == '__main__':

    N = 5;
    PrintReverseOrder(N);

# This code is contributed by 29AjayKumar
```

### C#

```csharp
// C# program to print all numbers
// between 1 to N in reverse order
using System;

class GFG{

// Recursive function to print
// from N to 1
static void PrintReverseOrder(int N)
{
    for(int i = N; i > 0; i--)
       Console.Write(i + " ");
}

// Driver code
public static void Main(String[] args)
{
    int N = 5;

    PrintReverseOrder(N);
}
}

// This code is contributed by Rajput-Ji
```

### JavaScript

```javascript
<script>

    // Javascript program to print all numbers between 1
    // to N in reverse order

    // Recursive function to print from N to 1
    function PrintReverseOrder(N)
    {

        for (let i = N; i > 0; i--)
            document.write(i + " ");

    }

     let N = 5;

    PrintReverseOrder(N);

</script>
```

## 输出

```
5 4 3 2 1
```