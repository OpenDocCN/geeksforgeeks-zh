# std::gslice | Valarray 广义切片选择器

> 原文:[https://www . geesforgeks . org/stdgslice-valarray-generalized-slice-selector/](https://www.geeksforgeeks.org/stdgslice-valarray-generalized-slice-selector/)

**Valarray 广义切片选择器:**这个类表示 Valarray 广义切片选择器(一个多维切片)。它不包含也不引用任何元素——它只描述了要在 **valarray::operator[]** 中用作索引的元素的选择。

换句话说， **std::gslice** 是一个选择器类，用于识别由一组多级步幅和尺寸定义的 **std::valarray** 索引的子集。类型为 **std::gslice** 的对象可以用作 valarray 运算符[]的索引，以选择例如表示为 valarray 的多维数组的列。

给定起始值 s、步幅列表 i <sub>j</sub> 和尺寸列表 d <sub>j</sub> ，由这些值构建的标准:gslice 选择一组指数:

```cpp
k<sub>j</sub> = s + Σ<sub>j</sub>(i<sub>j</sub>d<sub>j</sub>)
```

valarray 广义切片由起始索引、一组大小和一组步长指定。它产生切片选择的多维组合。

**语法:**

```cpp
gslice( std::size_t start, const std::valarray& sizes,
                           const std::valarray& strides );
size_t start : index of the first element in the selection.
size_t (size) : number of elements in the selection.
size_t (stride) : span that separates the elements selected

```

*   In the given syntax, the default constructor is equivalent to gslice(0, std::valarray (), std::valarray ()). This constructor exists only to allow the construction of slice arrays.
*   Construct a new slice with parameters of start, size and stride.

**例 1:**

```cpp
start = 1 , size = {2, 3} , stride = {7, 2}
Input :  0 1 2 3 4 5 6 7 8 9 10 11 12 13
Output : 1 3 5 8 10 12
Explanation: 1 + 0*7 + 0*2 = 1,
             1 + 0*7 + 1*2 = 3,
             1 + 0*7 + 2*2 = 5,
             1 + 1*7 + 0*2 = 8,
             1 + 1*7 + 1*2 = 10,
             1 + 1*7 + 2*2 = 12

```

**例 2:**

```cpp
start = 3 , size = {2,4,3} , strides = {19,4,1}
Input : 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22
Output: 3 4 5 7 8 9 11 12 13 15 16 17 19 20 21 22
Explanation : 3 + 0*19 + 0*4 + 0*1 = 3,
              3 + 0*19 + 0*4 + 1*1 = 4,
              3 + 0*19 + 0*4 + 2*1 = 5,
              3 + 0*19 + 1*4 + 0*1 = 7,
              3 + 0*19 + 1*4 + 1*1 = 8,
              ...
              ...
              3 + 1*19 + 0*4 + 0*1 = 22 

```

**示例 1:c++ 程序中的 gslice 示例:**

```cpp
// C++ Program to test the 
// functioning of std::gslice
#include <iostream>     // std::cout
#include <cstddef>      // std::size_t
#include <valarray>     // std::valarray, std::gslice

int main ()
{
  //valarray sample of size 14
  std::valarray<int> sample (14);
  for (int i=0; i<14; ++ i) sample[i]=i;

  std::size_t start=1;
  std::size_t lengths[]= {2,3};
  std::size_t strides[]= {7,2};

  //gslice object which can be used directly
  std::gslice mygslice (start,
                        std::valarray<std::size_t>(lengths,2),
                        std::valarray<std::size_t>(strides,2));
  //creating data using gslice
  std::valarray<int> data = sample[mygslice];

 /* Can also be done in the following way 
 (without creating gslice object): 
 std::valarray<int> data=sample[std::gslice(start, 
                       std::valarray<std::size_t>(lengths,2),
                       std::valarray<std::size_t>(strides,2))];
  */  

  std::cout << "gslice:";

//displaying content of data 
  for (int i=0; i<data.size(); i++)
      std::cout << ' ' << data[i];
  std::cout << '\n';

  return 0;
}
```

输出:

```cpp
gslice: 1 3 5 8 10 12

```

**示例 2:演示如何使用 gslices 寻址三维数组的列并执行一些操作**

```cpp
//C++ Program to demonstrate use of 
// gslice to address columns of 3D array
#include <iostream> // std::cout
#include <valarray> // std::gslice
void test_print(std::valarray<int>& v, int rows, int cols, int planes)
{
    for(int r=0; r<rows; ++ r) {
        for(int c=0; c<cols; ++ c) {
            for(int z=0; z<planes; ++ z)
                std::cout << v[r*cols*planes + c*planes + z] << ' ';
            std::cout << '\n';
        }
        std::cout << '\n';
    }
}
int main()
{
    // 3d array: 2 x 4 x 3 elements
    std::valarray<int> v = 
    { 111,112,113 , 121,122,123 , 131,132,133 , 141,142,143,
     211,212,213 , 221,222,223 , 231,232,233 , 241,242,243};

 // int ar3D [2][4][3]
    std::cout << "Initial 2x4x3 array:\n";
    test_print(v, 2, 4, 3);

    // update every value in the first columns of both planes
    // two level one strides of 12 elements
    // then four level two strides of 3 elements
    v[std::gslice(0, {2, 4}, {4*3, 3})] = 1; 

    // subtract the third column from the 
    // second column in the 1st plane
    v[std::gslice(1, {1, 4}, {4*3, 3})] 
        -= v[std::gslice(2, {1, 4}, {4*3, 3})];

    std::cout << "After column operations: \n";
    test_print(v, 2, 4, 3);
}
```

输出:

```cpp
Initial 2x4x3 array:
111 112 113 
121 122 123 
131 132 133 
141 142 143 

211 212 213 
221 222 223 
231 232 233 
241 242 243 

After column operations: 
1 -1 113 
1 -1 123 
1 -1 133 
1 -1 143 

1 212 213 
1 222 223 
1 232 233 
1 242 243 

```

本文由 [**舒巴姆拉纳**](https://auth.geeksforgeeks.org/profile.php?user=shubham_rana_77&list=practice) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。