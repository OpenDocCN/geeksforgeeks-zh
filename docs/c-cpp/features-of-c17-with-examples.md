# c++ 17 的特性

> 原文:[https://www . geesforgeks . org/features-of-c17-with-examples/](https://www.geeksforgeeks.org/features-of-c17-with-examples/)

C++ 17 使编写简单、清晰和更具表现力的代码成为可能。C++ 17 中引入的一些特性包括:

*   嵌套命名空间
*   if 和 switch 中的变量声明
*   if constexpr 语句
*   结构化绑定
*   折叠表达式
*   枚举的直接列表初始化

### <u>嵌套命名空间</u>

[名称空间](https://www.geeksforgeeks.org/namespace-in-c/)是一个非常方便的工具来组织和构造代码库，将逻辑上属于同一组的类和函数等组件放在一起。

让我们考虑一个视频游戏引擎的假设代码库。这里，为整个游戏引擎定义了一个命名空间，所以在这个**游戏**引擎中实现的所有类和函数都将在这个公共命名空间下声明。为了做更清晰的定义，你可以在全局命名空间下定义另一个命名空间，比如说[](https://www.geeksforgeeks.org/include-graphics-h-codeblocks/)**，这是一个*子命名空间*，现在把所有执行图形操作的类放在这个命名空间下，以此类推。**

*   ****在 C++ 17 之前:**
    下面是用于嵌套命名空间的语法:**

## **C++**

```cpp
// Below is the syntax for using
// the nested namespace

namespace Game {

    namespace Graphics {

        namespace Physics {

           class 2D {
              ..........
           };
        }
    }
}
```

*   ****c++ 17 时:****

**在 C++ 17 之前，您必须使用这种冗长的语法来声明嵌套命名空间中的类，但是 C++ 17 引入了一个新功能，使得打开嵌套命名空间成为可能，而不需要这种需要重复命名空间[关键字](https://www.geeksforgeeks.org/variables-and-keywords-in-c/)并跟踪左右大括号的忙乱语法。在 C++ 17 中有一个*简洁明了的语法*使用**双冒号** **来引入** **嵌套命名空间**。语法如下:**

## **C++**

```cpp
// Below is the syntax to use the
// nested namespace in one line

namespace Game::Graphics::Physics {

    class 2D {
       ..........
    };
}
```

**这使得代码不太容易出错**，因为不需要注意几级括号。****

### ****<u>if 和 switch 中的变量声明</u>****

******c++ 17 之前:******

****假设一个字符串的[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)，你想用**“$ { content }”替换一个字符串**“ABC”**；**如果它存在于载体中。为此，您可以调用标准的 [*find()*](https://www.geeksforgeeks.org/std-find-in-cpp/) *函数*在矢量中搜索项目，如下所示:****

## **C++**

```cpp
// Below is the approach for replace
// any string with another string
// in vector of string

vector<string> str

    // Find and replace abc with $$
    const auto it
    = find(begin(str), end(str), "abc");

    if (it != end(str)) {
       *it = "${content}quot;;
    }
```

****说明:****

*   **查找算法将返回一个指向匹配字符串的迭代器。**
*   **现在，如果我们再次想要用同一向量中的其他字符串替换另一个字符串，那么对于这个，遵循如上所示的相同方法，因为您将重复相同的代码，只需要*将迭代器*的名称更改为其他名称。**
*   **因为在同一个范围内声明两个以上同名迭代器会产生[编译错误](https://www.geeksforgeeks.org/difference-between-compile-time-errors-and-runtime-errors/)。名称更改选项将会工作，但是如果有几个字符串需要替换，但是这种方法效率不高。**

****当 C++ 17:**
为了处理这种情况 C++ 17 给出了一个更好的选择，通过在 **if 语句**中声明变量如下所示:**

## **C++**

```cpp
// Below is the syntax for replacing a
// string in vector of string in C++ 17

if (const auto it = find(begin(str),
                         end(str),
                         "abc");
    it != end(str)) {
    *it = "${content}quot;;
}
```

**现在迭代器**“it”**的范围在 if 语句本身内，同样的迭代器名称也可以用来替换其他字符串。
使用 [switch 语句](https://www.geeksforgeeks.org/switch-statement-cc/)使用下面给出的语法可以完成同样的事情:**

```cpp
switch (initial-statement; variable) {
  ....
  // Cases
}
```

**下面是在给定向量中替换一些定义字符串的程序，该程序只在 C++ 17 中运行:**

## **C++**

```cpp
// C++ 17 code to demonstrate if constexpr

#include <algorithm>
#include <iostream>
#include <string>
#include <vector>
using namespace std;

// Helper function to print content
// of string vector
void print(const string& str,
           const vector<string>& vec)
{
    cout << str;
    for (const auto& i : vec) {
        cout << i << " ";
    }
    cout << endl;
}

// Driver Code
int main()
{
    // Declare vector of string
    vector<string> vec{ "abc", "xyz",
                        "def", "ghi" };

    // Invoke print helper function
    print("Initial vector: ", vec);

    // abc -> $$, and the scope of "it"

    // Function invoked for passing
    // iterators from begin to end
    if (const auto it = find(begin(vec),
                             end(vec), "abc");

        // Check if the iterator reaches
        // to the end or not
        it != end(vec)) {

        // Replace the string if an
        // iterator doesn't reach end
        *it = "${content}quot;;
    }

    // def -> ###
    // Replace another string using
    // the same iterator name
    if (const auto it
                 = find(begin(vec),
                        end(vec), "def");

        it != end(vec)) {
        *it = "###";
    }
    print("Final vector: ", vec);
    return 0;
}
```