# c++ 中的前向迭代器

> 原文:[https://www.geeksforgeeks.org/forward-iterators-in-cpp/](https://www.geeksforgeeks.org/forward-iterators-in-cpp/)

浏览了 [std::search](https://www.geeksforgeeks.org/stdsearch-in-c/) 、 [std::search_n](https://www.geeksforgeeks.org/stdsearch_n-with-example-in-cpp/) 、 [std::下界](https://www.geeksforgeeks.org/stdlower_bound-in-c/)等各种 STL 算法的模板定义后，你一定找到了它们的模板定义，由类型为**正向迭代器**的对象组成。那么它们是什么，为什么被使用？

**前向迭代器**是 C++ 标准库中存在的五种主要类型的迭代器之一，其他的还有 **[输入迭代器](https://www.geeksforgeeks.org/input-iterators-in-cpp/)****[输出迭代器](https://www.geeksforgeeks.org/output-iterators-c/)****[双向迭代器](https://www.geeksforgeeks.org/bidirectional-iterators-in-cpp/)** 和 **[随机访问迭代器](https://www.geeksforgeeks.org/random-access-iterators-in-cpp/)** 。

前向迭代器被认为是输入和输出迭代器的**组合。它为两者的功能提供支持。它允许值被访问和修改。**

![](img/4ee94c1e4b4b22bb10c8ac1fb40cf559.png)

需要记住的一点是**双向**和**随机访问**迭代器也是有效的前向迭代器，如上面的迭代器层次所示。

**显著特征**

1.  **可用性:**对不可解引用的前向迭代器执行操作永远不会使其迭代器值不可解引用，因此，这使得使用这类迭代器的算法能够使用迭代器的多个副本多次传递相同的迭代器值。所以，它**可以用在多遍算法**中。
2.  **Equality / Inequality Comparison:** A forward iterator can be compared for equality with another iterator. Since, iterators point to some location, so the two iterators will be equal only when they point to the same position, otherwise not.

    因此，如果 A 和 B 是前向迭代器，以下两个表达式是有效的:

    ```cpp
    A == B  // Checking for equality
    A != B  // Checking for inequality

    ```

3.  **Dereferencing:** Because an input iterator can be dereferenced, using the operator * and -> as an rvalue and an output iterator can be dereferenced as an lvalue, so forward iterators can be used for both the purposes.

    ```cpp
    // C++ program to demonstrate forward iterator
    #include <iostream>
    #include <vector>
    using namespace std;
    int main()
    {
        vector<int> v1 = { 1, 2, 3, 4, 5 };

        // Declaring an iterator
        vector<int>::iterator i1;

        for (i1 = v1.begin(); i1 != v1.end(); ++ i1) {
            // Assigning values to locations pointed by iterator
            *i1 = 1;
        }

        for (i1 = v1.begin(); i1 != v1.end(); ++ i1) {
            // Accessing values at locations pointed by iterator
            cout << (*i1) << " ";
        }

        return 0;
    }
    ```

    输出:

    ```cpp
    1 1 1 1 1

    ```

    因此，正如我们在这里看到的，我们既可以访问迭代器，也可以给迭代器赋值，因此迭代器至少是一个前向迭代器(它在层次上也可以更高)。

4.  **Incrementable:** A forward iterator can be incremented, so that it refers to the next element in sequence, using operator ++().

    **注意:**我们可以使用带有增量运算符的前向迭代器这一事实并不意味着运算符–-()也可以与它们一起使用。记住，向前迭代器是单向的，只能向前移动。

    因此，如果 A 是前向迭代器，下面两个表达式是有效的:

    ```cpp
    A++   // Using post increment operator
    ++ A   // Using pre increment operator

    ```

5.  **可交换:**这些迭代器指向的值可以交换或互换。

**实际执行**

在了解了它的特性之后，了解它的实际实现也是非常重要的。如前所述，向前迭代器既可以在我们想要访问元素时使用，也可以在我们必须为元素赋值时使用，因为它是输入和输出迭代器的组合。以下两个 STL 算法可以说明这一事实:

*   **std::replace:** As we know this algorithm is used to replace all the elements in the range which are equal to a particular value by a new value. So, let us look at its internal working (Don’t go into detail just look where forward iterators can be used and where they cannot be):

    ```cpp
    // Definition of std::replace()
    template void replace(ForwardIterator first, ForwardIterator last,
                          const T& old_value, const T& new_value)
    {
        while (first != last) {
            if (*first == old_value) // L1
                *first = new_value; // L2
            ++ first;
        }
    }
    ```

    在这里，我们可以看到我们已经利用了前向迭代器，因为我们需要利用输入和输出迭代器的特性。在 L1，我们需要首先作为右值(输入迭代器)取消引用迭代器，在 L2，我们需要首先作为左值(输出迭代器)取消引用，因此为了完成这两个任务，我们使用了前向迭代器。

*   **std::reverse_copy:** As the name suggests, this algorithm is used to copy a range into another range, but in reverse order. Now, as far as accessing elements and assigning elements are concerned, forward iterators are fine, **but as soon as we have to decrement the iterator, then we cannot use these forward iterators** for this purpose.

    ```cpp
    // Definition of std::reverse_copy()
    template OutputIterator reverse_copy(BidirectionalIterator first,
                                         BidirectionalIterator last,
                                         OutputIterator result)
    {
        while (first != last)
            *result++ = *--last;
        return result;
    }
    ```

    在这里，我们可以看到我们已经将 last 声明为双向迭代器，而不是前向迭代器，因为我们不能像在 last 的情况下那样减少前向迭代器，所以我们不能在这个场景中使用它。

**注意:**因为我们知道前向迭代器是输入和输出迭代器的组合，所以如果任何算法涉及使用这两个迭代器中的任何一个，那么我们也可以在它们的位置使用前向迭代器，而不会影响程序。

所以，上面两个例子很好地展示了何时、何地、为什么以及如何实际使用前向迭代器。

**限制**

在研究了显著的特性之后，我们还必须知道它的不足之处，尽管输入或输出迭代器中的不足之处并不像它在层次结构中的位置那样多。

1.  **Can not be decremented:** Just like we can use operator ++() with forward iterators for incrementing them, we cannot decrement them. Although it is higher in the hierarchy than input and output iterators, still it can’t overcome this deficiency.

    这就是为什么，它的名字叫向前，这说明**它只能向前方向**移动。

    ```cpp
    If A is a forward iterator, then

    A--    // Not allowed with forward iterators

    ```

2.  **关系运算符:**虽然前向迭代器可以与等式运算符(==)一起使用，但它不能与其他关系运算符(如=)一起使用。

    ```cpp
    If A and B are forward iterators, then

    A == B     // Allowed
    A <= B     // Not Allowed

    ```

3.  **算术运算符:**与关系运算符类似，它们也不能用于+、–等算术运算符。这意味着向前的操作符只能在一个方向上移动，这个方向太向前，这个方向太连续。

    ```cpp
    If A and B are forward iterators, then

    A + 1     // Not allowed
    B - 2     // Not allowed

    ```

4.  **使用偏移取消引用运算符([ ]):** 前向迭代器不支持用于随机访问的偏移取消引用运算符([ ])。

    ```cpp
    If A is a forward iterator, then
    A[3]    // Not allowed 

    ```

本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。