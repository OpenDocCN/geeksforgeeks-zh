# C++中带有std::bitset的算术运算

> 原文：[https://www.geeksforgeeks.org/arithmetic-operations-with-stdbitset-in-c/](https://www.geeksforgeeks.org/arithmetic-operations-with-stdbitset-in-c/)

一个[位集](https://www.geeksforgeeks.org/c-bitset-and-its-application/)是一个由布尔值组成的[数组](https://www.geeksforgeeks.org/array-data-structure/)，但是每个布尔值并不是单独存储的。相反，位集优化了空间，使得每个 `bool` 只占用 1 位空间，因此位集占用的空间，比如说，`bs` 小于 `bool bs[N]` 和 [`vector<bool>bs(N)`](https://www.geeksforgeeks.org/vector-in-cpp-stl/)。然而，位集的一个限制是，`N` 在编译时必须是已知的，即常数（向量和动态数组没有这个限制）。

**重要提示：**

*   注意整数溢出。例如，如果位集声明为大小 3，而加法结果是 9，这就是整数溢出的情况，因为 9 无法存储在 3 位中。
*   注意负结果，因为位集被转换为无符号长整型，所以无法存储负数。

**增加 2 个位集：** 按照以下步骤解决问题：

*   初始化一个 `bool` `carry` 为 `false`。
*   创建一个位集 `sum` 来存储两个位集 `x` 和 `y` 的总和。
*   遍历位集 `x` 和 `y` 的长度，使用[全加器](https://www.geeksforgeeks.org/full-adder-in-digital-logic/)功能确定 `sum` 中当前位的值。
*   返回 `sum`。

下面是上述方法的实现：

### 加法实现

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;
// Utility function to add two bool values and calculate
// carry and sum
bool fullAdder(bool b1, bool b2, bool& carry)
{
    bool sum = (b1 ^ b2) ^ carry;
    carry = (b1 && b2) || (b1 && carry) || (b2 && carry);
    return sum;
}
// Function to add two bitsets
bitset<33> bitsetAdd(bitset<32>& x, bitset<32>& y)
{
    bool carry = false;
    // bitset to store the sum of the two bitsets
    bitset<33> ans;
    for (int i = 0; i < 33; i++) {
        ans[i] = fullAdder(x[i], y[i], carry);
    }
    return ans;
}
// Driver Code
int main()
{
    // Given Input
    bitset<32> a(25);
    bitset<32> b(15);

    // Store the result of addition
    bitset<33> result = bitsetAdd(a, b);

    cout << result;
    return 0;
}
```

**Output**

```
000000000000000000000000001000000
```

`时间复杂度：`O(N)，N 为位集长度
`辅助空间：`O(N)

**2 位集的减法：** 按照以下步骤解决问题：

*   初始化一个 `bool` `borrow` 为 `false`。
*   创建一个位集 `diff` 来存储两个位集 `x` 和 `y` 之间的差异。
*   遍历位集 `x` 和 `y` 的长度，使用[全减法器](https://www.geeksforgeeks.org/full-subtractor-in-digital-logic/)功能确定 `diff` 中当前位的值。
*   返回 `diff`。

下面是上述方法的实现：

### 减法实现

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;
// Utility function to subtract two bools and calculate diff
// and borrow
bool fullSubtractor(bool b1, bool b2, bool& borrow)
{
    bool diff;
    if (borrow) {
        diff = !(b1 ^ b2);
        borrow = !b1 || (b1 && b2);
    }
    else {
        diff = b1 ^ b2;
        borrow = !b1 && b2;
    }
    return diff;
}
// Function to calculate difference between two bitsets
bitset<33> bitsetSubtract(bitset<32> x, bitset<32> y)
{
    bool borrow = false;
    // bitset to store the sum of the two bitsets
    bitset<33> ans;
    for (int i = 0; i < 32; i++) {
        ans[i] = fullSubtractor(x[i], y[i], borrow);
    }
    return ans;
}
// Driver Code
int main()
{
    // Given Input
    bitset<32> a(25);
    bitset<32> b(15);

    // Store the result of addition
    bitset<33> result = bitsetSubtract(a, b);

    cout << result;
    return 0;
}
```

**Output**

```
00000000000000000000000000001010
```

`时间复杂度：`O(N)，N 为位集长度
`辅助空间：`O(N)