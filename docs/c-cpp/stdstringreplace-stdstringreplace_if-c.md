# std::string::replace，std::string::replace_if 在 C++ 中

> 哎哎哎:# t0]https://www . geeksforgeeks . org/stdstring replace-stdstring replace _ if-c/

### **替换()**

它将等于旧值的范围[第一个，最后一个]中的每个元素替换为新值。该函数使用运算符==将各个元素与 old_value 进行比较。

```cpp
template <class ForwardIterator, class T>
 void replace (ForwardIterator first, ForwardIterator last,
 const T& old_value, const T& new_value);
first, last : the range of elements to process
old_value : the value of elements to replace
new_value : the value to use as replacement
```

## C++

```cpp
// CPP code to demonstrate replace()

#include <iostream>
using namespace std;

// Function for demonstration
void replaceDemo(string s1, string s2, string s3, string s4)
{
    // Replaces 7 characters from 0th index by s2
    s1.replace(0, 7, s2);
    cout << s1 << endl;

    // Replaces 3 characters from 0th index with "Hello"
    s4.replace(0, 3, "Hello ");
    cout << s4 << endl;

    // Replaces 5 characters from 6th index of s4 with
    // 5 characters from 0th of s3
    s4.replace(6, 5, s3, 0, 5);
    cout << s4 << endl;

    // Replaces 5 characters from 6th index of s4 with
    // 6 characters from string "to all"
    s4.replace(6, 5, "to all", 6);
    cout << s4 << endl;

    // Replaces 1 character from 12th  index of s4 with
    // 3 copies of '!'
    s4.replace(12, 1, 3, '!');
    cout << s4 << endl;
}

// Driver code
int main()
{
    string s1 = "Example of replace";
    string s2 = "Demonstration";
    string s3 = "GeeksforGeeks";
    string s4 = "HeyWorld !";

    replaceDemo(s1, s2, s3, s4);
    return 0;
}
```

**输出:**

```cpp
Demonstration of replace
Hello World !
Hello Geeks !
Hello to all !
Hello to all!!!!
```

### **更换 _if**

replace_if()用 newValue 替换一元谓词(即 op(elem))为其生成 true 的范围[第一个，最后一个]中的每个元素。

```cpp
template <class ForwardIterator, class UnaryPredicate, class T>
 void replace_if (ForwardIterator first, ForwardIterator last,
 UnaryPredicate pred, const T& new_value );
Unary predicate are just functions that take a single parameter 
and return a Boolean value. It is used to check whether an 
element fits the criterion
```

## C++

```cpp
// CPP code to demonstrate replace_if()

#include <iostream>
#include <vector>
#include <algorithm> // Header file for replace_if
using namespace std;

// Function to check if character is vowel or not
bool IsVowel(char ch)
{
    return (ch == 'A' || ch == 'E' || ch == 'I' || ch == 'O' || ch == 'U');
}

// Function to replace all vowels with 'V'
void replace_ifDemo(vector<char>&v)
{
    replace_if(v.begin(), v.end(), IsVowel, 'V');
}

// Function to print content of vector
void print(vector<char>&v)
{
    int len = v.size();
    for (int i = 0; i < len; i++)
        cout << v[i] << " ";
    cout << endl;
}

// Driver code
int main()
{
    vector<char> v;

    for (int i = 0; i <= 6; i++)
        v.push_back('A' + i);
    cout << "Before replace_if " <<": ";
    print(v);
    replace_ifDemo(v);

    cout << "After replace_if " << ": ";
    print(v);

    return 0;
}
```

**输出:**

```cpp
Before replace_if : A B C D E F G 
After replace_if : V B C D V F G 
```

**相关文章:**[STD::string::replace _ copy()，STD::string::replace _ copy _ if](https://www.geeksforgeeks.org/stdstringreplace_copy-stdstringreplace_copy_if-cpp/)
本文由 **Sakshi Tiwari** 供稿。如果你喜欢极客(我们知道你喜欢！)并愿意投稿，也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。