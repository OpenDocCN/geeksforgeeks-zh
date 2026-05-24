# c++ 中的 std::stoul 和 STD::stoll

> 哎哎哎:# t0]https://www . geeksforgeeks . org/stdestoul-stdstobull-c/

**std::stoul**

将字符串转换为无符号整数。解析字符串，将其内容解释为指定基数的整数，该整数作为无符号长值返回。

```cpp
unsigned long stoul 
(const string&  str, size_t* idx = 0, int base = 10);
Parameters :
str : String object with the 
representation of an integral number.
idx : Pointer to an object of type size_t, 
whose value is set by the function to position of the 
next character in str after the numerical value.
This parameter can also be a null pointer, in which case
it is not used.
base : Numerical base (radix) that determines
the valid characters and their interpretation.
If this is 0, the base used is determined by the format in
the sequence.Notice that by default this argument is 10, not 0\. 

```

**STD::sto null**

将字符串转换为无符号长整型。解析字符串，将其内容解释为指定基数的整数，该整数作为无符号 long 类型的值返回。

```cpp
unsigned long long stoull 
(const string&  str, size_t* idx = 0, int base = 10);
Parameters :
str : String object with the representation 
of an integral number.
idx : Pointer to an object of type size_t,
whose value is set by the function to position of the next 
character in str after the numerical value. This parameter can 
also be a null pointer, in which case it is not used.
base : Numerical base (radix) that determines 
the valid characters and their interpretation.
If this is 0, the base used is determined by the format in the
sequence. Notice that by default this argument is 10, not 0\. 

```

**示例:**

```cpp
Input : FF
Output : 255

Input : FFFFF
Output : 

```

```cpp
// CPP code to convert hexadecimal
// string to int
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Hexadecimal string
    string str = "FF";

    // Converted integer
    unsigned long num = stoul(str, nullptr, 16);

    // Printing the integer
    cout << num << "\n";

    // Hexadecimal string
    string st = "FFFFFF";

    // Converted long long
    unsigned long long val = stoull(st, nullptr, 16);

    // Printing the long long
    cout << val;
    return 0;
}
```

输出:

```cpp
255
16777215

```

**另一个例子:** **程序比较两个包含十六进制值的字符串**
这里使用 **stoul** ，但是如果数字超过无符号长值，则使用**stoall**。

```cpp
// CPP code to compare two
// hexadecimal string
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Hexadecimal string
    string s1 = "4F";
    string s2 = "A0";

    // Converted integer
    unsigned long n1 = stoul(s1, nullptr, 16);
    unsigned long n2 = stoul(s2, nullptr, 16);

    // Compare both string
    if (n1 > n2)
        cout << s1 << " is greater than " << s2;
    else if (n2 > n1)
        cout << s2 << " is greater than " << s1;
    else
        cout << "Both " << s1 << " and " << s2 << " are equal";
    return 0;
}
```

输出:

```cpp
A0 is greater than 4F

```

本文由**沙钦·毕斯特**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。