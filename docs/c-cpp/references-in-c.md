# c++ 中的引用

> 原文:[https://www.geeksforgeeks.org/references-in-c/](https://www.geeksforgeeks.org/references-in-c/)

当变量被声明为引用时，它将成为现有变量的替代名称。可以通过在声明中放入“&”将变量声明为引用。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include<iostream>
using namespace std;

int main()
{
  int x = 10;

  // ref is a reference to x.
  int& ref = x;

  // Value of x is now changed to 20
  ref = 20;
  cout << "x = " << x << endl ;

  // Value of x is now changed to 30
  x = 30;
  cout << "ref = " << ref << endl ;

  return 0;
}
```

**输出:**

```cpp
 x = 20
ref = 30
```

**应用:**

1.  **Modify the passed parameters in a function**: If a function receives a reference to a variable, it can modify the value of the variable. For example, the following program variables are swapped using references.

    ## 卡片打印处理机（Card Print Processor 的缩写）

    ```cpp
    #include<iostream>
    using namespace std;

    void swap (int& first, int& second)
    {
        int temp = first;
        first = second;
        second = temp;
    }

    int main()
    {
        int a = 2, b = 3;
        swap( a, b );
        cout << a << " " << b;
        return 0;
    }
    ```

    **输出:**

    ```cpp
     3 2 
    ```

2.  **避免大型结构的** **副本**:想象一个必须接收大型对象的功能。如果我们在没有引用的情况下传递它，就会创建一个新的副本，这会浪费 CPU 时间和内存。我们可以使用引用来避免这种情况。

    ## 卡片打印处理机(卡片打印处理器的缩写)

    ```cpp
    struct Student {
       string name;
       string address;
       int rollNo;
    }

    // If we remove & in below function, a new
    // copy of the student object is created. 
    // We use const to avoid accidental updates
    // in the function as the purpose of the function
    // is to print s only.
    void print(const Student &s)
    {
        cout << s.name << "  " << s.address << "  " << s.rollNo;
    }
    ```

3.  **在每个循环中修改所有对象**:我们可以在每个循环中使用引用来修改所有元素。

    ## 卡片打印处理机(卡片打印处理器的缩写)

    ```cpp
    #include <bits/stdc++.h> 
    using namespace std; 

    int main() 
    { 
        vector<int> vect{ 10, 20, 30, 40 }; 

        // We can modify elements if we 
        // use reference
        for (int &x : vect) 
            x = x + 5;

        // Printing elements
        for (int x : vect) 
           cout << x << " "; 

        return 0; 
    } 
    ```

4.  **对于每个循环避免对象的** **副本**:当对象很大时，我们可以在每个循环中使用引用来避免单个对象的副本。

    ## 卡片打印处理机(卡片打印处理器的缩写)

    ```cpp
    #include <bits/stdc++.h> 
    using namespace std; 

    int main() 
    { 
        vector<string> vect{"geeksforgeeks practice", 
                         "geeksforgeeks write",
                         "geeksforgeeks ide"}; 

        // We avoid copy of the whole string
        // object by using reference.
        for (const auto &x : vect) 
           cout << x << endl; 

        return 0; 
    }
    ```

**引用与指针:**

引用和指针都可以用来改变一个函数在另一个函数中的局部变量。当作为参数传递给函数或从函数返回时，这两种方法都可以用来节省大对象的复制，从而提高效率。尽管有上述相似之处，但引用和指针之间有以下区别。

1.指针可以被声明为无效，但是引用永远不能是无效的。例如

```cpp
int a = 10;
void* aa = &a;. //it is valid
void &ar = a; // it is not valid
```

2.指针变量具有 n 级/多级间接性，即单指针、双指针、三指针。然而，引用变量只有一个/单个间接层。以下代码揭示了上述要点:

3.无法更新引用变量。

4.引用变量是一个内部指针。

5.引用变量的声明前面带有“&”符号(但不要将其理解为“的地址”)。

## C++

```cpp
#include <iostream>
using namespace std;

int main() {
    int i=10; //simple or ordinary variable.
    int *p=&i; //single pointer
    int **pt=&p; //double pointer
    int ***ptr=&pt; //triple pointer
    // All the above pointers differ in the value they store or point to.
    cout << "i=" << i << "\t" << "p=" << p << "\t" 
         << "pt=" << pt << "\t" << "ptr=" << ptr << "\n";
    int a=5; //simple or ordinary variable 
    int &S=a; 
    int &S0=S;
    int &S1=S0;
    cout << "a=" << a << "\t" << "S=" << S << "\t" 
         << "S0=" << S0 << "\t" << "S1=" << S1 << "\n";
    // All the above references do not differ in their values 
    // as they all refer to the same variable.
 }
```

*   **引用不如指针**
    **1)** 一旦创建了引用，以后就不能再引用另一个对象；它不能被重置。这通常是通过指针来完成的。
    **2)** 引用不能为空。指针通常为空，表示它们没有指向任何有效的东西。
    **3)** 声明引用时必须进行初始化。指针没有这样的限制。
    由于上述限制，C++ 中的引用不能用于实现链表、树等数据结构。在 Java 中，引用没有上述限制，可以用来实现所有的数据结构。Java 中引用功能更强大是 Java 不需要指针的主要原因。

*   **引用更安全更容易使用:**
    ***1)更安全** :* 由于引用必须初始化，像[野指针](https://www.geeksforgeeks.org/what-are-wild-pointers-how-can-we-avoid/)这样的野引用不太可能存在。仍然有可能存在不引用有效位置的引用(参见下面练习中的问题 5 和 6)
    ***2)更容易使用:*** 引用不需要解引用运算符来访问值。它们可以像普通变量一样使用。&'仅在申报时需要操作员。此外，可以使用点运算符('.'来访问对象引用的成员)，与需要箭头运算符(- >)来访问成员的指针不同。

*   加上上述原因，很少有地方像复制构造函数参数一样不能使用指针。引用必须用于在复制构造函数中传递参数。同样，引用必须用于重载一些运算符，如++。

**练习:**
预测以下程序的输出。如果存在编译错误，请修复它们。
**问题 1**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include<iostream>
using namespace std;

int &fun()
{
    static int x = 10;
    return x;
}
int main()
{
    fun() = 30;
    cout << fun();
    return 0;
}
```

**问题 2**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include<iostream>
using namespace std;

int fun(int &x)
{
    return x;
}
int main()
{
    cout << fun(10);
    return 0;
}
```

**问题 3**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include<iostream>
using namespace std;

void swap(char * &str1, char * &str2)
{
  char *temp = str1;
  str1 = str2;
  str2 = temp;
}

int main()
{
  char *str1 = "GEEKS";
  char *str2 = "FOR GEEKS";
  swap(str1, str2);
  cout<<"str1 is "<<str1<<endl;
  cout<<"str2 is "<<str2<<endl;
  return 0;
}
```

**问题 4**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include<iostream>
using namespace std;

int main()
{
   int x = 10;
   int *ptr = &x;
   int &*ptr1 = ptr;
}
```

**问题 5**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include<iostream>
using namespace std;

int main()
{
   int *ptr = NULL;
   int &ref = *ptr;
   cout << ref;
}
```

**问题 6**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include<iostream>
using namespace std;

int &fun()
{
    int x = 10;
    return x;
}
int main()
{
    fun() = 30;
    cout << fun();
    return 0;
}
```

**相关文章:**

*   [c++ 中的指针与引用](https://www.geeksforgeeks.org/pointers-vs-references-cpp/)
*   [我们什么时候通过引用或者指针传递参数？](https://www.geeksforgeeks.org/when-do-we-pass-arguments-by-reference-or-pointer/)
*   [引用可以引用 C++ 中的无效位置吗？](https://www.geeksforgeeks.org/g-fact-25/)
*   [c++ 中通过指针传递与通过引用传递](https://www.geeksforgeeks.org/passing-by-pointer-vs-passing-by-reference-in-c/)

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论