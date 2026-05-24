# C++位集有趣的事实

> 原文:[https://www.geeksforgeeks.org/c-bitset-interesting-facts/](https://www.geeksforgeeks.org/c-bitset-interesting-facts/)

[位集](https://www.geeksforgeeks.org/c-bitset-and-its-application/)是C++标准模板库中的一个容器，用于处理位级的数据。

## 1. 从字符串构造位集

位集存储位(只有两个可能值的元素:0或1)。然而，我们可以通过向位集构造函数提供位置来获得字符串的一部分(位置是相对于从左到右的字符串位置)。

示例:

```cpp
// C++ program to demonstrate that we can get part of a
// bit string in bitset.
#include <bitset>
#include <string>
#include <iostream>

int main()
{
  std::string bit_string = "110010";
  std::bitset<8> b1(bit_string);             // [0, 0, 1, 1, 0, 0, 1, 0]

  // string from position 2 till end
  std::bitset<8> b2(bit_string, 2);      // [0, 0, 0, 0, 0, 0, 1, 0]

  // string from position 2 till next 3 positions
  std::bitset<8> b3(bit_string, 2, 3);   // [0, 0, 0, 0, 0, 0, 0, 1]

  std::cout << b1 << '\n' << b2 << '\n' << b3 << '\n';

  return 0;
}
```

输出:

```

```

## 2. 使用自定义字符从字符串构造

我们可以使用`std::basic_string`中的字符构造一个位集。可以提供可选的起始位置和长度，以及表示set(`_1`)和unset(`_0`)位的替代值的字符。

**语法:**

```cpp
std::bitset b1(str, pos, n, zero, one);
str    : string used to initialize the bitset
pos    : a starting offset into str
n    : number of characters to use from str
zero    : alternate character for unset bits in str
one    : alternate characters for set bits in str 
```

*   如果`pos > str.size()`，此构造函数将引发`std::out_of_range`。
*   如果在`str`中检查的任何字符不是零或一，它将抛出`std::invalid_argument`。

```cpp
// C++ program to demonstrate that we can construct bitset using
// alternate characters for set and unset bits.
#include <bitset>
#include <string>
#include <iostream>

int main()
{
    // string constructor using custom zero/one digits
    std::string alpha_bit_string = "aBaaBBaB";
    std::bitset<8> b1(alpha_bit_string, 0, alpha_bit_string.size(),
                    'a', 'B');         // [0,1,0,0,1,1,0,1]

    std::cout << b1 << '\n';
}
```

输出:

```

```

## 3. 从C风格字符串构造

构造一个类位集的对象，将N个位初始化为与C风格的0和1字符串中提供的字符相对应的值。您可以在不将字符串转换为`std::string`类型的情况下调用构造函数。它还有两个可选参数，`zero`和`one`，分别指示`str`中的哪个字符将被解释为0位和1位。

```cpp
#include <bitset>
#include <iostream>

int main()
{
    // char* constructor using custom digits
    std::bitset<8> b1("XXXXYYYY", 8, 'X', 'Y'); // [0, 0, 0, 0, 1, 1, 1, 1]
    std::cout << b1 << '\n';
}
```

输出:

```

```

## 位组操作

### 1. `std::bitset::to_string()`

将位集的内容转换为字符串。使用`0`表示值为假的位，使用`1`表示值为真的位。结果字符串包含N个字符，第一个字符对应于最后(第N-1)位，最后一个字符对应于第一位。此外，我们可以通过参数传递用于打印真值和假值的字符。

示例:

```cpp
// C++ program to demonstrate that we can convert contents
// of bitset to a string.
#include <iostream>
#include <bitset>

int main()
{
    std::bitset<8> b(42);
    std::cout << b.to_string() << '\n'
              << b.to_string('*') << '\n'
              << b.to_string('O', 'X') << '\n';
}
```

输出:

```
00101010
**1*1*1*
OOXOXOXO
```

### 2. `std::bitset::to_ulong()`

将位集的内容转换为无符号长整数。位组的第一位对应于数字的最低有效位，最后一位对应于最高有效位。如果值不能用无符号长整型表示，函数将引发`std::overflow_error`。

示例:

```cpp
// C++ program to demonstrate that we can get value of bitset
// as  unsigned long integer.
#include <iostream>
#include <bitset>

int main()
{
    std::bitset<5> b(5);
    std::cout << b.to_ulong() << '\n';
}
```

输出:

```

```