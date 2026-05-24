# c++ 库中的 boost::algorithm::clamp()

> 原文:[https://www . geeksforgeeks . org/boostalgorithmclamp-in-c-library/](https://www.geeksforgeeks.org/boostalgorithmclamp-in-c-library/)

**[C++ boost 库](https://www.geeksforgeeks.org/advanced-c-boost-library/)** 中的 **clamp()** 函数位于标题*下,“boost/algorithm/clamp . HPP”*包含两个函数，用于在一对边界值之间“箝位”一个值。

**语法**:

```cpp
const T& clamp ( const T& val, const T& lo, const T& hi )
or 
const T& clamp ( const T& value, const T& low, const T& high, Pred p )
```

**参数**:该功能接受如下参数:

*   **值**:指定比较的值。
*   **low**: This specifies the lower range.
    *   **高**:指定较高的范围。
    *   **p** :这指定了谓词函数。

    **返回值**:该函数返回如下三个值:

    *   如果值小于低，则返回低。
    *   如果 high 大于 value，则返回 high。
    *   在所有其他情况下，它都会返回值。

    **程序-1** :

    ```cpp
    // C++ program to implement the
    // above mentioned function

    #include <bits/stdc++.h>
    #include <boost/algorithm/clamp.hpp>
    using namespace std;

    // Drivers code
    int main()
    {

        int value = 5;
        int low = 10, high = 20;

        // Function used
        int ans
            = boost::algorithm::clamp(value, low, high);

        cout << ans;
        return 0;
    }
    ```

    **Output:**

    ```cpp
    10

    ```

    **程序-2** :

    ```cpp
    // C++ program to implement the
    // above mentioned function

    #include <bits/stdc++.h>
    #include <boost/algorithm/clamp.hpp>
    using namespace std;

    // Drivers code
    int main()
    {

        int value = 25;
        int low = 10, high = 20;

        // Function used
        int ans
            = boost::algorithm::clamp(value, low, high);
        cout << ans;
        return 0;
    }
    ```

    **Output:**

    ```cpp
    20

    ```

    **程序-3** :

    ```cpp
    // C++ program to implement the
    // above mentioned function

    #include <bits/stdc++.h>
    #include <boost/algorithm/clamp.hpp>
    using namespace std;

    // Drivers code
    int main()
    {

        int value = 15;
        int low = 10, high = 20;

        // Function used
        int ans
            = boost::algorithm::clamp(value, low, high);
        cout << ans;
        return 0;
    }
    ```

    **Output:**

    ```cpp
    15

    ```

    **参考**:[https://www . boost . org/doc/libs/1 _ 70 _ 0/libs/algorithm/doc/html/the _ boost _ algorithm _ library/CXX14/mismatch . html](https://www.boost.org/doc/libs/1_70_0/libs/algorithm/doc/html/the_boost_algorithm_library/CXX14/mismatch.html)