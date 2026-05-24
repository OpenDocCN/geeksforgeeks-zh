# c++ 中的随机访问迭代器

> 原文:[https://www . geesforgeks . org/random-access-iterators-in-CPP/](https://www.geeksforgeeks.org/random-access-iterators-in-cpp/)

浏览了各种 STL 算法的模板定义，如 [std::nth_element](https://www.geeksforgeeks.org/stdnth_element-in-cpp/) 、 [std::sort](https://www.geeksforgeeks.org/sort-c-stl/) ，您一定找到了它们的模板定义，该定义由类型为**的随机访问迭代器**的对象组成。那么它们是什么，为什么被使用？

**随机访问迭代器**是 C++ 标准库中存在的五种主要类型的迭代器之一，其他的还有 **[输入迭代器](https://www.geeksforgeeks.org/input-iterators-in-cpp/)****[输出迭代器](https://www.geeksforgeeks.org/output-iterators-c/)****[正向迭代器](https://www.geeksforgeeks.org/forward-iterators-in-cpp/)** 和 **[双向迭代器](https://www.geeksforgeeks.org/bidirectional-iterators-in-cpp/)** 。

随机访问迭代器是一种迭代器，可用于**访问相对于它们所指向元素的任意偏移位置**的元素，提供与指针相同的功能。随机访问迭代器在功能上是**最完整的迭代器**。所有指针类型也是有效的随机访问迭代器。

需要注意的是像 **vector、deque 这样的容器支持随机访问迭代器**。这意味着，如果我们为它们声明普通迭代器，那么这些迭代器将是随机访问迭代器，就像列表、映射、多映射、集合和多集合一样，它们是双向迭代器。

![](img/4ee94c1e4b4b22bb10c8ac1fb40cf559.png)

因此，从上面的层次结构可以说，随机访问迭代器是所有迭代器类型中最强的。

**显著特征**

1.  **可用性:**随机访问迭代器可以**用在多遍算法**中，即涉及在不同遍次中多次处理容器的算法。

2.  **Equality / Inequality Comparison:** A Random-access iterator can be compared for equality with another iterator. Since, iterators point to some location, so the two iterators will be equal only when they point to the same position, otherwise not.

    因此，如果 A 和 B 是随机访问迭代器，以下两个表达式是有效的:

    ```cpp
    A == B  // Checking for equality
    A != B  // Checking for inequality

    ```

3.  **Dereferencing:** A random-access iterator can be **dereferenced both as a rvalue as well as a lvalue.**

    ```cpp
    // C++ program to demonstrate Random-access iterator
    #include<iostream>
    #include<vector>
    using namespace std;
    int main()
    {
        vector<int>v1 = {10, 20, 30, 40, 50};

        // Declaring an iterator
        vector<int>::iterator i1;

        for (i1=v1.begin();i1!=v1.end();++ i1)
        {
            // Assigning values to locations pointed by iterator
            *i1 = 7;
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
    7 7 7 7 7

    ```

    因此，正如我们在这里看到的，我们既可以访问迭代器，也可以给迭代器赋值，因此迭代器是一个随机访问迭代器。

4.  **Incrementable:** A Random-access iterator can be incremented, so that it refers to the next element in sequence, using operator ++(), as seen in the previous code, where i1 was incremented in the for loop.

    因此，如果 A 是随机访问迭代器，下面两个表达式是有效的:

    ```cpp
    A++   // Using post increment operator
    ++ A   // Using pre increment operator

    ```

5.  **Decrementable:** Just like we can use operator ++() with Random-access iterators for incrementing them, we can also decrement them.

    ```cpp
    // C++ program to demonstrate Random-access iterator
    #include<iostream>
    #include<vector>
    using namespace std;
    int main()
    {
        vector<int>v1 = {1, 2, 3, 4, 5};

        // Declaring an iterator
        vector<int>::iterator i1;

        // Accessing the elements from end using decrement
        // operator
        for (i1=v1.end()-1;i1!=v1.begin()-1;--i1)
        {

            cout << (*i1) << " ";

        }
        return 0;
    }
    ```

    输出:

    ```cpp
    5 4 3 2 1

    ```

    因为，我们从向量的末尾开始，然后通过递减指针向开头移动，这表明递减运算符可以用于这样的迭代器。

6.  **关系运算符:**虽然双向迭代器不能与关系运算符如，=，一起使用，但是层次较高的随机访问迭代器支持所有这些关系运算符。

    ```cpp
    If A and B are Random-access iterators, then

    A == B     // Allowed
    A <= B     // Allowed

    ```

7.  **Arithmetic Operators:** Similar to relational operators, they also can be used with arithmetic operators like +, – and so on. This means that Random-access iterators can move in both the direction, and that too randomly.

    ```cpp
    If A and B are Random-access iterators, then

    A + 1     // Allowed
    B - 2     // Allowed

    ```

    ```cpp
    // C++ program to demonstrate Random-access iterator
    #include<iostream>
    #include<vector>
    using namespace std;
    int main()
    {
        vector<int>v1 = {1, 2, 3, 4, 5};

        // Declaring first iterator
        vector<int>::iterator i1;

        // Declaring second iterator
        vector<int>::iterator i2;

        // i1 points to the beginning of the list
        i1 = v1.begin();

        // i2 points to the end of the list
        i2 = v1.end();

        // Applying relational operator to them
        if ( i1 < i2)
        {
            cout << "Yes";
        } 

        // Applying arithmetic operator to them
        int count = i2 - i1;

        cout << "\ncount = " << count;
        return 0;
    }
    ```

    输出:

    ```cpp
    Yes
    count = 5

    ```

    这里，因为 i1 指向开始，i2 指向结束，所以 i2 将大于 i1，并且它们之间的差将是它们之间的总距离。

8.  **Use of offset dereference operator ([ ]):** Random-access iterators support offset dereference operator ([ ]), which is used for random-access.

    ```cpp
    If A is a Random-access iterator, then
    A[3]    // Allowed 

    ```

    ```cpp
    // C++ program to demonstrate Random-access iterator
    #include<iostream>
    #include<vector>
    using namespace std;
    int main()
    {
        vector<int>v1 = {1, 2, 3, 4, 5};
        int i;

        // Accessing elements using offset dereference
        // operator [ ]
        for(i=0;i<5;++ i)
        {
            cout << v1[i] << " ";
        }
        return 0;  
    }
    ```

    输出:

    ```cpp
    1 2 3 4 5

    ```

9.  **可交换:**这些迭代器指向的值可以交换或互换。

**实际执行**

在了解了它的特性之后，了解它的实际实现也是非常重要的。如前所述，随机访问迭代器可以用于任何目的和任何场景。下面的 STL 算法展示了它的一个实际实现:

*   **std::random_shuffle:** As we know this algorithm is used to randomly shuffle all the elements present in a container. So, let us look at its internal working (Donot go into detail just look where random-access iterators can be used):

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

    在这里，我们可以看到我们使用了随机访问迭代器，因为没有其他类型的迭代器支持算术运算符，这就是我们使用它的原因。

事实上，如果你正在考虑使用随机访问迭代器，那么你可以**使用随机访问迭代器来代替任何其他类型的迭代器**，因为它是 C++ 标准库中最强和最好的迭代器类型。

本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。