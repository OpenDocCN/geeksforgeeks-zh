# c++ STL 中的 not1 和 not2 函数模板，示例

> 原文:[https://www . geesforgeks . org/not 1-和-not 2-function-templates-in-c-STL-with-examples/](https://www.geeksforgeeks.org/not1-and-not2-function-templates-in-c-stl-with-examples/)

这些函数采用一元和二元[函数对象(函子)](https://www.geeksforgeeks.org/functors-in-cpp)，并返回该函数对象的补码。它可以在竞争程序设计中得到二进制和一元函数的补码。

**当为补码函数写代码比较难或者比较冗长的时候，这些函数非常有用。**例如，如果我们想从一个字符串中删除辅音，那么我们可以为**编写一个一元函数，并可以在 STL 的 [remove_if 函数中使用它的补语。](https://www.geeksforgeeks.org/stdremove-stdremove_if-c/)**

1.  **not1:** This function takes unary function object and returns its complement object. Here we need to define argument_type for unary functor in our functor.

    **语法:**

    ```cpp
    template <class Predicate> 
      unary_negate<Predicate> 
        not1 (const Predicate& pred)
    {
      return unary_negate<Predicate>(pred);
    }

    ```

    **参数:**函数接受一个强制参数 **pred** ，指定要求反的一元函数对象。

    **返回值:**函数返回被求反的一元对象。

    **示例:**

    ```cpp
    // C++ program to demonstrate
    // not1 function template

    #include <bits/stdc++.h>
    using namespace std;

    struct pred {
        bool operator()(const int i) const
        {
            return (i % 2 == 0);
        }

        // defines argument_type for unary functor
        // it is begin used by not1
        // as argument_type
        typedef int argument_type;
    };

    // Driver code
    int main()
    {
        vector<int> odd{ 1, 2, 3, 4, 5,
                         6, 7, 8, 9, 10 };

        // simple pred functor use
        // it removes even numbers
        auto end
            = remove_if(odd.begin(),
                        odd.end(),
                        pred());

        odd.resize(distance(odd.begin(), end));

        cout << "removal of even elements: ";
        for (int i = 0; i < odd.size(); i++) {
            cout << odd[i] << " ";
        }
        cout << "\n";

        vector<int> even{ 1, 2, 3, 4, 5,
                          6, 7, 8, 9, 10 };

        // complement of pred using not1
        // which removes odd numbers
        end
            = remove_if(even.begin(),
                        even.end(),
                        not1(pred()));

        even.resize(distance(even.begin(), end));

        cout << "removal of odd elements: ";
        for (int i = 0; i < even.size(); i++) {
            cout << even[i] << " ";
        }

        return 0;
    }
    ```

    **Output:**

    ```cpp
    removal of even elements: 1 3 5 7 9 
    removal of odd elements: 2 4 6 8 10

    ```

2.  **not2:** This function takes binary functor as argument and returns complement functor of it.

    **语法:**

    ```cpp
    template <class Predicate> 
      binary_negate<Predicate> 
        not2 (const Predicate& pred)
    {
      return binary_negate<Predicate>(pred);
    }

    ```

    **参数:**函数接受一个强制参数 **pred** ，指定要求反的二元函数对象。

    **返回值:**函数返回被求反的二进制对象。

    **示例:**

    ```cpp
    // C++ program to demonstrate
    // not2 function template

    #include <bits/stdc++.h>
    using namespace std;

    int main()
    {
        vector<int> vec{ 4, 2, 7, 9, 3, 5, 10, 6 };

        // simple use of not2 just provide binary
        // functor and it will return it complement
        sort(vec.begin(), vec.end(), not2(less<int>()));

        for (int i = 0; i < vec.size(); i++) {
            cout << vec[i] << " ";
        }
        return 0;
    }
    ```

    **Output:**

    ```cpp
    10 9 7 6 5 4 3 2

    ```

    **参考文献:**

    *   [http://www.cplusplus.com/reference/functional/not1/](http://www.cplusplus.com/reference/functional/not1/)
    *   [http://www.cplusplus.com/reference/functional/not2/](http://www.cplusplus.com/reference/functional/not2/)