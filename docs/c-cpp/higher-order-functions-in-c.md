# c++ 中的高阶函数

> 原文:[https://www.geeksforgeeks.org/higher-order-functions-in-c/](https://www.geeksforgeeks.org/higher-order-functions-in-c/)

**高阶函数**是以函数为自变量的函数。它被用在功能语言中，而在 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中却没有使用，尽管自从 C++ 11 给了我们 [lambdas](https://www.geeksforgeeks.org/lambda-expression-in-c/) 和‘STD::function’后，这种情况正在慢慢改变……而且人们经常没有意识到‘STD::function’并不是一个能够填充所有用例的工具。在本文中，我们将解释如何将函数作为参数传递给不同的调用函数。

**语法:**

> return_type function_name(函数< return_type fun_name(参数列表)，其他函数参数)

**参数:**上图中**函数 _ 名称**以一个名为 **fun_name** 的函数为自变量。**函数名**和 **fun_name** 都可以有一些额外的参数。

下面是同样的说明:

## C++ 14

```cpp
// C++ program to illustrate the higher
// order function in C++
#include <bits/stdc++.h>
using namespace std;

// Function that will be passed as an
// arguments to calling function
bool Parser(string x)
{
    // Check if string start
    // with alphabet 'R'
    return x[0] == 'R';
}

// Function that takes function as
// an arguments
vector<string> Parse(vector<string> a,
                     function<bool(string)> Parser)
{
    vector<string> ans;

    // Traverse the vector a
    for (auto str : a) {
        if (Parser(str)) {
            ans.push_back(str);
        }
    }

    // Return the resultant vector
    return ans;
}

// Driver Code
int main()
{
    vector<string> dict = { "geeks", "Rxop",
                            "Rka", "for" };

    // Function Call for Higher
    // Order Functions
    vector<string> ans = Parse(dict, Parser);

    // Print the results
    for (auto str : ans) {
        cout << str << " ";
    }

    return 0;
}
```

**Output:** 

```cpp
Rxop Rka
```

**<u>高阶函数的优势</u> :**

通过使用高阶函数，可以解决许多问题。例如，要构建一个以列表和另一个函数作为输入的函数，请将该函数应用于该列表的每个元素，并返回新列表。在 Haskell 中，使用名为 map 的内置高阶函数可以非常容易地做到这一点。[地图](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)的定义是:

```cpp
map :: (a -> b) -> [a] -> [b] 
map _ [ ] = [ ] 
map f (x : xs) = f x : map f xs
```

在这里，

*   第一行是函数初始化。
*   元素符号代表“是类型”。
*   **【a】**代表相似元素的列表，实体已经写在最后 **- >之后**永远是函数的返回类型。Haskell 中的函数总是只返回一个实体。
*   **(a- > b)** 定义一个从‘a’到‘b’的函数。我们用递归来定义地图，
    **【】**表示空列表， **_** 表示“任何”。
*   第二行描述了如果输入了空列表和任何函数，那么输出将是空列表。
*   **x: xs** 用于从列表中逐个取出元素，x 为第一个元素(头)，xs 为剩余列表(尾)。 **:** 符号代表串联。简而言之，第三行是从列表中取出每个元素，并对其应用函数**‘f’**，然后将其与剩余的列表连接起来。