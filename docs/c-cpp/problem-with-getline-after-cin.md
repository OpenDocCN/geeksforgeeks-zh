# CIN>之后的 getline()问题>T1】

> 原文:[https://www . geeksforgeeks . org/CIN 之后的 getline 问题/](https://www.geeksforgeeks.org/problem-with-getline-after-cin/)

[C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中的 [**getline()**](https://www.geeksforgeeks.org/getline-string-c/) 函数用于[从输入流中读取一个字符串或一行](https://www.geeksforgeeks.org/getline-string-c/)。 **getline()** 函数不忽略前导空格字符。所以在使用 **getline()** 的时候要特别小心，在 [**cin**](https://www.geeksforgeeks.org/basic-input-output-c/) 之后，因为 **cin** 忽略了空格字符，把它作为垃圾留在了流中。

**程序 1:**

下面是 C++ 程序来说明相同:

## C++

```cpp
// C++ program for the above problem
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    int fav_no;
    string name;

    cout << "Type your favorite number: ";

    // The cin statement uses the
    // fav_no and leaves the \n
    // in the stream as garbage
    cin >> fav_no;

    cout << "Type your name : ";

    // getline() reads \n
    // and finish reading
    getline(cin, name);

    // In output only fav_no
    // will be displayed not
    // name
    cout << name
         << ", your favourite number is : "
         << fav_no;

    return 0;
}
```