# 在 C++ 中将向量传递给函数

> 原文:[https://www.geeksforgeeks.org/passing-vector-function-cpp/](https://www.geeksforgeeks.org/passing-vector-function-cpp/)

当我们[将一个数组传递给一个函数](https://www.geeksforgeeks.org/how-arrays-are-passed-to-functions-in-cc/)时，一个[指针](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/)实际上被传递了。但是，传递向量有两种方法:

1.  Pass value
2.  By reference

当一个[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)被传递给一个函数时，该向量的一个副本被创建。向量的这个新副本随后被用在函数中，因此，函数中对向量所做的任何更改都不会影响原始向量。

例如，我们可以在程序下面看到，在函数内部所做的更改不会反映到外部，因为函数有一个副本。

**示例(通过值):**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate that when vectors
// are passed to functions without &, a copy is
// created.
#include <bits/stdc++.h>
using namespace std;

// The vect here is a copy of vect in main()
void func(vector<int> vect) { vect.push_back(30); }

int main()
{
    vector<int> vect;
    vect.push_back(10);
    vect.push_back(20);

    func(vect);

    // vect remains unchanged after function
    // call
    for (int i = 0; i < vect.size(); i++)
        cout << vect[i] << " ";

    return 0;
}
```

**Output**

```cpp
10 20 
```

传递值会保持原始向量不变，并且不会修改向量的原始值。然而，在向量很大的情况下，上述传递方式可能也需要花费很多时间。所以，通过参考是个好主意。

**示例(通过引用):**

## CPP

```cpp
// C++ program to demonstrate how vectors
// can be passed by reference.
#include <bits/stdc++.h>
using namespace std;

// The vect is passed by reference and changes
// made here reflect in main()
void func(vector<int>& vect) { vect.push_back(30); }

int main()
{
    vector<int> vect;
    vect.push_back(10);
    vect.push_back(20);

    func(vect);

    for (int i = 0; i < vect.size(); i++)
        cout << vect[i] << " ";

    return 0;
}
```

**输出**

```cpp
10 20 30 
```

通过引用传递节省了大量时间，并使代码的实现更快。

> **注意:**如果我们不想让函数修改向量，我们可以把它作为**常量**引用传递。

## CPP

```cpp
// C++ program to demonstrate how vectors 
// can be passed by reference with modifications 
// restricted. 
#include<bits/stdc++.h> 
using namespace std; 

// The vect is passed by constant reference 
// and cannot be changed by this function. 
void func(const vector<int> &vect) 
{ 
    // vect.push_back(30);   // Uncommenting this line would 
                            // below error 
    // "prog.cpp: In function 'void func(const std::vector<int>&)': 
    // prog.cpp:9:18: error: passing 'const std::vector<int>' 
    // as 'this' argument discards qualifiers [-fpermissive]" 

    for (int i = 0; i < vect.size(); i++) 
    cout << vect[i] << " "; 
} 

int main() 
{ 
    vector<int> vect; 
    vect.push_back(10); 
    vect.push_back(20); 

    func(vect); 

    return 0; 
}
```

**输出**

```cpp
10 20 
```

本文由 **Kartik** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。