# 竞争编程中最关键的错误&技巧

> 原文:[https://www . geesforgeks . org/最关键的错误-竞争编程技巧/](https://www.geeksforgeeks.org/most-critical-mistakes-tips-in-competitive-programming/)

初学者一听到这个词，脑海中就会弹出一个画面，学生们坐在一个装满电脑的房间里，对一些不寻常的东西进行编码。老实说，这并不难理解，所以我们将提出一些帮助程序员更快升级的技巧。因此，让我们从每个主题中最被低估的点开始，即使是高级的有竞争力的程序员也会忽略这些点。

![Most-Critical-Mistakes-Tips-in-Competitive-Programming](img/e474ee910a9e246dd48115d5a11dd721.png)

所以溢出的概念在竞争性编码中随处可见，最糟糕的问题是不理解它，写了一个完全完美的代码，但仍然得到错误的答案，这是因为，在更高的输入范围，编译器根据数据大小剥离结果，因此记住数据类型的基本范围是很重要的。

```cpp
Int => [-109 To 109]
Long Int / long => [-1012,1012]
Long Long Int / long long => [-1018,10^18]
```

**示例:**

## C++

```cpp
// C++ Program, to Illustrate General Tips In Competitive
// Programming

// Importing all C++ libraries
#include <bits/stdc++.h>

using namespace std;

// Main method
int main()
{

    // Case: Stack Overflow
    int a = 100000, b = 100000;
    // Expected answer ? 10^10 but
    // no the answer you get is 1410065408, error in
    // precision.
    int c = a * b;
    long long int d = a * b;

    // Note: Still error will be generated bacause
    // calcultation was done on two ints which were later
    // converted into long long ie they already
    // lost their data before converting

    // Print and display on console
    cout << c << " " << d << endl;

    // Now if we store a value more than its capacity then
    // what happens is the number line of range of value
    // bacomes a number
    // Example: Circle, If min val is 1 and max is 9, so if
    // we add 1 to 9 it will result in 1, it looped back to
    // starting, this is overflow

    int p = INT_MAX;

    // An example of overflow
    cout << "An example of overflow " << p + 1 << endl;

    // Long long is way better than double,
    // double although can store more than long long but
    // in exchange it will cost you your precision.
    // We can simply use the below command as follows:
    // cout<<fixed(no scientific
    // notation)<<setprecision(0){removes decimal}<<variable
    // to give value same form as long long

    // Question where the answer came wrong coz of
    // overflow!!
    int t, n;
    cin >> t;
    while (t--) {
        cin >> n;

        // Here, before i used int and got wrong answer,
        // then made it long long
        long long pdt = 1, temp;

        for (int i = 0; i < n; i++) {
            cin >> temp;
            pdt *= temp;
        }

        if (pdt % 10 == 2 || pdt % 10 == 3 || pdt % 10 == 5)
            cout << "YES" << endl;

        else
            cout << "NO" << endl;
    }
}
```

**Output**

```cpp
1410065408 1410065408
An example of overflow -2147483648
```

## **数据结构提示**

**提示 1:** 在竞争性编程中，当需要一个函数和主函数时，总是全局声明数组，全局声明的数组可以有 10^7 大小，因为它们存储在**数据段**中。

**提示 2:** 每当你声明一个需要返回多个项目的函数，或者一般情况下你的目标是在做一些修改后返回一个数组时，一定要选择 **Pass By Reference (** 如 void swap(int **& a、** int **& b** ) **)** ，它在两个方面帮助你一、 通过减少制作数据副本然后对其进行处理的时间，第二，当您直接处理主数据时，您可以修改任意多的值，而不必担心返回值和处理它们。

*   在 main 方法中声明的数组大小的限制是 10^5，因为它存储在内存限制约为 8MB 的**堆栈内存**中，如果大小超过这个限制，就会导致**堆栈溢出**。
*   当您在 cin 输入之后将多个字符串作为输入时，有时会出现一个非常特殊的错误。它不会接受所需的输入，而是自动接受空格作为输入，然后接受剩余的两个字符串，要解决这个问题，请在使用 **getline()** 将字符串作为输入之前使用 **cin.ignore()** 。
*   当从另一个字符串组成一个新字符串时，不使用像 str = str + str2[I]这样的语法，即添加字符来获得一个字符串，这个方法的时间复杂度是 **O(大小(字符串))**、因此列出了向一个字符串添加字符，我们使用 **push_back(字符)**，其时间复杂度是 **O(n)。**

## 关于 STL 的提示

到目前为止，我们已经知道 STL 代表 C++、中的**标准模板库**，这对有竞争力的程序员来说是一个福音，它包含内置的特殊数据结构和算法，可以像疯狂一样减少和优化您的代码。请记住下面列出的 STL 数据结构提示，如下所示:

**提示 1:** 每当我们需要对问题中的数据进行排序并删除重复项时，最佳做法是将其存储在**集中，**会自动对数据进行排序，并且根据**集**的属性，它只存储唯一值。

**提示 2:** 在我们需要找到所有值的出现频率的问题中，最好的做法是使用一个 **Map，**Map 的属性使其自动按照字典顺序排列数据，只需一个小技巧，你就会有最高效的解决方案。

**例**

## C++

```cpp
// C++ Program to Illustrate STL Algorithms Tips

// Importing all C++ libraries
// Standard command
#include <bits/stdc++.h>

using namespace std;

// Main method
// From here the code starts executing
int main()
{

    // Creating vector and initializing objects
    // by passing custom integer numbers
    vector<int> v
        = { 1, 4, 2, 5, 6, 3, 9, 0, 10, 3, 15, 17, 3 };

    // Operation 1
    // Finding the minimum element in the array,

    // Note: It returns the pointer/iterator
    auto min = min_element(v.begin(), v.end());

    // Print and display elements on console
    cout << "Min element: " << *min << endl;

    // Operation 2
    // // Finding the maximum  element in the array
    auto max = max_element(v.begin(), v.end());
    cout << "Max Element: " << *max << endl;

    // Operation 3
    // Sum of all elements, the third parameter tells us
    // initial sum ki value kya hai.
    auto sum = accumulate(v.begin(), v.end(), 0);
    cout << "The sum of all elements: " << sum << endl;

    // Operation 4
    // Count the frequency of an element in the array/vector
    auto cnt = count(v.begin(), v.end(), 3);
    cout << "Frequency Of 3 is: " << cnt << endl;

    // Operation 5
    // Finds an element and returns its pointer
    auto elem = find(v.begin(), v.end(), 3);

    if (elem != v.end())
        cout << "the element is at posn: " << *elem << endl;
    else
        cout << "Element not found" << endl;

    // Operation 6
    // Reversing a string or array/vector
    // using reverse method
    reverse(v.begin(), v.end());

    cout << "Reversed Vector: ";

    for (auto val : v) {
        cout << val << " ";
    }

    // New line for better readability
    cout << endl;

    // Operation 7
    // Sort array/vector using sort() method
    sort(v.begin(), v.end());
    cout << "Sorted Vector: ";
    for (auto val : v) {
        cout << val << " ";
    }
}
```

**Output**

```cpp
Min element: 0
Max Element: 17
The sum of all elements: 78
Frequency Of 3 is: 3
the element is at posn: 3
Reversed Vector: 3 17 15 3 10 0 9 3 6 5 2 4 1 
Sorted Vector: 0 1 2 3 3 3 4 5 6 9 10 15 17 
```

> **注意:**这些是一些可以让你的生活变得轻松的流行算法，它们都有相同的使用模式，即函数名
> 
> **(下 lim，上 lim+1)**