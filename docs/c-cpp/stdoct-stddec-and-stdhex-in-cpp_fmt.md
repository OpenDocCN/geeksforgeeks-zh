# C++ 中的 std::oct、std::dec 和 std::hex

> 原文：[https://www.geeksforgeeks.org/stdoct-stddec-and-stdhex-in-cpp/](https://www.geeksforgeeks.org/stdoct-stddec-and-stdhex-in-cpp/)

该函数用于将基数设置为八进制、十进制或十六进制。它将字符串流的 `basefield` 格式标志设置为指定的基数。

## std::oct

当 `basefield` 设置为八进制时，插入流中的整数值以八进制为基数（即基数 8）表示。对于输入流，当设置此标志时，提取的值也应该用八进制表示。

## std::hex

当 `basefield` 设置为十六进制时，插入流中的整数值以十六进制基数（即基数 16）表示。对于输入流，当设置此标志时，提取的值也应该以十六进制基数表示。

## std::dec

`basefield` 格式标志可以采用十进制值（每个值都有自己的操纵器）。这是一个输入输出操纵器。可以用 `out << std::oct`、`std::hex` 或 `std::dec`（对于任何 `std::basic_ostream` 类型的 `out`）或者通过这样的表达式来调用，语法：

```
ios_base& hex (ios_base& str);
```

`str`：其 `basefield` 格式标志受影响的流对象。
返回值：返回按十进制基数解析为八进制基数的增强字符串。

## 示例

输入：

输出：
```
oct - 66
dec - 54
hex - 36
```

```cpp
// CPP program to illustrate
// std::oct, std::hex, std::dec
#include <iostream> // std::cout, std::dec, std::hex, std::oct

int main()
{
    int n = 54;
    std::cout << std::oct << "oct - " << n << '\n';
    std::cout << std::dec << "dec - " << n << '\n';
    std::cout << std::hex << "hex - " << n << '\n';
    return 0;
}
```

输出：

```
oct - 66
dec - 54
hex - 36
```