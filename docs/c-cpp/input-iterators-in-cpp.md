# c++ 中的输入迭代器

> 原文:[https://www.geeksforgeeks.org/input-iterators-in-cpp/](https://www.geeksforgeeks.org/input-iterators-in-cpp/)

浏览了 [**std::find**](https://www.geeksforgeeks.org/stdfind-in-c/) 、[T5】STD::equal](https://www.geeksforgeeks.org/stdequal-in-cpp/)、 [**std::count**](https://www.geeksforgeeks.org/std-count-cpp-stl/) 等各种 STL 算法的模板定义后，您一定找到了它们的模板定义，该模板定义由类型为**的对象组成输入迭代器**。那么它们是什么，为什么被使用？
**输入迭代器**是 C++ 标准库中存在的五种主要迭代器类型之一，其他的还有 [**输出迭代器**](https://www.geeksforgeeks.org/output-iterators-c/)[**正向迭代器**](https://www.geeksforgeeks.org/forward-iterators-in-cpp/)[**双向迭代器**](https://www.geeksforgeeks.org/bidirectional-iterators-in-cpp/)**和 [**随机访问迭代器**](https://www.geeksforgeeks.org/random-access-iterators-in-cpp/) 。
输入迭代器被认为是所有可用迭代器中最弱的**和最简单的**，这是基于它们的功能和使用它们可以实现的目标。它们是可以在顺序输入操作中使用的迭代器，其中迭代器指向的每个值只读一次，然后迭代器递增。****** 

******![](img/4ee94c1e4b4b22bb10c8ac1fb40cf559.png)******

******需要记住的一点是**转发**、**双向**和**随机访问**迭代器也是有效的输入迭代器，如上面的迭代器层次所示。****** 

******显著特征****** 

1.  ******可用性:**输入迭代器只能和**单程算法**一起使用，也就是我们最多可以去一次范围内所有位置的算法，就像当我们必须搜索或找到范围内的任何元素时，我们最多去一次位置。**** 
2.  ******等式/不等式比较:**一个输入迭代器可以与另一个迭代器进行等式比较。因为迭代器指向某个位置，所以两个迭代器只有指向同一个位置时才相等，否则不相等。
    所以，如果 A 和 B 是输入迭代器，以下两个表达式是有效的:**** 

```cpp
**A == B  // Checking for equality
A != B  // Checking for inequality** 
```

****3。**取消引用:**可以取消对输入迭代器的引用，使用运算符*和- >作为右值，以获取存储在迭代器所指向位置的值。
所以，如果 A 是输入迭代器，下面两个表达式是有效的:****

```cpp
***A       // Dereferencing using *
A -> m   // Accessing a member element m** 
```

****4。**递增:**输入迭代器可以递增，这样它就可以引用序列中的下一个元素，使用运算符++()。****

******注意:**我们可以使用带有增量运算符的输入迭代器，这并不意味着运算符–-()也可以与它们一起使用。请记住，输入迭代器是单向的，只能向前移动。
所以，如果 A 是输入迭代器，下面两个表达式是有效的:****

```cpp
**A++   // Using post increment operator
++ A   // Using pre increment operator** 
```

******可交换:**这些迭代器指向的值可以交换或互换。****

******实际实现**
了解了它的特点和不足之后，了解它的实际实现也是非常重要的。如前所述，输入迭代器只在我们想要访问元素时使用，而不是在我们必须给元素赋值时使用。以下两个 STL 算法可以说明这一事实:****

*   ******std::find:** 正如我们所知，该算法用于查找容器内部元素的存在。所以，让我们看看它的内部工作方式(不要深入细节，只看哪里可以使用输入迭代器，哪里不可以):****

## ****卡片打印处理机（Card Print Processor 的缩写）****

```cpp
**// Definition of std::find() template 

InputIterator find (InputIterator first, InputIterator last, 
                    const T& val)
{
    while (first!=last) 
    {
        if (*first==val) return first;
        ++ first;
    }
    return last;
}**
```

*   ****所以，这是输入迭代器的实际实现，**单程算法，其中只有我们必须按顺序移动并访问元素，并检查与另一个元素的相等性**，就像上面使用的第一个一样，所以在这里可以使用它们。更多这样的算法是 **std::equal** 、 **std::equal_range** 和 **std::count。****** 
*   ******std::copy:** 顾名思义，这个算法是用来将一个范围复制到另一个范围。现在，就访问元素而言，输入迭代器是可以的，**但是一旦我们必须在另一个容器中分配元素，那么我们就不能为此目的使用这些输入迭代器**。****

## ****卡片打印处理机（Card Print Processor 的缩写）****

```cpp
**// Definition of std::copy() template 
OutputIterator copy(InputIterator first, InputIterator last,
                    OutputIterator result) 
{
    while (first != last) 
    *result++ = *first++ ;
    return result;
}**
```

*   ****在这里，因为结果是结果容器的迭代器，元素被分配给这个容器，所以对于这个，我们不能使用输入迭代器，而是在它们的位置使用输出迭代器，而对于第一个，它只需要增加和访问，我们使用了输入迭代器。****

******局限性**
在研究了显著特征之后，还必须知道它的不足之处，这些不足之处使它成为所有迭代器中最弱的一个，这在以下几点中提到:****

1.  ******只访问，不赋值:**最大的不足之一是**我们不能给这个迭代器指向的位置赋值**，它只能用来访问元素，不能赋值元素。****

## ****卡片打印处理机（Card Print Processor 的缩写）****

```cpp
**// C++ program to demonstrate input iterator
#include <iostream>
#include <vector>
using namespace std;
int main()
{
    vector<int> v1 = { 1, 2, 3, 4, 5 };

    // Declaring an iterator
    vector<int>::iterator i1;

    for (i1 = v1.begin(); i1 != v1.end(); ++ i1) {
        // Accessing elements using iterator
        cout << (*i1) << " ";
    }
    return 0;
}**
```

******输出:******

```cpp
**1 2 3 4 5** 
```

****上面是一个使用输入迭代器访问元素的例子，但是，如果我们做一些类似的事情:****

```cpp
***i1 = 7;** 
```

*   ****所以，这在输入迭代器中是不允许的。但是，如果您对上面的代码尝试这样做，它将会工作，因为向量返回的迭代器在层次结构中比输入迭代器更高。
    这个很大的缺陷就是像 [std::copy](http://contribute.geeksforgeeks.org/different-methods-to-copy-in-c-stl-stdcopy-copy_n-copy_if-copy_backwards/) 这样的许多算法需要将一个范围复制到另一个容器中的原因**不能**对结果容器使用输入迭代器，因为我们不能用这样的迭代器给它赋值，而是使用输出迭代器。**** 
*   ******不能递减:**就像我们可以使用带有输入迭代器的运算符++()来递增一样，我们不能递减它们。****

```cpp
**If A is an input iterator, then

A--    // Not allowed with input iterators** 
```

*   ******在多遍算法中使用:**由于它是单向的，只能向前移动，因此，这样的迭代器不能用在多遍算法中，在多遍算法中，我们需要多次处理容器。**** 
*   ******关系运算符:**虽然，输入迭代器可以与等式运算符(==)一起使用，但它不能与其他关系运算符一起使用，如< =。****

```cpp
**If A and B are input iterators, then

A == B     // Allowed
A <= B     // Not Allowed** 
```

*   ******算术运算符:**和关系运算符类似，也不能和+、–等算术运算符一起使用。这意味着输入操作符只能朝一个方向移动，这个方向太向前，那个方向太向后。****

```cpp
**If A and B are input iterators, then

A + 1     // Not allowed
B - 2     // Not allowed** 
```

****因此，上面的两个例子很好地展示了输入迭代器在何时、何地、为什么以及如何被实际使用。
本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。****