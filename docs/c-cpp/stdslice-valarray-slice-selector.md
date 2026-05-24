# 标准::切片(Valarray 切片选择器)

> 原文:[https://www . geesforgeks . org/stdslice-valarray-slice-selector/](https://www.geeksforgeeks.org/stdslice-valarray-slice-selector/)

**Valarray 切片选择器:**这个类代表一个 Valarray 切片选择器。它不包含也不引用任何元素——它只描述了要在 **valarray::operator[]** 中用作索引的元素的选择。

std::slice 是标识 std::valarray 子集的选择器类。std::slice 类型的对象包含三个值:起始索引、跨距和子集中值的总数。std::slice 类型的对象可以用 valarray 的运算符[]作为索引。

```cpp
class slice;

```

简单来说，它用于根据索引进行切片。valarray 切片由起始索引、大小和步幅定义。
**语法:**

```cpp
slice( std::size_t start, std::size_t size, std::size_t stride );
size_t star : is the index of the first element in the selection
size_t size : is the number of elements in the selection
stride : is the span that separates the elements selected.
```

*   在给定的语法中，默认构造函数等同于切片(0，0，0)。此构造函数的存在只是为了允许构造切片数组。
*   它用参数开始、大小、步幅构建一个新的切片。该切片将参考元素的大小编号，每个元素的位置为:

    ```cpp
    start + 0*stride
    start + 1*stride
    ....
    ....
    start + (size-1)*stride

    ```

**示例:**

```cpp
slice(1, 5, 4)
Input :  0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
Output : 1 5 9 13 17 
Explanation : starting from index 1 then next index 1 + 1 * 4 = 5, next index 1 + 2 * 4 = 9, 
              next index 1 + 3 * 4 = 13, next index 1 + 4 * 4 = 17.

```

因此，步长大于 1 的切片不会选择 valarray 中的连续元素。例如，切片(3，4，5)选择元素 3，8，13 和 18。

```cpp
// C++ program to test the functioning of std::slice
#include <iostream> // std::cout
#include <cstddef> // std::size_t
#include <valarray> // std::valarray, std::slice

int main()
{
    std::valarray<int> sample(12);
    // initialising valarray
    for (int i = 0; i < 13; ++ i)
        sample[i] = i;

    // using slice from start 1 and size 3 and stride 4
    std::valarray<int> bar = sample[std::slice(2, 3, 4)];

    // display slice result
    std::cout << "slice(2, 3, 4):";
    for (std::size_t n = 0; n < bar.size(); n++)
        std::cout << ' ' << bar[n];
    std::cout << '\n';

    return 0;
}
```

输出:

```cpp
slice(2, 3, 4): 2 6 10

```

**应用:**切片的一个简单应用就是求矩阵的迹。

```cpp
// C++ program to find trace of a matrix by using std::slice
#include <iostream> // std::cout
#include <valarray> // std::valarray, std::slice

using namespace std;

int main()
{
    // row and column of matrix
    int row = 3, col = 3;

    // matrix of size row*col in row major form.
    std::valarray<int> matrix(row * col);

    // initialising matrix
    for (int i = 0; i < row * col; ++ i)
        matrix[i] = i + 1;

    // using slice from start 0 with size as col and stride col+1
    std::valarray<int> diagonal = matrix[std::slice(0, col, col + 1)];

    // finding trace using diagonal we got using slice
    int index = 0;
    for (int i = 0; i < row; i++) {
        for (int j = 0; j < col; j++)
            std::cout << matrix[index++ ] << " "; // same as matrix[i][j]
        std::cout << endl;
    }

    int sum = 0; // initialising sum as 0
    // calculating trace of matrix
    for (int i = 0; i < diagonal.size(); i++)
        sum += diagonal[i];
    std::cout << "Trace of matrix is : ";
    std::cout << sum << endl; // sum is trace of matrix
    return 0;
}
```

输出:

```cpp
1 2 3 
4 5 6 
7 8 9 
Trace of matrix is : 15

```

本文由**舒巴姆拉纳**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。