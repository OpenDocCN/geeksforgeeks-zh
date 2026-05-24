# c++ 中的三元图，带示例

> 原文:[https://www.geeksforgeeks.org/trigraphs-in-c-with-examples/](https://www.geeksforgeeks.org/trigraphs-in-c-with-examples/)

在 C++ 中，**三元组**是一个表示单个字符的**三字符序列**。意思是**三字序列**是从双问号(？？).这些字符是用一个称为三元组的 3 个字符的序列构成的，这组字符被一个单独的字符代替。

<figure class="table">|||

| s。没有。一 | 三字母词 | of equal value |
| --- | --- | --- |
| 1。 | ？？= | # |
| 2。 | ？？/ | \ |
| 3。 | ？？ | ^ |
| 4。 | ？？（ | 【 |
| 5。 | ？？) | 】 |
| 6。 | ？？！ | &#124; |
| 7。 | ？？< | { |
| 8。 | ？？> | } |
| 9。 | ？？- | ~ |

</figure>

**语法:**

```cpp
??=define
Becomes,
#define

```

下面是三元图序列的基本实现示例:

## C++

```cpp
// C++ implementation to 
// illustrate the example 
// of trigraph sequences

# include <iostream>
using namespace std;

??=define MSG "GeeksforGeeks"
??=define Program "C++"

// Driver Code
int main()
??< // Here ??< denotes {
    cout << "My message to " << MSG << endl;
    cout << "My program is " << Program;

    return 0;
??> // Here ??> denotes }
```

**Output:**

```cpp
My message to GeeksforGeeks
My program is C++

```

下面是三元图序列的另一个例子:

## C++

```cpp
// C++ program to demonstrate 
// the example 
// of trigraph sequences

# include <iostream>
using namespace std;

// Here ??= denotes #
??=define Name "Kalpana"
??=define Age "23"
??=define Qualification "B.tech"
??=define From "Delhi"

// Driver Code
int main()
??<
    cout << "My Name is: " << Name << endl;
    cout << "My Age is: " << Age << endl;

    cout << "My Qualification is: "
         << Qualification << endl;
    cout << "I'm From " << From;

    return 0;
??>
```

**Output:**

```cpp
My Name is: Kalpana
My Age is: 23
My Qualification is: B.tech
I'm From Delhi

```