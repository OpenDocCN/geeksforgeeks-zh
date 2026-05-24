# 如何用一个比较来检查一个数字是否在[低，高]范围内？

> 原文:[https://www . geeksforgeeks . org/如何检查数字是否在范围内 a-b-使用一个比较/](https://www.geeksforgeeks.org/how-to-check-whether-a-number-is-in-the-rangea-b-using-one-comparison/)

这是一个简单但有趣的编程难题。给定三个整数，低、高和 x，使得高> =低。如何使用单一比较检查 x 是否在范围[低，高]内。例如，如果范围是[10，100]并且数字是 30，则输出为真，如果数字是 5，则相同范围的输出为假。
一个简单解决方案是将 x 与低和高
进行比较

## C++

```cpp
#include <iostream>
using namespace std;    
// Returns true if x is in range [low..high], else false    
bool inRange(unsigned low, unsigned high, unsigned x)        
{        
 return (low <= x && x <= high);         
}        
int main()       
{        
 inRange(10, 100, 30)? cout << "Yes\n": cout <<"No\n";       
 inRange(10, 100, 5)?  cout << "Yes\n": cout <<"No\n";   
}
```

输出:

```cpp
Yes
No
```

```cpp
 The above solution does two comparisons, 
 Can we do the same task using one comparison? 
```

**我们强烈建议你尽量减少浏览器，先自己试试这个。**
想法是比较“x 低”和“高 x”。当且仅当 x 大于或等于低且小于或等于高时，x 在范围[低，高]内。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
using namespace std;

// Returns true if x is in range [low..high], else false
bool inRange(unsigned low, unsigned high, unsigned x)
{
    return  ((x-low) <= (high-low));
}

int main()
{
    inRange(10, 100, 30)? cout << "Yes\n":  cout  <<"No\n";
    inRange(10, 100, 5)?  cout << "Yes\n":  cout  <<"No\n";
}
```

输出:

```cpp
Yes
No
```

对于[10，100]和 x = 5，这是如何工作的？
当我们从 5 中减去 10，我们得到-5，它被认为是无符号整数形式的 UNIT_MAX-4。UNIT_MAX 是可能的最大无符号整数值。这里的假设是，数字以 2 的补码形式存储。在 2 的补码形式中，-1 代表 UINT_MAX，-2 代表 UINT_MAX-1，..等等。
感谢乌特卡尔斯提出这个解决方案。
**一个适用于负数的解决方案也**
这个想法是将(x 低)和(x 高)相乘。如果 x 在范围内，则必须大于等于低，即(x-低)> = 0。并且必须小于或等于高，即(高–x)<= 0。所以如果乘法的结果小于或等于 0，那么 x 在范围内。否则不行。感谢伊娃提出这个方法。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
using namespace std;

// Returns true if x is in range [low..high], else false
bool inRange(int low, int high, int x)
{
    return ((x-high)*(x-low) <= 0);
}

int main()
{
    inRange(10, 100, 30)? cout << "Yes\n":  cout  <<"No\n";
    inRange(10, 100, 5)?  cout << "Yes\n":  cout  <<"No\n";
}
```

输出:

```cpp
Yes
No
```

如果发现有不正确的地方，请写评论，或者想分享更多关于以上讨论话题的信息