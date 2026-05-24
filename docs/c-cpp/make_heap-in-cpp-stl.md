# c++ STL 中的 make_heap()

> 原文:[https://www.geeksforgeeks.org/make_heap-in-cpp-stl/](https://www.geeksforgeeks.org/make_heap-in-cpp-stl/)

make_heap()用于将序列转换为堆。堆是一种数据结构，其中**指向最高的**(或最低的)元素，并在**0(1)**时间进行访问。所有其他元素的顺序取决于特定的实现，但始终保持一致。该功能在表头**算法**中定义。make_heap()函数有两种实现。这两者都通过本文进行了解释。

**语法 1 : make_heap(iter_first，iter_last)**

> **模板:**
> **虚空 make _ heap(randomaccessetrator 第一，randomaccessetrator 最后)；**
> **参数:**
> **第一个**:必须将
> 转换为堆的序列起始元素的指针。
> **最后一个**:指向序列最后一个元素的下一个地址的指针
> 必须转换为堆。

下面是演示代码:

```cpp
// C++ code to demonstrate the working of 
// make_heap() using syntax 1

#include<iostream>
#include<algorithm> // for heap 
#include<vector>
using namespace std;

int main()
{
    // initializing vector;
    vector<int> vi = { 4, 6, 7, 9, 11, 4 };

    // using make_heap() to transform vector into
    // a max heap
    make_heap(vi.begin(),vi.end());

    //checking if heap using 
    // front() function
    cout << "The maximum element of heap is : ";
    cout << vi.front() << endl;

}
```

输出:

```cpp
The maximum element of heap is : 11

```

**语法 2 : make_heap(iter_first，iter_last，comp)**

> **模板:**
> **虚空 make _ heap(randomaccessetrator 第一，randomaccessetrator 最后，comp)；**
> **参数:**
> **第一个**:指向必须转换为堆的序列起始元素的指针。
> **last** :指向序列中最后一个必须转换为堆的元素的下一个地址的指针。
> **comp :** 比较器函数，返回所比较的每个元素的布尔真/假。这个函数接受两个参数。这可以是函数指针或函数对象，不能更改值。

下面是演示代码:

```cpp
// C++ code to demonstrate the working of 
// make_heap() using syntax 2 

#include<iostream> 
#include<algorithm> // for heap 
#include<vector> 
using namespace std; 

// comparator function to make min heap 
struct greaters{ 
bool operator()(const long& a,const long& b) const{ 
    return a>b; 
} 
}; 

int main() 
{ 
    // initializing vector; 
    vector<int> vi = { 15, 6, 7, 9, 11, 45 }; 

    // using make_heap() to transform vector into 
    // a min heap 
    make_heap(vi.begin(),vi.end(), greaters()); 

    // checking if heap using 
    // front() function 
    cout << "The minimum element of heap is : "; 
    cout << vi.front() << endl; 

} 
```

输出:

```cpp
The minimum element of heap is : 6

```

**可能的应用:**该功能可用于调度。在调度中，在迭代中动态插入新元素。一次又一次地排序以获得最大值需要非常复杂的 O(nlogn)，相反，我们使用“push_heap()”函数来堆积 O(logn)时间内产生的堆。下面的代码描述了它的实现。

```cpp
// C++ code to demonstrate  
// application of make_heap() (max_heap)
// priority scheduling

#include<iostream>
#include<algorithm> // for heap 
#include<vector>
using namespace std;

int main()
{
    // initializing vector;
    // initial job priorities
    vector<int> vi = { 15, 6, 7, 9, 11, 19};

    // No. of incoming jobs.
    int k = 3;

    // using make_heap() to transform vector into
    // a min heap
    make_heap(vi.begin(),vi.end());

    // initializing job variable
    int a = 10;

    for ( int i=0; i<k; i++)
    {

    // push a job with priority level
    vi.push_back(a); 

    // transform into heap ( using push_heap() )
    push_heap(vi.begin(), vi.end());

    //checking top priority job
    // front() function
    cout << "Job with maximum priority is : ";
    cout << vi.front() << endl;

    // increasing job priority level
    a = a + 10;

    }

}
```

输出:

```cpp
Job with maximum priority is : 19
Job with maximum priority is : 20
Job with maximum priority is : 30

```

本文由 **[【曼吉特·辛格】](https://www.facebook.com/manjeet.04.singh)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。