# std::string::data()在 C++ 中

> 原文:[https://www.geeksforgeeks.org/stdstringdata-in-c/](https://www.geeksforgeeks.org/stdstringdata-in-c/)

data()函数将字符串的字符写入数组。它返回一个指向数组的指针，该指针是从字符串到数组的转换中获得的。它的返回类型不是有效的 C 字符串，因为**没有“\ 0”**字符被追加到数组的末尾。
**语法:**

```cpp
const char* data() const;
char* is the pointer to the obtained array.
Parameters : None

```

*   **std::string::data()** 返回字符串所属的数组。因此，调用者不能修改或释放内存。
    我们举一个同样的例子，ptr 指向最终数组。

    ```cpp
    ptr[2] = 'a';
    this will raise an error as ptr points to an array that
    is owned by the string, in other words ptr is now pointing
    to constant array and assigning it a new value is now not allowed.

    ```

*   data()的返回值仅在下一次调用同一字符串的非常数成员函数之前有效。
    **解释:**
    假设 str 是需要在数组中转换的原始字符串

    ```cpp
    // converts str in an array pointed by pointer ptr.
    const char* ptr = str.data(); 

    // Bad access of str after modification
    // of original string to an array
    str += "hello"; // invalidates ptr

    // Now displaying str with reference of ptr
    // will give garbage value
    cout << ptr; // Will give garbage value

    ```

```cpp
// CPP code to illustrate
// std::string::data()

#include <iostream>
#include <string>
#include <cstring>
using namespace std;

// Function to demonstrate data() 
void dataDemo(string str1)
{
    // Converts str1 to str2 without appending
    // '/0' at the end
    const char* str2;
    str2 = str1.data();

    cout << "Content of transformed string : ";
    cout << str2 << endl;

    cout << "After data(), length: ";
    cout << strlen(str2);

}

// Driver code
int main()
{
    string str("GeeksforGeeks");

    cout << "Content of Original String : ";
    cout << str << endl;
    cout << "Length of original String : ";
    cout << str.size() << endl;

    dataDemo(str);

    return 0;
}
```

输出:

```cpp
Content of Original String : GeeksforGeeks
Length of original String : 13
Content of transformed string : GeeksforGeeks
After data(), length: 13

```

在这里，我们可以很容易地注意到，原始字符串和转换数组的内容和长度都是相同的。
本文由**萨基提瓦里**供稿。如果你喜欢极客(我们知道你喜欢！)并愿意投稿，也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者将文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。