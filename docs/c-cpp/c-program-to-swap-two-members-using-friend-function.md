# 使用友方函数

交换两个成员的 C++ 程序

> 原文:[https://www . geesforgeks . org/c-程序到交换-两个成员-使用朋友-函数/](https://www.geeksforgeeks.org/c-program-to-swap-two-members-using-friend-function/)

**先决条件:** [朋友函数](https://www.geeksforgeeks.org/friend-class-function-cpp/)
T5【案例 1:
给定两个数字 a & b，使用 C++ 的朋友函数交换这两个数字。

**示例:**

```cpp
Input : a = 5, b = 9
Output : a = 9, b = 5

Input : a = 4, b = 6
Output : a= 6, b = 4
```

**方法:**
创建一个 Swap 类，在其中声明三个变量，即 a、b 和 temp，并为输入创建一个构造函数。在其中声明一个朋友函数。通过引用将参数作为调用来传递交换对象的副本，从而在类范围之外定义友元函数。使用交换变量执行交换操作。

## C++

```cpp
// C++ Program to swap two numbers using friend function
#include <iostream>

using namespace std;

class Swap {

    // Declare the variables of Swap Class
    int temp, a, b;

public:

    // Define the parameterized constructor, for inputs
    Swap(int a, int b)
    {
        this->a = a;
        this->b = b;
    }

    // Declare the friend function to swap, take arguments
    // as call by reference
    friend void swap(Swap&);
};

// Define the swap function outside class scope
void swap(Swap& s1)
{
    // Call by reference is used to passed object copy to
    // the function
    cout << "\nBefore Swapping: " << s1.a << " " << s1.b;

    // Swap operations with Swap Class variables
    s1.temp = s1.a;
    s1.a = s1.b;
    s1.b = s1.temp;
    cout << "\nAfter Swapping: " << s1.a << " " << s1.b;
}

// Driver Code
int main()
{
    // Declare and Initialize the Swap object
    Swap s(4, 6);
    swap(s);
    return 0;
}
```

**Output:** 

```cpp
Before Swapping: 4 6
After Swapping: 6 4
```