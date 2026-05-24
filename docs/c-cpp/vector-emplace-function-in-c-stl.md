# c++ STL 中的向量侵位()函数

> 原文:[https://www . geesforgeks . org/vector-侵位-function-in-c-stl/](https://www.geeksforgeeks.org/vector-emplace-function-in-c-stl/)

**向量::侵位()**是 C++ 中的一个 STL，它通过在该位置插入一个新元素来扩展容器。只有当需要更多空间时，才会发生重新分配。这里的容器尺寸增加了一个。
**语法:**

```cpp
template 
iterator vector_name.emplace (const_iterator position, element);
```

**参数:**
该功能接受两个强制参数，具体如下:

*   *位置*–它指定迭代器指向容器中要插入新元素的位置。

*   元素-它指定要插入到向量容器中的元素。

**返回值:**函数返回一个迭代器，指向新插入的元素。

**复杂度:**线性
下面的程序说明了上面的功能:
**程序 1:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// vector::emplace() function
// insertion at thefront
#include <bits/stdc++.h>
using namespace std;

int main()
{
    vector<int> vec = { 10, 20, 30 };

    // insert element by emplace function
    // at front
    auto it = vec.emplace(vec.begin(), 15);

    // print the elements of the vector
cout << "The vector elements are: ";
    for (auto it = vec.begin(); it != vec.end(); ++ it)
        cout << *it << " ";

    return 0;
}
```

**Output:** 

```cpp
The vector elements are: 15 10 20 30
```

**节目 2:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// vector::emplace() function
// insertion at the end
#include <bits/stdc++.h>
using namespace std;

int main()
{
    vector<int> vec = { 10, 20, 30 };

    // insert element by emplace function
    // at the end
    auto it = vec.emplace(vec.end(), 16);

    // print the elements of the vector
cout << "The vector elements are: ";
    for (auto it = vec.begin(); it != vec.end(); ++ it)
        cout << *it << " ";

    return 0;
}
```

**Output:** 

```cpp
The vector elements are: 10 20 30 16
```

**节目 3:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// vector::emplace() function
// insertion at the middle
#include <bits/stdc++.h>
using namespace std;

int main()
{
    vector<int> vec = { 10, 20, 30 };

    // insert element by emplace function
    // in the middle
    auto it = vec.emplace(vec.begin() + 2, 16);

    // print the elements of the vector
cout << "The vector elements are: ";
    for (auto it = vec.begin(); it != vec.end(); ++ it)
        cout << *it << " ";

    return 0;
}
```

**Output:** 

```cpp
The vector elements are: 10 20 16 30
```

**其他相关链接:** [**炮台 _ 正面()**](https://www.geeksforgeeks.org/listemplace_front-listemplace_back-c-stl/) **和** [**炮台 _ 背面()**](https://www.geeksforgeeks.org/listemplace_front-listemplace_back-c-stl/)

**<u>在阵列中使用移位操作定期插入 V/s 炮台( )功能</u> :**

**a)** 如果要在第一个和最后一个索引之间的某个特定位置插入一个元素，我们必须移动该特定索引旁边的所有元素。所以，如果想要保持我们的代码精确，那么**炮位()**将是一个不错的选择。就**时间复杂度而言**两者取**相同的线性时间**，这直接取决于换挡操作的次数。

**Ex:**

## C++

```cpp
#include <iostream>
#include <vector>
#include <array>
using namespace std;

int main() {
    array<int,6> a={1,2,4,5};
    vector<int>  v={1,2,4,5};

    // Insert 3 in the arr at index 2

    for(int i=3;i>=0;i--)
    {
      if(i!=1)
        a[i+1]=a[i];
      else {       
        a[i+1]=3; break;
        }
    }   // Time complexity is high

    cout<<"Content of a: ";
    for(int i=0;i<5;i++)
       cout<<a[i]<<" ";

    v.emplace( v.begin() + 2 , 3);

    cout<<"\nContent of v: ";         
    for(int i=0;i<v.size();i++)
       cout<<v[i]<<" ";

    return 0;
}
```

**Output**

```cpp
Content of a: 1 2 3 4 5 
Content of v: 1 2 3 4 5 
```