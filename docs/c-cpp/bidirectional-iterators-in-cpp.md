# c++ 中的双向迭代器

> 原文:[https://www . geesforgeks . org/双向-迭代器-in-cpp/](https://www.geeksforgeeks.org/bidirectional-iterators-in-cpp/)

浏览了各种 STL 算法的模板定义，如 [std::reverse](http://contribute.geeksforgeeks.org/stdreverse-in-c/) 、[STD::next _ replacement](http://www.cplusplus.com/reference/algorithm/next_permutation/)和 [std::reverse_copy](http://www.cplusplus.com/reference/algorithm/reverse_copy/) 之后，您一定找到了它们的模板定义，该定义由类型为**双向迭代器**的对象组成。那么它们是什么，为什么被使用？

**双向迭代器**是 C++ 标准库中存在的五种主要迭代器类型之一，其他的还有 **[输入迭代器](https://www.geeksforgeeks.org/input-iterators-in-cpp/)****[输出迭代器](https://www.geeksforgeeks.org/output-iterators-c/)****[正向迭代器](https://www.geeksforgeeks.org/forward-iterators-in-cpp/)** 和 **[随机访问迭代器](https://www.geeksforgeeks.org/random-access-iterators-in-cpp/)** 。

双向迭代器是一种迭代器，可用于在**两个方向**访问一个范围内的元素序列(朝末尾和朝开头)。它们类似于向前迭代器，除了它们可以**向后移动**，也不同于向前迭代器，向前迭代器只能向前移动。

需要注意的是像**这样的容器列表、映射、多映射、集合和多集合都支持双向迭代器**。这意味着，如果我们为它们声明普通迭代器，那么它们将是双向迭代器，就像向量和 deque 一样，它们是随机访问迭代器。

![](img/4ee94c1e4b4b22bb10c8ac1fb40cf559.png)

需要记住的一点是**随机访问**迭代器也是有效的双向迭代器，如上面的迭代器层次所示。

**显著特征**

1.  **可用性:**由于前向迭代器可以用于多遍算法，即涉及在各遍中多次处理容器的算法，因此双向迭代器也可以用于多遍算法。
    。
2.  **Equality / Inequality Comparison:** A Bidirectional iterator can be compared for equality with another iterator. Since, iterators point to some location, so the two iterators will be equal only when they point to the same position, otherwise not.

    因此，如果 A 和 B 是双向迭代器，以下两个表达式是有效的:

    ```cpp
    A == B  // Checking for equality
    A != B  // Checking for inequality

    ```

3.  **Dereferencing:** Because an input iterator can be dereferenced, using operator * and -> as an rvalue and an output iterator can be dereferenced as an lvalue, so forward iterators being the combination of both can be used for both the purposes, and similarly, bidirectional operators can also serve both the purposes.

    ```cpp
    // C++ program to demonstrate bidirectional iterator
    #include<iostream>
    #include<list>
    using namespace std;
    int main()
    {
        list<int>v1 = {1, 2, 3, 4, 5};

        // Declaring an iterator
        list<int>::iterator i1;

        for (i1=v1.begin();i1!=v1.end();++ i1)
        {
            // Assigning values to locations pointed by iterator
            *i1 = 1;
        }

        for (i1=v1.begin();i1!=v1.end();++ i1)
        {
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

    因此，正如我们在这里看到的，我们既可以访问迭代器，也可以给迭代器赋值，因此迭代器是一个双向迭代器。

4.  **Incrementable:** A Bidirectional iterator can be incremented, so that it refers to the next element in sequence, using operator ++().

    因此，如果 A 是双向迭代器，以下两个表达式是有效的:

    ```cpp
    A++   // Using post increment operator
    ++ A   // Using pre increment operator

    ```

5.  **Decrementable:** This is the feature which differentiates a Bidirectional iterator from a forward iterator. Just like we can use operator ++() with bidirectional iterators for incrementing them, we can also decrement them.

    这就是为什么，它的名字叫双向，说明**它可以双向移动**。

    ```cpp
    // C++ program to demonstrate bidirectional iterator
    #include<iostream>
    #include<list>
    using namespace std;
    int main()
    {
        list<int>v1 = {1, 2, 3, 4, 5};

        // Declaring an iterator
        list<int>::iterator i1;

        // Accessing the elements from end using decrement
        // operator
        for (i1=v1.end();i1!=v1.begin();--i1)
        {
            if (i1 != v1.end())
            {
                cout << (*i1) << " ";
            }
        }
        cout << (*i1);

        return 0;
    }
    ```

    输出:

    ```cpp
    5 4 3 2 1

    ```

    因为，我们从列表的末尾开始，然后通过递减指针向开头移动，这表明递减运算符可以用于这种迭代器。这里，我们运行循环，直到迭代器变得等于 begin()，这就是为什么第一个值不在循环中打印，而是单独打印的原因。

6.  **可交换:**这些迭代器指向的值可以交换或互换。

**实际执行**

在了解了它的特性之后，了解它的实际实现也是非常重要的。如前所述，双向迭代器可以用于前向迭代器在迭代器需要递减的情况下可以使用的所有目的。以下两个 STL 算法可以说明这一事实:

*   **std::reverse_copy:** As the name suggests, this algorithm is used to copy a range into another range, but in reverse order. Now, as far as accessing elements and assigning elements are concerned, forward iterators are fine, **but as soon as we have to decrement the iterator, then we cannot use these forward iterators** for this purpose, and that’s where bidirectional iterators come for our rescue.

    ```cpp
    // Definition of std::reverse_copy()
    template 
    OutputIterator reverse_copy(BidirectionalIterator first,
                                BidirectionalIterator last,
                                OutputIterator result) 
    {
        while (first != last) 
        *result++ = *--last;
        return result;
    }
    ```

    在这里，我们可以看到，我们已经将 last 声明为双向迭代器，因为我们不能像在 last 的情况下那样减少正向迭代器，所以我们不能在这个场景中使用它，我们必须仅将其声明为双向迭代器。

*   **std::random_shuffle:** As we know this algorithm is used to randomly shuffle all the elements present in a container. So, let us look at its internal working (Don’t go into detail just look where bidirectional iterators can be used and where they cannot be):

    ```cpp
    // Definition of std::random_shuffle()
    template 
    void random_shuffle(RandomAccessIterator first,
                        RandomAccessIterator last,
                        RandomNumberGenerator& gen)
    {
        iterator_traits::difference_type i, n;
        n = (last - first);
        for (i=n-1; i>0; --i) 
        {
            swap (first[i],first[gen(i+1)]);
        }
    }
    ```

    在这里，我们可以看到我们使用了随机访问迭代器，虽然我们可以增加一个双向迭代器，也可以减少它，但是**我们不能对它应用像+、–**这样的算术运算符，这就是这个算法中需要的，其中(最后–首先)完成，因此，出于这个原因，我们不能在这些场景中使用双向迭代器。

**注意:**由于我们知道双向迭代器在层次结构中比正向迭代器高，而正向迭代器本身又比输入输出迭代器高，因此，这三种类型的迭代器都可以被双向迭代器替代，不会影响算法的工作。

所以，上面的两个例子很好地展示了双向迭代器实际使用的时间、地点、原因和方式。

**限制**

在研究了显著的特性之后，我们还必须知道它的不足之处，尽管输入或输出迭代器中的不足之处并不像它在层次结构中的位置那样多。

1.  **关系运算符:**虽然，双向迭代器可以与等式运算符(==)一起使用，但它不能与其他关系运算符(如，=)一起使用。

    ```cpp
    If A and B are Bidirectional iterators, then

    A == B     // Allowed
    A <= B     // Not Allowed

    ```

2.  **Arithmetic Operators:** Similar to relational operators, they also can’t be used with arithmetic operators like +, – and so on. This means that bidirectional iterators can move in both the direction, but sequentially.

    ```cpp
    If A and B are Bidirectional iterators, then

    A + 1     // Not allowed
    B - 2     // Not allowed

    ```

    ```cpp
    // C++ program to demonstrate bidirectional iterator
    #include<iostream>
    #include<list>
    using namespace std;
    int main()
    {
        list<int>v1 = {1, 2, 3, 4, 5};

        // Declaring first iterator
        list<int>::iterator i1;

        // Declaring second iterator
        list<int>::iterator i2;

        // i1 points to the beginning of the list
        i1 = v1.begin();

        // i2 points to the end of the list
        i2 = v1.end();

        // Applying relational operator to them
        if ( i1 > i2)
        {
            cout << "Yes";
        } 
        // This will throw an error because relational
        // operators cannot be applied to bidirectional iterators

        // Applying arithmetic operator to them
        int count = i1 - i2;
        // This will also throw an error because arithmetic 
        // operators cannot be applied to bidirectional iterators  
        return 0;
    }
    ```

    输出:

    ```cpp
    Error, because of use of arithmetic and relational operators 
    with bidirectional iterators 

    ```

3.  **使用偏移取消引用运算符([ ]):** 双向迭代器不支持用于随机访问的偏移取消引用运算符([ ])。

    ```cpp
    If A is a Bidirectional iterator, then
    A[3]    // Not allowed 

    ```

本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。