# 用户定义大小的 c++ 2D 向量

> 原文:[https://www . geeksforgeeks . org/2d-vector-in-CPP-带有用户定义的大小/](https://www.geeksforgeeks.org/2d-vector-in-cpp-with-user-defined-size/)

2D 矢量是矢量的[矢量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)。像 2D 数组一样，我们可以声明并赋值给 2D 向量！
假设你熟悉 C++ 中的法向量，借助一个例子，我们演示 2D 向量与法向量的区别如下:

## C++

```cpp
/* Vectors belong to a C++ library
   called STL so we need to import
   it first! */
#include <vector>
using namespace std;
int main()
{
    /*
    In the case of a normal vector we initialize it as:

    1\. vector<datatype> variable_name

    Now in the case of a 2D vector all we do is create
    a vector of datatype vector.

    We simply replace "datatype" with "vector<int>":

    1\. vector<vector<int>> variable_name

    That's literally it! We just created a 2D vector!
    On line 23 below we declare an actual 2D vector
    named "vect".
    */

    vector<vector<int>> vect;

    return 0;
}
```

在 2D 向量中，每个元素都是向量。

## C++

```cpp
/* C++ code to demonstrate a 2D vector
   with elements(vectors) inside it. */
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    /*
    Below we initialize a 2D vector
    named "vect" on line 12 and then
    we declare the values on
    line 14, 15 and 16 respectively.
    */

    vector<vector<int>> vect
    {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };

    /*
    Now we print the values that
    we just declared on lines
    14, 15 and 16 using a simple
    nested for loop.
    */

    for (int i = 0; i < vect.size(); i++)
    {
        for (int j = 0; j < vect[i].size(); j++)
        {
            cout << vect[i][j] << " ";
        }   
        cout << endl;
    }

    return 0;
}
```

**Output**

```cpp
1 2 3 
4 5 6 
7 8 9 
```

访问向量元素的另一种方法是:

## C++

```cpp
/* C++ code to demonstrate a 2D vector
   with elements(vectors) inside it. */
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    /*
    Below we initialize a 2D vector
    named "vect" on line 12 and then
    we declare the values on
    line 14, 15 and 16 respectively.
    */

    vector<vector<int>> vect
    {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };

    /*
    Now we print the values that
    we just declared on lines
    14, 15 and 16 using a simple
    nested for loop with the help of iterator.
    */

    /*
    vector<vector<int>> vect
    We can divide this declaration to two parts, which will
    help us to understand the below concepts.

    1\. vect is a 2D vector consisting multiple elements of type vector<int>.
    2\. vector<int> is a 1D vector consisting of multiple int data.

    So we can use iterator provided by STL instead of
    i,j variable used in for loop. It can reduce the error which can
    happen wrt to i, j operations(i++, j++)    

    In the below code we are using iterator to access the vector elements.
    1\. We are getting vect1D vectors of type vector<int> from the 2D vector vect.
    2\. We are getting int elements to x from the vector<int> vect 1D vector.

    */

    for (vector<int> vect1D : vect)
    {
        for (int x : vect1D)
        {
            cout << x << " ";
        }   
        cout << endl;
    }

    return 0;
}
```

**Output**

```cpp
1 2 3 
4 5 6 
7 8 9 
```

像 Java 的交错数组一样，2D 向量的每个元素可以包含不同数量的值。

## C++

```cpp
/*
C++ program to demonstrate a 2D vector where
each of its elements is of different size.
*/
#include <iostream>
#include <vector>
using namespace std;
int main()
{
    /*
    We initialize a 2D vector
    named "vect" on line 16 with
    different number of values
    in each element.
    */

    vector<vector<int>> vect
    {
        /* Element one with 2 values in it. */
        {1, 2},

        /* Element two with 3 values in it. */
        {4, 5, 6},

         /* Element three with 4 values in it. */
        {7, 8, 9, 10}
    };

    /*
    Now we print the vector that we
    just defined using a simple
    nested for loop.
    */

    for (int i = 0; i < vect.size(); i++)
    {
        for (int j = 0; j < vect[i].size(); j++)
        {
            cout << vect[i][j] << " ";
        }   
        cout << endl;
    }
    return 0;
}   
```

**Output**

```cpp
1 2 
4 5 6 
7 8 9 10 
```

**练习题:**用不同大小的列定义 2D 向量。
例子:

```cpp
Input : Number of rows : 5 
        Number of columns in rows : 
        2 3 4 5 1
Output : 1 2
         1 2 3
         1 2 3 4
         1 2 3 4 5 
         1

Input : Number of rows : 3
        Number of columns in rows : 
        3 2 1

Output : 1 2 3
         1 2
         1
```

2D 向量通常被视为内部有“行”和“列”的矩阵。在引擎盖下，它们实际上是 2D 矢量的元素。
我们首先声明一个名为“row”的整数变量，然后声明一个名为“column”的数组，该数组将保存每行的大小值。

之后，我们继续按照列的大小初始化每行的内存。

## C++

```cpp
/*
C++ program to create a 2D vector where
every row has a certain number of values
as defined by the user.(On line 13)
*/  

#include <iostream>
#include <vector>
using namespace std;
int main()
{

    /* Here we tell how many rows
    the 2D vector is going to have. */
    int row = 5;

    /* We define the number of values
    each row is supposed to have. */
    int column[] = {5, 3, 4, 2, 1};

    /*
    We now create a vector of vector with size
    equal to row.
    */

    vector<vector<int>> vec(row);
    /*
    On line 21 we created a 2D vector and assigned
    it a capacity of "row"(in this case 5) units.
    */

    /*
    Now we will proceed to create the structure of
    our 2D vector by assigning the value of rows and
    columns through a nested for loop.
    */

    for(int i = 0; i < row; i++)
    {  
        /* Declaring the size of the column. */
        int col = column[i];

        /*
        On the 43rd line we declare the
        i-th row to the size of the column.
        We create a normal vector of capacity "col" which
        in every iteration of the for loop will define the
        values inside of each row.
        */
        vec[i] = vector<int>(col);
        for(int j = 0; j < col; j++)
        {
            vec[i][j] = j + 1;
        }   
    }

    /*
    We now finally use a simple nested for loop
    to print the 2D vector that we just created above.
    */

    for(int i = 0; i < row; i++)
    {
        for (int j = 0; j < vec[i].size(); j++)
        {
            cout << vec[i][j] << " ";
        }   
        cout << endl;
    }
    return 0;
}
```

**Output**

```cpp
1 2 3 4 5 
1 2 3 
1 2 3 4 
1 2 
1 
```

**另一种方法**
假设我们想要初始化一个由**“n”**行和**“m”**列组成的 2D 向量，值为 0。

## C++

```cpp
// CPP program
#include <iostream>
#include <vector>
using namespace std;
int main()
{
    int n = 3;
    int m = 4;

    /*
    We create a 2D vector containing "n"
    elements each having the value "vector<int> (m, 0)".
    "vector<int> (m, 0)" means a vector having "m"
    elements each of value "0".
    Here these elements are vectors.
    */
    vector<vector<int>> vec( n , vector<int> (m, 0));

    for(int i = 0; i < n; i++)
    {
        for(int j = 0; j < m; j++)
        {
            cout << vec[i][j] << " ";
        }
        cout<< endl;
    }

    return 0;
}
```

**Output**

```cpp
0 0 0 0 
0 0 0 0 
0 0 0 0 
```

**又一种方法:**
假设我们想要创建一个由**【n】**行和**【m】**列和输入值组成的 2D 向量。

## C++

```cpp
// CPP program
#include <iostream>
#include <vector>
using namespace std;
int main()
{
    int n = 4;
    int m = 5;

    /*
    Create a vector containing "n"
    vectors each of size "m".
    */
    vector<vector<int>> vec( n , vector<int> (m));

    for(int i = 0; i < n; i++)
    {
        for(int j = 0; j < m; j++)
        {
            vec[i][j] = j + i + 1;
        }
    }

    for(int i = 0; i < n; i++)
    {
        for(int j = 0; j < m; j++)
        {
            cout << vec[i][j] << " ";
        }
        cout << endl;
    }

   return 0;
}
```

**Output**

```cpp
1 2 3 4 5 
2 3 4 5 6 
3 4 5 6 7 
4 5 6 7 8 
```

我们希望您在离开本文时对 2D 向量有更好的理解，并且现在有足够的信心自己应用它们。

本文由**阿米特·维尔马**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。