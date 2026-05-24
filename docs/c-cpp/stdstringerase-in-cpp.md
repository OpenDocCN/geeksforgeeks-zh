# std::string::在 C++ 中擦除

> 原文:[https://www.geeksforgeeks.org/stdstringerase-in-cpp/](https://www.geeksforgeeks.org/stdstringerase-in-cpp/)

该函数删除字符串内容的一部分，从而缩短字符串的长度。受影响的字符取决于使用的成员函数版本:
**返回值:** erase()返回*this。

1.  **语法 1:** 删除字符串中的所有字符

```cpp
string& string ::erase ()

```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code to illustrate
// erase() function

#include <iostream>
#include <string>
using namespace std;

// Function to demo erase()
void eraseDemo(string str)
{
    // Deletes all characters
    str.erase();

    cout << "After erase() : ";
    cout << str;
}

// Driver code
int main()
{
    string str("Hello World!");

    cout << "Before erase() : ";
    cout << str << endl;
    eraseDemo(str);

    return 0;
}
```

**输出:**

```cpp
Before erase() : Hello World!
After erase() : 

```

**2。语法 2:** 删除位置“位置”后的所有字符

```cpp
string& string ::erase (size_type pos)
- Throw out_of_range if idx > size().

```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code to illustrate working of
// erase(idx)

#include <iostream>
#include <string>
using namespace std;

// Function to demo erase
void eraseDemo(string str)
{
    // Deletes all characters except first one
    str.erase(1);

    cout << "After erase(idx) : ";
    cout << str;
}

// Driver code
int main()
{
    string str("Hello World!");

    cout << "Before erase(idx) : ";
    cout << str << endl;
    eraseDemo(str);

    return 0;
}
```

**输出:**

```cpp
Before erase(idx) : Hello World!
After erase(idx) : H

```

**3。语法 3:** 从索引 idx 开始，最多擦除*这个的 len 个字符。

```cpp
string& string ::erase (size_type idx, size_type len )
- If len is missing, all remaining characters are removed.
- Throw out_of_range if idx > size().

```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code to illustrate
// erase(size_type idx, size_type len )
#include <iostream>
#include <string>
using namespace std;

// Function to demo erase
void eraseDemo(string str)
{
    // Deletes 4 characters from index number 1
    str.erase(1, 4);

    cout << "After erase : ";
    cout << str;
}

// Driver code
int main()
{
    string str("Hello World!");

    cout << "Before erase : ";
    cout << str << endl;
    eraseDemo(str);

    return 0;
}
```

**输出:**

```cpp
Before erase : Hello World!
After erase : H World!

```

**4。语法 4:** 删除迭代器位置位置的单个字符。

```cpp
string& string ::erase (iterator pos)
- Return the first character after the last character removed
- If no such character is remaining then, returns 
  string::end() i.e. position after the last character.

```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code to illustrate
// erase(iterator pos)

#include <iostream>
#include <string>
using namespace std;

// Function to demo erase
void eraseDemo(string str)
{
    // Deletes character at position 4
    str.erase(str.begin() + 4);

    cout << "After erase : ";
    cout << str;
}

// Driver code
int main()
{
    string str("Hello World!");

    cout << "Before erase : ";
    cout << str << endl;
    eraseDemo(str);

    return 0;
}
```

**输出:**

```cpp
Before erase : Hello World!
After erase : Hell World!

```

**5。语法 5:** 从迭代器位置删除字符。到另一个迭代器位置。

```cpp
string& string ::erase (iterator beg, iterator end )
- Erases all characters of the range [ beg, end)
- Returns end i.e. the first character after the
  last character removed.
- If no such character is remaining then, returns 
  string::end() i.e. position after the last character

```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code to illustrate
// erase(iterator pos, iterator end)

#include <iostream>
#include <string>
using namespace std;

// Function to demo erase
void eraseDemo(string str)
{
    // Deletes all characters between 0th index and
    // str.end() - 6
    str.erase(str.begin() + 0, str.end() - 6);

    cout << "After erase : ";
    cout << str;
}

// Driver code
int main()
{
    string str("Hello World!");

    cout << "Before erase : ";
    cout << str << endl;
    eraseDemo(str);

    return 0;
}
```

**输出:**

```cpp
Before erase : Hello World!
After erase : World!

```

**相关文章:**[STD::string::clear](https://www.geeksforgeeks.org/stdstringclear-in-cpp/)
本文由 **Sakshi Tiwari** 供稿。如果你喜欢极客(我们知道你喜欢！)并愿意投稿，也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。