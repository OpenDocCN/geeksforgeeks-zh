# 在 C++ 中迭代集合的不同方式

> 原文:[https://www . geeksforgeeks . org/不同的迭代方式-在 c 集中迭代/](https://www.geeksforgeeks.org/different-ways-to-iterate-over-a-set-in-c/)

[集合](https://www.geeksforgeeks.org/set-in-cpp-stl/)是一种关联的[容器](https://www.geeksforgeeks.org/containers-cpp-stl/)，其中每个元素必须是唯一的，因为元素的值标识了它。这些值以特定的顺序存储。

**语法:**

> **设置 < 数据类型 > 设置名;**
> 
> 这里，
> **数据类型:**集合可以根据值采用任何数据类型，例如 int、char、float 等。

本文重点讨论在 [C++ ](http://www.geeksforgeeks.org/c-plus-plus/) 中可以用来迭代集合的所有方法。本文将讨论以下方法:

1.  **使用** [**迭代器**](https://www.geeksforgeeks.org/iterators-c-stl/) **迭代一个集合。**
2.  **使用** [**反向迭代程序**](https://www.geeksforgeeks.org/vector-rbegin-and-rend-function-in-c-stl/) **反向迭代一个集合。**
3.  **使用** [**基于范围的 for 循环**](https://www.geeksforgeeks.org/range-based-loop-c/) **迭代一个集合。**
4.  **对每个循环使用** [**迭代一个集合**](https://www.geeksforgeeks.org/for_each-loop-c/) **。**

让我们开始详细讨论这些方法。

**<u>使用迭代器对集合进行迭代。</u>T3】**

在这种方法中，使用 **begin()** 函数创建并初始化迭代器 **itr** ，该函数将指向第一个元素，并且在每次迭代之后，itr 指向集合中的下一个元素，并且它将继续迭代，直到到达集合的末尾。
本办法将采用以下方法:

1.  [**begin()**](https://www.geeksforgeeks.org/setbegin-setend-c-stl/) **:返回集合中第一个元素的迭代器。**
2.  [**【end()**](https://www.geeksforgeeks.org/setbegin-setend-c-stl/)**:**返回集合中最后一个元素之后的理论元素的迭代器。

下面是实现上述方法的 C++ 程序:

## C++

```cpp
// C++ program to implement 
// the above approach
#include<bits/stdc++.h>
using namespace std;

// Function to display elements 
// of a set
void display(set<int> s)
{
  set<int>::iterator itr;

  // Displaying set elements
  for (itr = s.begin(); 
       itr != s.end(); itr++) 
  {
    cout << *itr << " ";
  }
}  

// Driver code
int main()
{
  // Empty set container
  set<int> s;

  // Insert elements in random order
  s.insert(10);
  s.insert(20);
  s.insert(30);
  s.insert(40);
  s.insert(50);

  // Invoking function display()
  // to display elements of set
  display(s);
  return 0;
}
```

**输出:**

> 10 20 30 40 50

**<u>使用逆向迭代器</u>** 向后迭代一个集合

在这种方法中，使用 **rbegin()** 函数创建并初始化 **reverse_iterator itr** ，该函数将指向集合中的最后一个元素，并且在每次迭代之后，itr 指向集合中向后方向的下一个元素，并且它将继续迭代，直到到达集合的开头。
本方法使用以下功能:

1.  **set::rbegin():** 它是 C++ STL 中的内置函数，返回指向容器中最后一个元素的反向迭代器。
2.  **set::rend():** 它是 C++ STL 中的一个内置函数，返回一个反向迭代器，指向 set 容器中第一个元素之前的理论元素。

下面是实现上述方法的 C++ 程序:

## C++

```cpp
// C++ program to implement 
// the above approach
#include<bits/stdc++.h>
using namespace std;

// Function to display elements 
// of the set
void display(set<int> s)
{
  set<int>::reverse_iterator itr;

  // Displaying elements of the 
  // set
  for (itr = s.rbegin(); 
       itr != s.rend(); itr++) 
  {
    cout << *itr << " ";
  }
}

// Driver code
int main()
{
  // Empty set container
  set<int> s;

  // Insert elements in random order
  s.insert(10);
  s.insert(20);
  s.insert(30);
  s.insert(40);
  s.insert(50);

  // Invoking display() function
  display(s);
  return 0;
}
```

**输出:**

> 50 40 30 20 10

**<u>使用基于范围的 for 循环迭代一个集合</u>**

在此方法中，基于范围的 for 循环将用于向前迭代集合中的所有元素。

**语法:**

> **为(range _ declaration:range _ expression)**
> 
> **loop_statement**
> 
> **参数:**
> 
> **range_declaration :**
> 一个命名变量的声明，其类型是 range_expression 表示的序列元素的类型，或者是对该类型的引用。通常使用自动说明符进行自动类型推导。
> 
> **range_expression:**
> 表示合适序列或支撑初始化列表的任何表达式。
> 
> **loop_statement:**
> 任何语句，通常是复合语句，它是循环的主体。

下面是实现上述方法的 C++ 程序:

## C++

```cpp
// C++ program to implement
// the above approach
#include<bits/stdc++.h>
using namespace std;

// Function to display elements
// of the set
void display(set<int> s)
{
  // Printing the elements of 
  // the set
  for (auto itr : s) 
  {
    cout << itr << " ";
  }  
}
// Driver code
int main()
{
  // Empty set container
  set<int> s;

  // Insert elements in random order
  s.insert(10);
  s.insert(20);
  s.insert(30);
  s.insert(40);
  s.insert(50);

  // Invoking display() function
  display(s);
  return 0;
}
```

**输出:**

> 10 20 30 40 50

**<u>使用 for _ 每个循环</u>** 迭代一个集合

在这种方法中，for_each 循环接受一个在每个容器元素上执行的函数。

**语法:**

> **对于每一个(输入生成器开始 _iter，输入生成器最后 _iter，函数 fnc)**
> 
> **start_iter:** 必须执行功能操作的起始位置。
> 
> **last_iter:** 必须执行功能的结束位置。
> 
> **fnc/obj_fnc:** 第三个参数是一个函数或对象函数，该操作将应用于每个元素。

下面是实现上述方法的 C++ 程序:

## C++

```cpp
// C++ program to implement
// the above approach
#include<bits/stdc++.h>
using namespace std;

void print(int x)
{
  cout << x << " ";
}

// Function to display the 
// elements of set
void display(set<int> s)
{
  for_each(s.begin(), s.end(), 
           print);
}

// Driver code
  int main()
{
  // Empty set container
  set<int> s;

  // Insert elements in random order
  s.insert(10);
  s.insert(20);
  s.insert(30);
  s.insert(40);
  s.insert(50);

  // Invoking display() function
  display(s);
  return 0;
}
```

**输出:**

> 10 20 30 40 50