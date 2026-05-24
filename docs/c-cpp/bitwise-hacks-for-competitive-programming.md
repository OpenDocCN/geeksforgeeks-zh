# 竞争编程的逐位黑客攻击

> 原文:[https://www . geesforgeks . org/bitwise-hacks-for-competitive-programming/](https://www.geeksforgeeks.org/bitwise-hacks-for-competitive-programming/)

建议先参考[关于按位运算符](https://www.geeksforgeeks.org/interesting-facts-bitwise-operators-c/)的有趣事实。
T3】1。如何在数字“num”中设置一位:
如果我们想在数字“num”的第 n 个位置设置一位，可以使用“OR”运算符(|)来完成。

*   首先，我们通过(1<
*   然后，使用“或”运算符在该位置设置位。使用“或”运算符是因为它将设置该位，即使该位以前在数字“num”的二进制表示中未设置。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include<iostream>
using namespace std;
// num is the number and pos is the position
// at which we want to set the bit.
void set(int & num,int pos)
{
     // First step is shift '1', second
     // step is bitwise OR
     num |= (1 << pos);
}
int main()
{
     int num = 4, pos = 1;
     set(num, pos);
     cout << (int)(num) << endl;
     return 0;
}
```

输出:

```cpp
6
```

我们已经通过“通过引用调用”传递了参数，以对数字进行永久更改。
**2。如何在数字“num”的第 n 个位置取消设置/清除位:**T3

假设我们想在数字“num”的第 n 个位置取消设置一个位，那么我们必须在“AND”(&)运算符的帮助下这样做。

*   首先，我们通过(1<
*   现在，在清除这个左移的“1”后，即变成“0”，我们将使用数字“num”来“AND”(&)在第 n 个位置取消设置位。

## C

```cpp
#include <iostream>
using namespace std;
// First step is to get a number that  has all 1's except the given position.
void unset(int &num,int pos)
{
    //Second step is to bitwise and this  number with given number
    num &= (~(1 << pos));
}
int main()
{
    int num = 7;
    int  pos = 1;
    unset(num, pos);
    cout << num << endl;
    return 0;
}
```

输出:

```cpp
5
```

**3。在第 n 个位置切换一个位:**
切换是指如果位“关”(0)则打开位“开”(1)，如果位“开”(1)则关闭位“关”(0)。我们将在这里使用“异或”运算符，这是'^'.“异或”运算符背后的原因是因为它的属性。

*   “异或”运算符的属性。
    *   1^1 = 0
    *   0^0 = 0
    *   1^0 = 1
    *   0^1 = 1
*   如果两位不同，则“异或”运算符返回一个设置位(1)，否则返回一个未设置位(0)。

## C

```cpp
#include <iostream>
using namespace std;
// First step is to shift 1,Second step is to XOR with given number
void toggle(int &num,int pos)
{
    num ^= (1 << pos);
}
int main()
{
    int num = 4;
    int pos = 1;
    toggle(num, pos);
    cout << num << endl;
    return 0;
}
```

输出:

```cpp
6
```

**4。检查第 n 个位置的位是否置位或未置位:**

使用“与”运算符很容易做到。

*   向左移动“1”到给定位置，然后“与”(“&”)。

## C

```cpp
#include <iostream>
using namespace std;

bool at_position(int num,int pos)
{
    bool bit = num & (1<<pos);
    return bit;
}

int main()
{
    int num = 5;
    int pos = 0;
    bool bit = at_position(num, pos);
    cout << bit << endl;
    return 0;
}
```

输出:

```cpp
1
```

请注意，我们首先左移了“1”，然后使用“与”运算符在该位置获取位。因此，如果“num”中的“pos”位置有“1”，则“AND”之后的“我们的变量”位将存储“1”，否则，如果数字“num”中的“pos”位置有“0”，则“AND”之后的“我们的变量”位将存储“0”。

**一些更快速的黑客攻击:**

*   **反转数字/1 补码的每一位:**

如果我们想反转一个数字的每一位，即把位“0”改为“1”，把位“1”改为“0”。我们可以在“~”运算符的帮助下做到这一点。例如:如果数字是 num=00101100(二进制表示)，那么“~num”将是“11010011”。

*这也是‘数的 1 补码’。*

## C

```cpp
#include <iostream>
using namespace std;
int main()
{
    int num = 4;

    // Inverting every bit of number num
    cout << (~num);
    return 0;
}
```

```cpp
Output:
 -5
```

*   **数的二进制补码:**数的二进制补码是 1 的补码+ 1。

所以从形式上来说，我们可以通过寻找 1 的补码并在结果上加 1(即~num+1)得到 2 的补码，或者我们还可以使用“-”运算符。

## C

```cpp
#include <iostream>
using namespace std;
int main()
{
    int num = 4;
    int twos_complement = -num;
    cout << "This is two's complement " << twos_complement << endl;
    cout << "This is also two's complement " << (~num+1) << endl;
    return 0;
}
```

输出:

```cpp
This is two's complement -4
This is also two's complement -4
```

*   **剥离最低设置位:**

在许多情况下，我们希望剥离最低设置位，例如在二进制索引树数据结构中，计算一个数字中设置位的数量。

我们这样做:

```cpp
X = X & (X-1)
```

但是它是如何工作的呢？
我们举个例子看看这个，让 X = 1100。
(X-1)反转所有位，直到它遇到最低集“1”，并且它还反转该最低集“1”。
X-1 变成 1011。在用 X-1“与”X 之后，我们得到最低设置位剥离。

## C

```cpp
#include <iostream>
using namespace std;
void strip_last_set_bit(int &num)
{
    num = num & (num-1);
}
int main()
{
    int num = 7;
    strip_last_set_bit(num);
    cout << num << endl;
    return 0;
}
```

输出:

```cpp
6
```

*   **获取数字的最低设置位:**

这是通过使用表达式“X &(-X)”来完成的。让我们通过一个例子来看看这个:让 X = 00101100。所以~X(1 的补码)将是‘11010011’，2 的补码将是(~X+1 或-X)，即‘11010100’。因此，如果我们将原始数“X”与它的二进制补码“-X”进行“与”，我们将得到最低的集位。

```cpp
00101100
& 11010100
-----------
00000100
```

## C

```cpp
#include <iostream>
using namespace std;
int lowest_set_bit(int num)
{
    int ret = num & (-num);
    return ret;
}
int main()
{
    int num = 10;
    int ans = lowest_set_bit(num);
    cout << ans << endl;
    return 0;
}
```

输出:

```cpp
2
```

**在竞争编程的循环中，2 除和 2 乘也很常见，因此使用按位运算符有助于加快代码速度。**

**用右移位运算符除以 2:**

```cpp
00001100 >> 1 (00001100 is 12)
------------
00000110 (00000110 is 6)
```

## C++

```cpp
#include <iostream>
using namespace std;
int main()
{
    int num = 12;
    int ans = num>>1;
    cout << ans << endl;
    return 0;
}
```

**Output**

```cpp
6
```

**用左移位运算符乘以 2:**

```cpp
00001100 << 1 (00001100 is 12)
------------
00011000 (00000110 is 24)
```

## C++

```cpp
#include <iostream>
using namespace std;
int main()
{
    int num = 12;
    int ans = num<<1;
    cout << ans << endl;
    return 0;
}
```

**Output**

```cpp
24
```

[竞争编程的位技巧](https://www.geeksforgeeks.org/bit-tricks-competitive-programming/)
更多关于位黑客的文章，请参考[位运算符文章](https://www.geeksforgeeks.org/category/bit-magic/)。
本文由 **Pankaj Mishra** 供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
发现有不正确的地方请写评论，或者想分享更多以上讨论话题的信息