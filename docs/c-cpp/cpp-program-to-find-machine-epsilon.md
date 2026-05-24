# C++ 程序查找机器ε

> 原文:[https://www . geesforgeks . org/CPP-程序到查找-机器-epsilon/](https://www.geeksforgeeks.org/cpp-program-to-find-machine-epsilon/)

机器ε是最小数量的 EPS(ε)，使得 1 + EPS 不等于 1。机器ε是一个机器相关的浮点值，它提供了由于浮点运算中的舍入而导致的相对误差的上限。数学上，对于每种浮点类型，它相当于 1.0 和大于 1.0 的最小可表示值之间的差值。

在 C 语言中，机器ε在标准标题中指定，名称为 FLT _ε、DBL _ε和 LDBL _ε。这三个宏分别为 float、double 和 long double 类型提供了机器ε。

在 C++ 中，标准标题中也有类似的宏。C++ 中首选的方法是使用标准标题中指定的 STD::numeric _ limits::epsilon()–值。

在 Java 中，它被称为 ULP(最后一位的单位)。您可以使用 java.lang.Math 包和 Math.ulp()方法找到它。

在 Python3 中，该信息在 sys.float_info 中可用，它对应于 C99 中的 float.h。
这是 c++ 等价的 std::numeric_limits::epsilon()。
> > >导入 sys
>>>sys . float _ info . epsilon

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to find machine epsilon
#include<iostream>
#include <cfloat>
using namespace std;

// Function for Machine Epsilon with an
// initial value provided as EPS.
void machineEpsilon(float EPS)
{
    // taking a floating type variable
    float prev_epsilon;

    // run until condition satisfy
    while ((1+EPS) != 1)
    {
        // copying value of epsilon into previous epsilon
        prev_epsilon = EPS;

        // dividing epsilon by 2
        EPS /=2;
    }

    // print output of the program
    cout << "Machine Epsilon is : " << prev_epsilon << endl;
}

// Driver Code
int main()
{
    // calling function which calculate machine epsilon
    // with initial value provided as 0.5
    machineEpsilon(0.5);

    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to find machine epsilon

import java.util.*;

class Count{

    // Function for Machine Epsilon with an
    // initial value provided as EPS.

    public static void machineEpsilon(double EPS)
    {
        // taking a floating type variable
        double prev_epsilon = 0.0;

        // run until condition satisfy
        while ((1+EPS) != 1)
        {
            // copying value of epsilon
            // into previous epsilon
            prev_epsilon = EPS;

            // dividing epsilon by 2
            EPS /=2;
        }

        // print output of the program
        System.out.print( "Machine Epsilon is : "
                         + prev_epsilon);
    }   

    public static void main(String[] args)
    {
        // calling function which
        // calculate machine epsilon
        // with initial value provided as 0.5
        machineEpsilon(0.5);

    }
}

// This code is contributed by rishabh_jain
```

## 蟒蛇 3

```cpp
# Python program to find machine epsilon

# Function for Machine Epsilon with an
# initial value provided as EPS.
def machineEpsilon(EPS):

    # taking a floating type variable
    # run until condition satisfy
    while ((1+EPS) != 1):

        # copying value of epsilon
        # into previous epsilon
        prev_epsilon = EPS

        # dividing epsilon by 2
        EPS = EPS / 2

    # print output of the program
    print( "Machine Epsilon is : " ,
            prev_epsilon )

# Driven code
# calling function which
# calculate machine epsilon
# with initial value provided as 0.5
machineEpsilon(0.5);

# This code is contributed by
# "rishabh_jain".
```

Output:

```cpp

Machine Epsilon is : 1.19209e-07

```

请注意，上述结果因机器而异。

本文由**萨赫勒拉杰普特**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。