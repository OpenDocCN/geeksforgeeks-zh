# c++ STL 中的 fill()和 fill_n()函数

> 原文:[https://www . geesforgeks . org/fill-and-fill _ n-functions-in-c-STL/](https://www.geeksforgeeks.org/fill-and-fill_n-functions-in-c-stl/)

一个向量一旦被声明，它的所有值就被初始化为零。下面是演示相同内容的示例代码。

```cpp
// C++ program for displaying the default initialization
// of the vector vect[]
#include<bits/stdc++.h>
using namespace std;

int main() 
{
    // Creating a vector of size 8
    vector<int> vect(8);  

    // Printing default values
    for (int i=0; i<vect.size(); i++)
       cout << ' ' << vect[i];
}
```

输出:

```cpp
0 0 0 0 0 0 0 0
```

如果我们希望将向量初始化为一个特定的值，比如 1，会怎么样？为此，我们可以传递该值以及向量的大小。

```cpp
// C++ program for displaying specified initialization
// of the vector vect[]
#include<bits/stdc++.h>
using namespace std;

int main () 
{
    // Creates a vector of size 8 with all initial
    // values as 1.
    vector<int> vect(8, 1);  

    for (int i=0; i<vect.size(); i++)
       cout << ' ' << vect[i];
}
```

输出:

```cpp
1 1 1 1 1 1 1 1
```

如果我们希望将前 4 个值初始化为 100，将其余 6 个值初始化为 200，会怎么样？
一种方法是手动为向量中的每个位置提供一个值。STL 标准模板库中提供的其他方法是填充和填充 _n.

*   **[fill()](https://www.geeksforgeeks.org/stdfill-function-in-c-stl-with-examples/)**
    The ‘fill’ function assigns the value ‘val’ to all the elements in the range [begin, end), where ‘begin’ is the initial position and ‘end’ is the last position.

    **注意:**请注意，范围中包含“开始”，但不包含“结束”。下面是一个演示“填充”的示例:

    ```cpp
    // C++ program to demonstrate working of fill()
    #include <bits/stdc++.h>
    using namespace std;

    int main ()
    {
      vector<int> vect(8);

      // calling fill to initialize values in the
      // range to 4
      fill(vect.begin() + 2, vect.end() - 1, 4);

      for (int i=0; i<vect.size(); i++)
        cout << vect[i] << " ";

      return 0;
    }
    ```

    **输出:**

    ```cpp
    0 0 4 4 4 4 4 0

    ```

*   **[fill_n()](https://www.geeksforgeeks.org/stdfill_n-function-in-c-stl/)**
    In fill_n(), we specify beginning position, number of elements to be filled and values to be filled. The following code demonstrates the use of fill_n.

    ```cpp
    // C++ program to demonstrate working of fil_n()
    #include <bits/stdc++.h>
    using namespace std;

    int main()
    {
        vector<int> vect(8);  

        // calling fill to initialize first four values
        // to 7
        fill_n(vect.begin(), 4, 7);

        for (int i=0; i<vect.size(); i++)
            cout << ' ' << vect[i];
        cout << '\n';

        // calling fill to initialize 3 elements from 
        // "begin()+3" with value 4
        fill_n(vect.begin() + 3, 3, 4);

        for (int i=0; i<vect.size(); i++)
            cout << ' ' << vect[i];
        cout << '\n';

        return 0;
    }
    ```

    输出:

    ```cpp
     7 7 7 7 0 0 0 0
     7 7 7 4 4 4 0 0

    ```

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论