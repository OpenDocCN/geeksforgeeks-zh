# 如何在 C++ 中将单个字符转换为字符串？

> 原文:[https://www . geesforgeks . org/如何将单字符转换为 cpp 中的字符串/](https://www.geeksforgeeks.org/how-to-convert-a-single-character-to-string-in-cpp/)

如何将单个字符转换为字符串对象？
示例:

```cpp
Input :  x = 'a'
Output : string s = "a"

Input :  x = 'b'
Output : string s = "b"
```

想法是使用[字符串类](https://www.geeksforgeeks.org/c-string-class-and-its-applications/)，它有一个构造函数，允许我们指定
字符串的大小作为第一个参数，指定大小的字符作为第二个参数。

**这叫做类填充构造函数。**

```cpp
// Create a string of size n and fill
// the string with character x.
string s(size_t n, char x);
```

注- **size_t** 是无符号长整型的 typedef，因此我们不应该传递负参数。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to get a string from single
// character.
#include<bits/stdc++.h>
using namespace std;

string getString(char x)
{
    // string class has a constructor
    // that allows us to specify size of
    // string as first parameter and character
    // to be filled in given size as second
    // parameter.
    string s(1, x);

    return s;  
}

int main() {
  cout << getString('a');
  return 0;
}
```

**Output**

```cpp
a
```

然而，还有许多其他方法可以将字符转换成字符串。上面提到的方法只在初始化字符串实例时有效。

## 1-使用=/+=运算符

这是一个非常基本的方法，这些操作符被重载来分配或追加一个字符。

## C++

```cpp
// CPP program to get a string from single
// character.
#include<bits/stdc++.h>
using namespace std;

int main() {
  char ex = 'G';
  string str;

  // Using += operator (here we append character to end of string)
  str += ex;
  cout << str << endl;

  // using = operator (overwrites the string)
  str = "GeekForGeeks";
  str = ex;
  cout << str << endl;
}
```

**Output**

```cpp
G
G

```

## 2-标准::字符串::追加()

这种方法与上面讨论的+=运算符类似，但它给了我们另一个优势。通过使用这种方法，我们可以添加任意多的字符。

```cpp
// appends n copy of character x at end of string
string s(size_t n, char x);
```

## C++

```cpp
// CPP program to get a string from single
// character.
#include<bits/stdc++.h>
using namespace std;

int main() {
  string str;
  str.append(1, 'G');
  cout << str << endl;
}
```

**Output**

```cpp
G

```

## 3- std::string::assign()

这个方法与上面讨论的=运算符类似，但它给了我们另一个优势。通过使用这种方法，我们可以添加任意多的字符。

```cpp
// assigns n copy of character x to the string
string s(size_t n, char x);
```

## C++

```cpp
// CPP program to get a string from single
// character.
#include<bits/stdc++.h>
using namespace std;

int main() {
  string str = "GeekForGeeks";
  // assign method overwrites initial content
  str.assign(1, 'G');
  cout << str << endl;
}
```

**Output**

```cpp
G

```

## 4 小时::stringstream

这种方法在使用中可能比较少见。我个人不喜欢这种方法，除非我广泛使用它。例如，如果您的程序有多个转换，如字符串到 int、floats 等，您可以使用它。

## C++

```cpp
// CPP program to get a string from single
// character by stringstream.
#include<bits/stdc++.h>
using namespace std;

int main() {
  stringstream stream;

  // adding our character to stream
  char ex = 'G';
  stream << ex;

  // retrieving back our input into string
  string str;
  stream >> str;

  cout << str << endl;
}
```

**Output**

```cpp
G

```

这些是我们可以从字符串中获取字符的一些方法。然而，还有很多方法，如使用替换，插入方法，但这是不必要的，相当罕见。