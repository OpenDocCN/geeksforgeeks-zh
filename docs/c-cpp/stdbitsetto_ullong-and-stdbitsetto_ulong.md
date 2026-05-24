# c++ STL 中的 std::bitset::to_ullong 和 STD::bit set::to _ ulong

> 原文:[https://www . geesforgeks . org/stdbitsetto _ ullong-and-stdbitsetto _ ulong/](https://www.geeksforgeeks.org/stdbitsetto_ullong-and-stdbitsetto_ulong/)

**位集:**位集是 bool 的数组，但每个布尔值并不单独存储，而是位集优化了空间，使得每个 bool 只占用 1 位空间，因此位集 bs 占用的空间小于 bool bs[N]和向量 bs(N)占用的空间。然而，位集的一个限制是，N 在编译时必须是已知的，即常数(向量和动态数组没有这个限制)

**std::bitset::to_ullong**

此函数将位集的内容转换为无符号长整型。位组的第一位对应于数字的最低有效位，最后一位对应于最高有效位。

**语法:**

```cpp
bit.to_ullong()

```

这里，比特是以比特为单位的数字(即，101 代表 5)

> **参数:**
> 
> *   We are not passing any parameters
>     
>     **返回:**
>     
>     *   Return the converted integer.
>     
>     **异常:**
>     
>     *   如果值不能用无符号长整型表示，将会发生 overflow_error。

示例:

```cpp
Input : 1010
Output : 10

```

```cpp
Input : 10000001
Output :129

```

**#代码 1 :**

```cpp
#include <bitset> 
#include <iostream> 
#include <limits> 
using namespace std; 

int main() 
{ 
    bitset<numeric_limits<unsigned long long>::digits> b(10); 

    cout << b << endl << b.to_ullong();

    return 0; 
}

//Code is improved by Rajnis09
```

**输出:**

```cpp
0000000000000000000000000000000000000000000000000000000000001010  
10

```

**#代码 2 :**

```cpp
#include <bitset>
#include <iostream>
#include <limits>
using namespace std;

int main()
{
    bitset<numeric_limits<unsigned long long>::digits> b(20);

    cout << b << endl << b.to_ullong();

    return 0;
}
```

**输出:**

```cpp
0000000000000000000000000000000000000000000000000000000000010100 
20

```

**std::bitset::to_ulong**

此函数将位集的内容转换为无符号长整数。位组的第一位对应于数字的最低有效位，最后一位对应于最高有效位。

**语法:**

```cpp
bit.to_ulong()

```

这里，比特是以比特为单位的数字(即，101 代表 5)

> **参数:**
> 
> *   We are not passing any parameters
>     
>     **返回:**
>     
>     *   Return the converted integer.
>     
>     **相关异常:**
>     
>     *   如果值不能用无符号长整型表示，将会出现 overflow_error。

示例:

```cpp
Input : 1010

Output : 10

```

```cpp
Input : 10000001
Output :129

```

**#代码 1 :**

```cpp
#include <bitset>
#include <iostream>
#include <limits>
using namespace std;

int main()
{
    bitset<numeric_limits<unsigned long>::digits> b(10);

    cout << b << endl << b.to_ulong();

    return 0;
}
```

**输出:**

```cpp
0000000000000000000000000000000000000000000000000000000000001010  
10

```

**#代码 2 :**

```cpp
#include <bitset>
#include <iostream>
#include <limits>
using namespace std;

int main()
{
    bitset<numeric_limits<unsigned long>::digits> b(20);

    cout << b << endl << b.to_ulong();

    return 0;
}
```

**输出:**

```cpp
0000000000000000000000000000000000000000000000000000000000010100 
20

```