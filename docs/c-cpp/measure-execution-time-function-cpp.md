# 测量 C++ 中函数的执行时间

> 原文:[https://www . geesforgeks . org/measure-execution-time-function-CPP/](https://www.geeksforgeeks.org/measure-execution-time-function-cpp/)

我们可以使用 C++ 11 中引入的[**【STD::chrono】**](https://www.geeksforgeeks.org/chrono-in-c/)库，找出程序不同部分所花费的时间。我们已经在[讨论了如何在 C](https://www.geeksforgeeks.org/how-to-measure-time-taken-by-a-program-in-c/) 中测量程序花费的时间。那里描述的函数在 C++ 中也受支持，但是它们是特定于 C 的。对于干净健壮的 C++ 程序，我们应该努力只使用 C++ 特定的语言结构。

**std::chrono** 有两个不同的对象——时间点和持续时间。顾名思义，时间点代表时间点，而持续时间代表时间间隔或时间跨度。C++ 库允许我们减去两个时间点，得到其间经过的时间间隔。使用提供的方法，我们还可以将这个持续时间转换为适当的单位。

**std::chrono** 为我们提供了三个不同精度的时钟。**高分辨率时钟**最精确，因此用于测量执行时间。

**第一步:获取函数调用前的时间点**

```cpp
#include <chrono>
using namespace std::chrono;

// Use auto keyword to avoid typing long
// type definitions to get the timepoint
// at this instant use function now()
auto start = high_resolution_clock::now();
```

**第二步:获取函数调用后的时间点**

```cpp
#include <chrono>
using namespace std::chrono;

// After function call
auto stop = high_resolution_clock::now();
```

**第三步:获取时间点的差异，并将其转换为所需的单位**

```cpp
// Subtract stop and start timepoints and
// cast it to required unit. Predefined units
// are nanoseconds, microseconds, milliseconds,
// seconds, minutes, hours. Use duration_cast()
// function.
auto duration = duration_cast<microseconds>(stop - start);

// To get the value of duration use the count()
// member function on the duration object
cout << duration.count() << endl;
```

下面给出了一个完整的 C++ 程序来演示这个过程。我们用一些随机数填充一个向量，并测量 sort()函数对这个向量进行排序所花费的时间。

```cpp
// C++ program to find out execution time of
// of functions
#include <algorithm>
#include <chrono>
#include <iostream>
#include<vector>
using namespace std;
using namespace std::chrono;

// For demonstration purpose, we will fill up
// a vector with random integers and then sort
// them using sort function. We fill record
// and print the time required by sort function
int main()
{

    vector<int> values(10000);

    // Generate Random values
    auto f = []() -> int { return rand() % 10000; };

    // Fill up the vector
    generate(values.begin(), values.end(), f);

    // Get starting timepoint
    auto start = high_resolution_clock::now();

    // Call the function, here sort()
    sort(values.begin(), values.end());

    // Get ending timepoint
    auto stop = high_resolution_clock::now();

    // Get duration. Substart timepoints to 
    // get durarion. To cast it to proper unit
    // use duration cast method
    auto duration = duration_cast<microseconds>(stop - start);

    cout << "Time taken by function: "
         << duration.count() << " microseconds" << endl;

    return 0;
}
```

输出:(取决于机器)

```cpp
Time taken by function: 3062 microseconds

```

**参考文献**
[https://www.geeksforgeeks.org/chrono-in-c/](https://www.geeksforgeeks.org/chrono-in-c/)