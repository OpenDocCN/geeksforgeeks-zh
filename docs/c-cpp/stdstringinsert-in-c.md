# std::string::insert()在 C++ 中

> 哎哎哎:# t0]https://www . geeksforgeeks . org/stdstring insert-in-c/

**insert()** 用于在字符串中的指定位置插入字符。它支持各种语法来简化相同的操作，这里我们将描述它们。

**语法 1:** 从索引 idx 开始插入字符串的字符。

```cpp
string& string::insert (size_type idx, const string& str)
idx :is the index number
str : is the string from which characters is to be picked to insert 
Returns *this.
Errors: 
Throws out_of_range if idx > size().
Throws length_error if the resulting size exceeds the maximum number of characters.

```

```cpp
// CPP code for insert (size_type idx, const string& str)

#include <iostream>
#include <string>

using namespace std;

// Function to demonstrate insert
void insertDemo(string str1, string str2)
{

    // Inserts str2 in str1 starting 
    // from 6th index of str1
    str1.insert(6, str2);
    cout << "Using insert : ";
    cout << str1;
}

// Driver code
int main()
{
    string str1("Hello World! ");
    string str2("GeeksforGeeks ");

    cout << "Original String : " << str1 << endl;
    insertDemo(str1, str2);

    return 0;
}
```

输出:

```cpp
Original String : Hello World! 
Using insert : Hello GeeksforGeeks World! 

```

**语法 2:** 最多插入 str 的 str_num 个字符，从索引 str_idx 开始。

```cpp
string& string::insert (size_type idx, const string& str, size_type str_idx,
                                                           size_type str_num)
idx : is the index number where insertion is to be made.
str : is the string from which characters are to be picked to insert.
str_idx : is the index number in str.
str_num : is the number of characters to be inserted from str.
Returns *this.
Errors: 
Throws out_of_range if idx > size().
Throws out_of_range if str_idx > str.size().
Throws length_error if the resulting size exceeds the maximum number of characters.

```

```cpp
// CPP code for insert (size_type idx, const string& str, 
// size_type str_idx, size_type str_num)

#include <iostream>
#include <string>

using namespace std;

// Function to demonstrate insert
void insertDemo(string str1, string str2)
{

    // Inserts 6 characters from index number
    // 8 of str2 at index number 6 of str1 
    str1.insert(6, str2, 8, 6);
    cout << "Using insert : ";
    cout << str1;
}

// Driver code
int main()
{
    string str1("Hello World! ");
    string str2("GeeksforGeeks ");

    cout << "Original String : " << str1 << endl;
    insertDemo(str1, str2);

    return 0;
}
```

输出:

```cpp
Original String : Hello World! 
Using insert : Hello Geeks World! 

```

**语法 3:** 插入 C 字符串 cstr 的字符，使新字符以索引 idx 开始。

```cpp
string& string::insert (size_ type idx, const char* cstr)
idx : is the index number where insertion is to be made.
*cstr : is the pointer to the C-string which is to be inserted.
Returns *this.
Errors: 
Throws out_of_range if idx > size().
Throws length_error if the resulting size exceeds the maximum number of characters.

```

**注意:** cstr 不能是空指针(空)。

```cpp
// CPP code for insert(size_ type idx, const char* cstr)

#include <iostream>
#include <string>

using namespace std;

// Function to demonstrate insert
void insertDemo(string str)
{

    // Inserts " are " at 5th index of str
    str.insert(5, " are ");
    cout << "Using insert : ";
    cout << str;
}

// Driver code
int main()
{
    string str("GeeksforGeeks ");

    cout << "Original String : " << str << endl;
    insertDemo(str);

    return 0;
}
```

输出:

```cpp
Original String : GeeksforGeeks 
Using insert : Geeks are forGeeks 

```

**语法 4:** 插入字符数组字符的 chars_len 字符，使新字符以索引 idx 开始。

```cpp
string& string::insert (size_type idx, const char* chars, size_type chars_len)
idx : index number where insertion is to be made.
*chars : is the pointer to the array.
chars_len : is the number of characters to be inserted from character array.
Returns : *this
Errors: 
Throws out_of_range if idx > size().
Throws length_error if the resulting size exceeds the maximum number of characters.

```

**注意**:字符必须至少有 chars_len 个字符。

```cpp
// CPP code for insert (size_type idx, const char* chars, 
// size_type chars_len)

#include <iostream>
#include <string>

using namespace std;

// Function to demonstrate insert
void insertDemo(string str)
{

    // Inserts 10 characters from" are here "
    // at 5th index of str
    str.insert(5, " are here ", 10);
    cout << "Using insert : ";
    cout << str;
}

// Driver code
int main()
{
    string str("GeeksforGeeks ");

    cout << "Original String : " << str << endl;
    insertDemo(str);

    return 0;
}
```

输出:

```cpp
Original String : GeeksforGeeks 
Using insert : Geeks are here forGeeks 

```

**语法 5:** 在 idx 指定的位置插入字符 c 的出现次数。

```cpp
string& string ::insert (size_type idx, size_type num, char c)
idx : is the index number where insertion is to be made.
c : is the character to be inserted.
num : is the number of repetition of character c
Returns : *this
Errors: 
Throw out_of_range if idx > size().
Throw length_error if the resulting size exceeds the maximum number of characters.
```

```cpp
// CPP code for :insert (size_type idx, size_type num, char c)

#include <iostream>
#include <string>

using namespace std;

// Function to demonstrate insert
void insertDemo(string str)
{

    // Inserts at 5th index,
    // 5 occurrences of '{content}apos;
    str.insert(5, 5, '{content}apos;);
    cout << "Using insert : ";
    cout << str;
}

// Driver code
int main()
{
    string str("**********");

    cout << "Original String : " << str << endl;
    insertDemo(str);

    return 0;
}
```

输出:

```cpp
Original String : **********
Using insert : *****$$$*****

```

**语法 6:** 在迭代器位置指定的位置插入字符 c 的出现次数。

```cpp
void string ::insert (iterator pos, size_type num, char c)
pos : is the position of iterator.
c : is the character which is to be inserted.
Returns : *this
Errors: 
Throws out_of_range if pos > size().
Throws length_error if the resulting size exceeds the maximum number of characters.

```

```cpp
// CPP code for :insert (iterator pos, size_type num, char c)
#include <iostream>
#include <string>

using namespace std;

// Function to demonstrate insert
void insertDemo(string str)
{

    // Inserts 5 occurrences of '{content}apos;
    // at position str.begin() + 5
    str.insert(str.begin() + 5, 5, '{content}apos;);
    cout << "Using insert : ";
    cout << str;
}

// Driver code
int main()
{
    string str("**********");

    cout << "Original String : " << str << endl;
    insertDemo(str);

    return 0;
}
```

输出:

```cpp
Original String : **********
Using insert : *****$$$*****

```

**语法 7:** 在迭代器 pos 引用的字符之前插入字符 c 的副本。

```cpp
iterator string ::insert (iterator pos, char c )
pos : is the position of iterator.
c : is the character which is to be inserted.
Returns :  iterator pointing to the first character inserted.
Error: 
Throws length_error if the resulting size exceeds the maximum number of characters.

```

```cpp
// CPP code for :insert (iterator pos, char c )
#include <iostream>
#include <string>

using namespace std;

// Function to demonstrate insert
void insertDemo(string str)
{
     std::string::iterator pos;

    // Inserts '{content}apos; at position
    //  str.begin() + 5
    pos = str.insert(str.begin()+5,'{content}apos;);
    cout << "Using insert : ";
    cout << str << endl;
    cout << "Value at Iterator returned : " << *pos;

}

// Driver code
int main()
{
    string str("**********");

    cout << "Original String : " << str << endl;
    insertDemo(str);

    return 0;
}
```

输出:

```cpp
Original String : **********
Using insert : *****$*****
Value at Iterator returned : $

```

**语法 8:** 在迭代器 pos 引用的字符之前插入范围[ beg，end 的所有字符。

```cpp
void string ::insert (iterator pos, InputIterator beg, InputIterator end )
pos : is the iterator position.
beg, end : Input iterators to the initial and final positions in a sequence.
Error: 
Throws length_error if the resulting size exceeds the maximum number of characters.

```

```cpp
// CPP code for insertinsert (iterator pos, InputIterator beg,
// InputIterator end )

#include <iostream>
#include <string>

using namespace std;

// Function to demonstrate insert
void insertDemo(string str1, string str2)
{

    // Inserts str2.begin() + 5 ,  str2.end() - 6
    // at position str1.begin() + 6
    str1.insert(str1.begin() + 6, str2.begin() + 5 ,  str2.end() - 6);
    cout << "Using insert : ";
    cout << str1;
}

// Driver code
int main()
{
    string str1("Hello  World! ");
    string str2("GeeksforGeeks ");

    cout << "Original String : " << str1 << endl;
    insertDemo(str1, str2);

    return 0;
}
```

输出:

```cpp
Original String : Hello World! 
Using insert : Hello forWorld! 

```

本文由**萨基提瓦里**供稿。如果你喜欢极客(我们知道你喜欢！)并愿意投稿，也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者将文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。