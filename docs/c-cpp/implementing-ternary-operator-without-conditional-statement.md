# 实现不带任何条件语句的三元运算符

> 原文:[https://www . geeksforgeeks . org/implementing-三元运算符-不带条件语句/](https://www.geeksforgeeks.org/implementing-ternary-operator-without-conditional-statement/)

不使用条件语句如何在 C++ 中实现[三元运算符](https://www.geeksforgeeks.org/cc-ternary-operator-some-interesting-observations/)。
在以下条件下: **a？b:c**T5【如果 a 为真，b 将被执行。
否则执行 c。
我们可以假设 a、b、c 为数值。

我们可以将方程编码为:
**结果=(！！a)*b +(！a)*c** 在上式中，如果 a 为真，则结果为 b.
否则结果为 c.

## C++

```cpp
// CPP code to implement ternary operator
#include <bits/stdc++.h>

// Function to implement ternary operator without
// conditional statements
int ternaryOperator(int a, int b, int c)
{
    // If a is true, we return (1 * b) + (!1 * c) i.e. b
    // If a is false, we return (!1 * b) + (1 * c) i.e. c
    return ((!!a) * b + (!a) * c);
}

// Driver code
int main()
{
    int a = 1, b = 10, c = 20;

    // Function call to output b or c depending on a
    std::cout << ternaryOperator(a, b, c) << '\n';

    a = 0;

    // Function call to output b or c depending on a
    std::cout << ternaryOperator(a, b, c);

    return 0;
}
```

## 蟒蛇 3

```cpp
# Python 3 code to implement ternary operator

# Function to implement ternary operator
# without conditional statements
def ternaryOperator( a, b, c):

    # If a is true, we return
    # (1 * b) + (!1 * c) i.e. b
    # If a is false, we return
    # (!1 * b) + (1 * c) i.e. c
    return ((not not a) * b + (not a) * c)

# Driver code
if __name__ == "__main__":

    a = 1
    b = 10
    c = 20

    # Function call to output b or c
    # depending on a
    print(ternaryOperator(a, b, c))

    a = 0

    # Function call to output b or c
    # depending on a
    print(ternaryOperator(a, b, c))

# This code is contributed by ita_c
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```cpp
<?php
// PHP code to implement
// ternary operator

// Function to implement
// ternary operator without
// conditional statements
function ternaryOperator($a, $b, $c)
{

    // If a is true, we return
    // (1 * b) + (!1 * c) i.e. b
    // If a is false, we return
    // (!1 * b) + (1 * c) i.e. c
    return ((!!$a) * $b + (!$a) * $c);
}

    // Driver code
    $a = 1;
    $b = 10;
    $c = 20;

    // Function call to output
    // b or c depending on a
    echo ternaryOperator($a, $b, $c) ,"\n";

    $a = 0;

    // Function call to output b
    // or c depending on a
    echo ternaryOperator($a, $b, $c);

// This code is contributed by jit_t.
?>
```

## java 描述语言

```cpp
<script>

// Javascript code to implement
// ternary operator

    // Function to implement
    // ternary operator without
    // conditional statements
    function ternaryOperator(a,b,c)
    {
        // If a is true,
        // we return (1 * b) + (!1 * c) i.e. b
        // If a is false,
        // we return (!1 * b) + (1 * c) i.e. c

        return ((!!a) * b + (!a) * c);
    }

    // Driver code
    let a = 1, b = 10, c = 20;
    // Function call to output b or c depending on a
    document.write( ternaryOperator(a, b, c)+"<br>");

    a = 0;
    // Function call to output b or c depending on a
    document.write( ternaryOperator(a, b, c)+"<br>");

    // This code is contributed by avanitrachhadiya2155

</script>
```

**输出:**

```cpp
10
20
```

问于:[英伟达](https://www.geeksforgeeks.org/tag/nvidia/)
本文由**罗希特·塔普利亚尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。