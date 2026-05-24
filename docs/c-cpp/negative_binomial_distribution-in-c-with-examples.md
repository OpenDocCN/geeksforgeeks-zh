# c++ 中的负二项分布，示例

> 原文:[https://www . geesforgeks . org/negative _ binomial _ distribution-in-c-with-examples/](https://www.geeksforgeeks.org/negative_binomial_distribution-in-c-with-examples/)

该功能在表头**随机**随机中定义。**负二项分布**是根据负二项离散分布(也称为帕斯卡分布)产生整数的随机数分布，由以下概率质量函数描述。
![P(i|k, p) = \binom{k + i - 1}{i} \cdot p^k \cdot (1 - p)^i  ](img/83490ad6944b7ffbb58c9026eb86163e.png "Rendered by QuickLaTeX.com")
该值代表在一系列独立的是/否试验中失败的次数(每个试验都以概率 p 成功)，正好在 k 次成功之前。
**语法:**

```cpp
template( class IntType = int )
class negative_binomial_distribution
```

**模板参数:**
**IntType :** 生成器生成的结果类型。
**成员类型**
**成员类型&定义**

<figure class="table">

| Result _ type | **int 类型** |
| param _ type 参数类型 | Type returned by member [T0】 param 【T1] |

</figure>

**成员功能:**公共成员功能

*   **构造函数():**构造负二项分布
*   **运算符():**生成随机数
*   **复位:**复位分配
*   **参数:**分布参数
*   **分钟:**最小值
*   **最大值:**最大值

**分布参数:**公共成员函数

*   **k :** 分布参数 k
*   **p :** 分布参数 p

**非成员函数:**函数模板

*   **运算符< < :** 插入输出流
*   **运算符> > :** 从输入流中提取
*   **关系运算符:**关系运算符

下面的程序来说明上面的模板

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate
// negative_binomial_distribution
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // number of experiments
    const int exps = 10000;

    // maximum number of stars to distribute
    const int numberstars = 100;

    // Generator generate numbers based
    // upon a generator function
    default_random_engine generator;

    // Aman watches GOT
    // At each episode, there's a 50%
    // chance that john snow will die
    // after how many time he'll be turned
    // away before watching 4 episodes?
    negative_binomial_distribution<int> distribution(4, 0.5);

    // initializing an array with size 10
    int p[10] = {};

    for (int i = 0; i < exps; ++ i) {
        int counting = distribution(generator);
        if (counting < 10)
            ++ p[counting];
    }

    cout << "Negative binomial distribution with "
         << "( k = 4, p = 0.5 ) :" << endl;

    // Printing the sequence stored in an array p
    for (int i = 0; i < 10; ++ i)
        cout << i << ": " << string(p[i] * numberstars / exps, '*') << endl;

    return 0;
}
```

**输出:**

```cpp
Negative binomial distribution with ( k = 4, p = 0.5 ) :
0: *****
1: ************
2: ****************
3: ***************
4: *************
5: **********
6: ********
7: *****
8: ***
9: **
```

分布参数为 1 和 20%
**的程序下面:程序 2:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate
// negative_binomial_distribution
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // number of experiments
    const int exps = 10000;

    // maximum number of stars to distribute
    const int numberstars = 100;

    // Generator generate numbers based
    // upon a generator function
    default_random_engine generator;

    // Aman watches GOT
    // At each episode, there's a
    // 20% chance that john snow will die
    // after how many time he'll be
    // turned away before watching 1 episodes?
    negative_binomial_distribution<int> distribution(1, 0.2);

    // initializing an array with size 10
    int p[10] = {};

    for (int i = 0; i < exps; ++ i) {
        int counting = distribution(generator);
        if (counting < 10)
            ++ p[counting];
    }

    cout << "Negative binomial distribution with "
         << "( k = 1, p = 0.2 ) :" << endl;

    // Printing the sequence stored in an array p
    for (int i = 0; i < 10; ++ i)
        cout << i << ": " << string(p[i] * numberstars / exps, '*') << endl;

    return 0;
}
```

**输出:**

```cpp
Negative binomial distribution with ( k = 1, p = 0.2 ) :
0: *******************
1: ***************
2: ************
3: **********
4: ********
5: ******
6: *****
7: ****
8: ***
9: **
```