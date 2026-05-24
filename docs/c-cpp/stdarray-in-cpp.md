# STD::c++ 中的数组

> 原文:[https://www.geeksforgeeks.org/stdarray-in-cpp/](https://www.geeksforgeeks.org/stdarray-in-cpp/)

数组是同类对象的集合，这个数组容器是为固定大小的数组或(静态大小)定义的。该容器环绕固定大小的数组，当声明为指针时，其大小信息不会丢失。
为了利用数组，我们需要包含数组头:

```cpp
 #include <array> 
```

我们来看一个例子。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate working of array
#include <algorithm>
#include <array>
#include <iostream>
#include <iterator>
#include <string>
using namespace std;

int main() {

  // construction uses aggregate initialization
  // double-braces required
  array<int, 5> ar1{{3, 4, 5, 1, 2}};
  array<int, 5> ar2 = {1, 2, 3, 4, 5};
  array<string, 2> ar3 = {{string("a"), "b"}};

  cout << "Sizes of arrays are" << endl;
  cout << ar1.size() << endl;
  cout << ar2.size() << endl;
  cout << ar3.size() << endl;

  cout << "\nInitial ar1 : ";
  for (auto i : ar1)
    cout << i << ' ';

  // container operations are supported
  sort(ar1.begin(), ar1.end());

  cout << "\nsorted ar1 : ";
  for (auto i : ar1)
    cout << i << ' ';

  // Filling ar2 with 10
  ar2.fill(10);

  cout << "\nFilled ar2 : ";
  for (auto i : ar2)
    cout << i << ' ';

  // ranged for loop is supported
  cout << "\nar3 : ";
  for (auto &s : ar3)
    cout << s << ' ';

  return 0;
}
```

**Output:** 

```cpp
Sizes of arrays are
5
5
2

Initial ar1 : 3 4 5 1 2 
sorted ar1 : 1 2 3 4 5 
Filled ar2 : 10 10 10 10 10 
ar3 : a b
```

这个 C++ STL 数组是一种顺序容器，在常规编程或竞争性编程中并不常用，但有时它的成员函数比我们日常生活中使用的常规正规数组提供了更高的优势。因此，我们正在讨论与这类数组一起使用的一些重要成员函数:

**<u>数组模板的成员函数如下</u> :**

> **<u>语法</u>:数组<对象 _ 类型，arr _ 大小>arr _ 名称；**

**a) [ ]运算符**:这与普通数组类似，我们用它来访问索引‘I’处的元素存储。

**Ex:**

## C++

```cpp
#include <iostream>
#include <array>
using namespace std;

int main() {
    array <char , 3> arr={'G','f','G'};
    cout<<arr[0] <<" "<<arr[2];
    return 0;
}
```

**Output**

```cpp
G G
```

**b) front()和 back()函数:**这些方法用于直接访问数组的第一个和最后一个元素。

## C++

```cpp
#include <iostream>
#include <array>
using namespace std;

int main() {
    array <int , 3> arr={'G','f','G'};  // ASCII val of 'G' =71 
    cout<<arr.front() <<" "<<arr.back();
    return 0;
}
```

**Output**

```cpp
71 71
```

**c) swap()函数:**此 swap 函数用于交换两个数组的内容。

例如:

## C++

```cpp
#include <iostream>
#include <array>
using namespace std;

int main() {
    array <int , 3> arr={'G','f','G'};  // ASCII val of 'G' =71 
    array <int , 3> arr1={'M','M','P'}; // ASCII val of 'M' = 77 and 'P' = 80
    arr.swap(arr1);  // now arr = {M,M,P}
    cout<<arr.front() <<" "<<arr.back();
    return 0;
}
```

**Output**

```cpp
77 80
```

**d) empty()函数:**该函数用于检查声明的 STL 数组是否为空，如果为空则返回 false 否则返回 true。

例如:

## C++

```cpp
#include <iostream>
#include <array>
using namespace std;

int main() {
    array <int , 3> arr={'G','f','G'};  // ASCII val of 'G' =71 
    array <int , 3> arr1={'M','M','P'}; // ASCII val of 'M' = 77 and 'P' = 80
    bool x = arr.empty(); // false ( not empty)
    cout<<boolalpha<<(x);
    return 0;
}
```

**Output**

```cpp
false
```

**e) at()函数:**这个函数用来访问存储在特定位置的元素，如果我们试图访问超出数组大小界限的元素，那么它会抛出一个异常。

例如:

## C++

```cpp
#include <iostream>
#include <array>
using namespace std;

int main() {
    array <int , 3> arr={'G','f','G'};  // ASCII val of 'G' =71 
    array <int , 3> arr1={'M','M','P'}; // ASCII val of 'M' = 77 and 'P' = 80
    cout<< arr.at(2) <<" " << arr1.at(2);
    //cout<< arr.at(3); // xception{Abort signal from abort(3) (SIGABRT)}
    return 0;
}
```

**Output**

```cpp
71 80
```

**f) fill()函数:**这是专门用来初始化或者用相似的值填充数组的所有索引。

例如:

## C++

```cpp
#include <iostream>
#include <array>
using namespace std;

int main() {
    array <int , 5> arr;
    arr.fill(1);
    for(int i: arr)
       cout<<arr[i]<<" ";
    return 0;
}
```

**Output**

```cpp
1 1 1 1 1 
```

**g) size()或 max_size()和 sizeof()函数:**size()或 max_size()都用于获取数组中最大的索引数，而 sizeof()用于获取数组的总大小(以字节为单位)。

## C++

```cpp
#include <iostream>
#include <array>
using namespace std;

int main() {
    array <int , 10> arr;    
    cout<<arr.size()<<'\n'; // toatal num of indexes
    cout<<arr.max_size()<<'\n'; // toatal num of indexes
    cout<<sizeof(arr); // toatal size of array
    return 0;
}
```

**Output**

```cpp
10
10
40
```

**h) <u>data( )</u> :** 这个函数返回指向数组对象第一个元素的指针。因为数组中的元素存储在连续的内存位置。这个 data()函数返回字符串/字符类型对象的基址。

**Ex:**

## C++

```cpp
#include <iostream>
#include <cstring>
#include <array>

using namespace std;

int main ()
{
  const char* str = "GeeksforGeeks";
  array<char,13> arr;
  memcpy (arr.data(),str,13);
  cout << arr.data() << '\n';
  return 0;
}
```

**Output**

```cpp
GeeksforGeeks
```

**I) c <u>begin()和 cend( )</u> :前往此 gfg 链接:** [**点击 _me**](https://www.geeksforgeeks.org/set-cbegin-and-cend-function-in-c-stl/)