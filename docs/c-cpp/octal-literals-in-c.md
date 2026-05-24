# C 语言中的八进制文字

> 原文:[https://www.geeksforgeeks.org/octal-literals-in-c/](https://www.geeksforgeeks.org/octal-literals-in-c/)

当我们通过在一个数字前加“0”来初始化一个值时，这个数字被视为八进制。例如，“10”被读取为 10，而“010”被读取为 8。

示例:

```cpp
Input : 0101
Output : 65

Input : 01010
Output : 520

```

```cpp
#include<iostream>
using namespace std;
int main()
{  
    int x = 0101; 
    cout << x; 
    return 0;
}
```

**Output:**

```cpp
65

```

```cpp
#include<iostream>
using namespace std;
int main()
{  
    int x = 020; 
    cout << x; 
    return 0;
}
```

**Output:**

```cpp
16

```

```cpp
#include<iostream>
using namespace std;
int main()
{  
    int x = 090; 
    cout << x; 
    return 0;
}
```

输出:

```cpp
Compiler Error : 9 is not a valid digit in octal number.

```