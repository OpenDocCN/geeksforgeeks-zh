# C++ 程序找到给定迭代器的类型

> 原文:[https://www . geesforgeks . org/CPP-program-to-find-type-of-the-of-the-给定-iterator/](https://www.geeksforgeeks.org/cpp-program-to-find-the-type-of-the-given-iterator/)

给定一个使用迭代器的程序，任务是找到所使用的迭代器的类型。

**示例:**

> **输入:** vector.begin()
> **输出:**随机访问迭代器
> 
> **输入:**list . begin()
> T3】输出:双向迭代器

也就是说，C++ 标准库中有五种类型的迭代器，如下所述:

*   *[c++ 中的正向迭代器](https://www.geeksforgeeks.org/forward-iterators-in-cpp/)**   *[c++ 中的双向 _ 迭代器](https://www.geeksforgeeks.org/bidirectional-iterators-in-cpp/)**   *[c++ 中的输入迭代器](https://www.geeksforgeeks.org/input-iterators-in-cpp/)**   *[c++ 中的输出迭代器](https://www.geeksforgeeks.org/output-iterators-cpp/)**   *[Random_access iterators in C++ ](https://www.geeksforgeeks.org/random-access-iterators-in-cpp/)

    **进场:**

    *   迭代器类型可以通过使用 **typeid** 来检查。typeid 是一个 C++ 语言运算符，它在运行时返回类型标识信息。它基本上返回一个 type_info 对象，该对象与其他 type_info 对象是等价的。
    *   同时使用**迭代器特征**。Traits 类定义迭代器的属性。标准算法通过使用相应 iterator_traits 实例化的成员来确定传递给它们的迭代器的某些属性以及它们所代表的范围。
    *   还传递了一个**迭代器类别**，它定义了迭代器所属的迭代器类别。
        标签有五种类型，即: *input_iterator_tag* 、 *output_iterator_tag* 、 *forward_iterator_tag* 、*双向 _iterator_tag* 、*random _ access _ iterator _ tag*。
    *   **typename** 与它一起用于在实例化期间向迭代器提供类型。
    *   现在，如果输入迭代器的迭代器类别与现有的迭代器类别匹配，就会显示结果。

    ```cpp
    // C++ program to find the type of iterator
    #include <bits/stdc++.h>
    using namespace std;
    template <class T>

    // function to return the iterator type
    string get_iterator_type(T it)
    {
        // if the iterator category of (it) matches input
        if (typeid(typename iterator_traits<T>::iterator_category)
            == typeid(input_iterator_tag))
            return "Input";

        // if the iterator category of (it) matches output
        else if (typeid(typename iterator_traits<T>::iterator_category)
                 == typeid(output_iterator_tag))
            return "Output";

        // if the iterator category of (it) matches forward
        else if (typeid(typename iterator_traits<T>::iterator_category)
                 == typeid(forward_iterator_tag))
            return "Forward";

        // if the iterator category of (it) matches bidirectional
        else if (typeid(typename iterator_traits<T>::iterator_category)
                 == typeid(bidirectional_iterator_tag))
            return "Bidirectional";

        // if the iterator category of (it) matches random_access
        else if (typeid(typename iterator_traits<T>::iterator_category)
                 == typeid(random_access_iterator_tag))
            return "Random_Access";

        // if the iterator category of (it)
        // does not match any of the above
        return "Missing";
    }

    // Driver code
    int main()
    {
        vector<int> v;

        // iterator that will be checked
        auto it = v.begin();

        cout << get_iterator_type(it) << " Iterator\n";

        return 0;
    }
    ```

    **Output:**

    ```cpp
    Random_Access Iterator

    ```

    **时间复杂度:** O(1)查找迭代器类型*