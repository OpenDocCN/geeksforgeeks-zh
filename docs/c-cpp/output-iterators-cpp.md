# c++ 中的输出迭代器

> 原文:[https://www.geeksforgeeks.org/output-iterators-cpp/](https://www.geeksforgeeks.org/output-iterators-cpp/)

浏览了**[【STD::copy】](https://www.geeksforgeeks.org/different-methods-copy-c-stl-stdcopy-copy_n-copy_if-copy_backwards/)****[【STD::move】](https://www.geeksforgeeks.org/stdmove-in-c/)****[【STD::transform】](https://www.geeksforgeeks.org/transform-c-stl-perform-operation-elements/)**等各种 STL 算法的模板定义后，你一定找到了它们的模板定义，由**输出迭代器**类型的对象组成。那么它们是什么，为什么被使用？

**输出迭代器**是 C++ 标准库中存在的五种主要迭代器类型之一，其他的还有 **[输入迭代器](https://www.geeksforgeeks.org/input-iterators-in-cpp/)****[正向迭代器](https://www.geeksforgeeks.org/forward-iterators-in-cpp/)****[双向迭代器](https://www.geeksforgeeks.org/bidirectional-iterators-in-cpp/)** 和 **[随机访问迭代器](https://www.geeksforgeeks.org/random-access-iterators-in-cpp/)** 。

输出迭代器被认为是与输入迭代器完全相反的**，因为它们执行与输入迭代器相反的功能。它们可以是序列中的**赋值，但不能用于访问值，不像输入迭代器那样做相反的访问值，不能赋值。所以，我们可以说**输入和输出迭代器是相互补充的**。****

**![](img/4ee94c1e4b4b22bb10c8ac1fb40cf559.png)**

**需要记住的一点是**转发**、**双向**和**随机访问**迭代器也是有效的输出迭代器，如上面的迭代器层次所示。**

****显著特征****

1.  ****可用性:**就像输入迭代器一样，输出迭代器只能和**单程算法**一起使用，也就是我们最多可以去一次范围内所有位置的算法，这样这些位置只能被解引用或赋值一次。**
2.  ****Equality / Inequality Comparison:** Unlike input iterators, output iterators cannot be compared for equality with another iterator.

    因此，如果 A 和 B 是输出迭代器，下面两个表达式是无效的:

    ```cpp
    A == B  // Invalid - Checking for equality
    A != B  // Invalid - Checking for inequality

    ```** 
3.  ****Dereferencing:** An input iterator can be dereferenced as an rvalue, using operator * and ->, whereas an **output iterator can be dereferenced as an lvalue** to provide the location to store the value.

    因此，如果 A 是输出迭代器，下面两个表达式是有效的:

    ```cpp
    *A = 1      // Dereferencing using *
    A -> m = 7   // Assigning a member element m

    ```** 
4.  ****Incrementable:** An output iterator can be incremented, so that it refers to the next element in sequence, using operator ++().

    因此，如果 A 是输出迭代器，下面两个表达式是有效的:

    ```cpp
    A++   // Using post increment operator
    ++ A   // Using pre increment operator

    ```** 
5.  ****可交换:**这些迭代器指向的值可以交换或互换。**

****实际执行****

**在了解了它的特点和不足之后，了解它的实际实现也是非常重要的。如前所述，输出迭代器仅在我们想要分配元素时使用，而不是在我们必须访问元素时使用。以下两个 STL 算法可以说明这一事实:**

*   ****std::move:** As the name suggests, this algorithm is used to move elements in a range into another range. Now, as far as accessing elements are concerned, input iterators are fine, **but as soon as we have to assign elements in another container, then we cannot use these input iterators** for this purpose, that is why here using output iterators becomes a compulsion.

    ```cpp
    // Definition of std::move()
    template 
    OutputIterator move (InputIterator first, InputIterator last,
                         OutputIterator result)
    {
        while (first!=last)
        {
            *result = std::move(*first);
            ++ result;
            ++ first;
        }
        return result;
    }

    ```

    在这里，因为结果是结果容器的迭代器，元素被分配给这个容器，所以对于这个，我们不能使用输入迭代器，并且已经在它们的位置使用了输出迭代器，而对于访问元素，使用只需要增加和访问的输入迭代器。** 
*   ****std::find:** As we know this algorithm is used to find the presence of an element inside a container and doesn’t involve the use of output iterators.

    ```cpp
    // Definition of std::find()
    template 
    InputIterator find (InputIterator first, InputIterator last, 
                        const T& val)
    {
        while (first!=last) 
        {
            if (*first==val) return first;
            ++ first;
        }
        return last;
    }

    ```

    因此，从这里开始，不需要给迭代器赋值，只需要访问和比较迭代器，所以不需要输出迭代器，因此只使用输入迭代器。** 

**因此，上面的两个例子很好地展示了输出迭代器在何时、何地、为什么以及如何被实际使用。**

****限制****

**在研究了显著的特性之后，我们还必须知道输出迭代器的不足，这在以下几点中提到:**

1.  ****Only assigning, no accessing:** One of the biggest deficiency is that **we cannot access the output iterators as rvalue.** So, an output iterator can only modify the element to which it points by being used as the target for an assignment.

    ```cpp
    // C++ program to demonstrate output iterator
    #include<iostream>
    #include<vector>
    using namespace std;
    int main()
    {
        vector<int>v1 = {1, 2, 3, 4, 5};

        // Declaring an iterator
        vector<int>::iterator i1;

        for (i1=v1.begin();i1!=v1.end();++ i1)
        {
            // Assigning elements using iterator
            *i1 = 1;
        }
        // v1 becomes 1 1 1 1 1
        return 0;
    }
    ```

    上面是一个使用输出迭代器分配元素的例子，但是，如果我们做一些类似的事情:

    ```cpp
    a = *i1 ; // where a is a variable

    ```

    因此，这对于输出迭代器是不允许的，因为它们只能是赋值中的目标。但是，如果您对上面的代码尝试这样做，它会起作用，因为向量返回的迭代器在层次结构中比输出迭代器更高。

    这个很大的不足就是为什么像 [std::find](http://contribute.geeksforgeeks.org/stdfind-in-c/) 这样要求访问一个范围内的元素并检查是否相等的很多算法不能使用输出迭代器来进行访问的原因，因为我们不能使用它来访问值，所以我们改为使用输入迭代器。** 
2.  ****不能递减:**就像我们可以使用带有输出迭代器的运算符++()来递增一样，我们不能递减它们。

    ```cpp
    If A is an output iterator,then

    A--    // Not allowed with output iterators

    ```** 
3.  ****用在多遍算法中:**由于，它是单向的，只能向前移动，因此，这样的迭代器不能用在多遍算法中，在多遍算法中，我们需要在容器中移动多次。**
4.  ****关系运算符:**就像输出迭代器不能用于等式运算符(==)一样，它也不能用于其他关系运算符，如=。

    ```cpp
    If A and B are output iterators, then

    A == B     // Not Allowed
    A <= B     // Not Allowed

    ```** 
5.  ****算术运算符:**与关系运算符类似，它们也不能用于+、–等算术运算符。这意味着输出操作符只能朝一个方向移动，这个方向太向前，那个方向太向后。

    ```cpp
    If A and B are output iterators, then

    A + 1     // Not allowed
    B - 2     // Not allowed

    ```** 

**本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。**

**如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写下您的评论。**