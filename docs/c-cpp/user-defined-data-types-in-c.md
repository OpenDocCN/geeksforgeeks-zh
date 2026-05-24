# c++ 中用户定义的数据类型

> 原文:[https://www.geeksforgeeks.org/user-defined-data-types-in-c/](https://www.geeksforgeeks.org/user-defined-data-types-in-c/)

**数据类型**是识别数据类型和处理数据的相关操作的手段。有三种数据类型:

1.  [预定义数据类型](https://www.geeksforgeeks.org/c-data-types/)
2.  [派生数据类型](https://www.geeksforgeeks.org/derived-data-types-in-c/)
3.  用户定义的数据类型

[![](img/e34f4bbc81e4786f2a7e8a88974702de.png)](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20191113115600/DatatypesInC.png)

在本文中，将解释用户定义的数据类型:

### 用户定义的数据类型:

用户定义的数据类型称为派生数据类型或用户定义的派生数据类型。
这些类型包括:

*   [级](https://www.geeksforgeeks.org/c-classes-and-objects/)
*   [结构](https://www.geeksforgeeks.org/structures-c/)
*   [工会](https://www.geeksforgeeks.org/union-c/)
*   [枚举](https://www.geeksforgeeks.org/enumeration-enum-c/)
*   Typedef 定义的数据类型

以下是以下类型的详细描述:

1.  **[Class](https://www.geeksforgeeks.org/c-classes-and-objects/):** The building block of C++ that leads to Object-Oriented programming is a **Class**. It is a user-defined data type, which holds its own data members and member functions, which can be accessed and used by creating an instance of that class. A class is like a blueprint for an object.

    **语法** :
    ![classes-and-objects-in-c](img/f21aadcadb8192f44d1badfacf248f3b.png)

    **示例:**

    ```cpp
    // C++ program to demonstrate
    // Class

    #include <bits/stdc++.h>
    using namespace std;

    class Geeks {
        // Access specifier
    public:
        // Data Members
        string geekname;

        // Member Functions()
        void printname()
        {
            cout << "Geekname is: " << geekname;
        }
    };

    int main()
    {

        // Declare an object of class geeks
        Geeks obj1;

        // accessing data member
        obj1.geekname = "GeeksForGeeks";

        // accessing member function
        obj1.printname();

        return 0;
    }
    ```

    **Output:**

    ```cpp
    Geekname is: GeeksForGeeks

    ```

2.  **[Structure](https://www.geeksforgeeks.org/structures-c/)**: A structure is a user defined data type in C/C++. A structure creates a data type that can be used to group items of possibly different types into a single type.

    **语法:**

    ```cpp
    struct address {
        char name[50];
        char street[100];
        char city[50];
        char state[20];
        int pin;
    };
    ```

    **示例:**

    ```cpp
    // C++ program to demonstrate
    // Structures in C++

    #include <iostream>
    using namespace std;

    struct Point {
        int x, y;
    };

    int main()
    {
        // Create an array of structures
        struct Point arr[10];

        // Access array members
        arr[0].x = 10;
        arr[0].y = 20;

        cout << arr[0].x << ", " << arr[0].y;

        return 0;
    }
    ```

    **Output:**

    ```cpp
    10, 20

    ```

3.  **[联合](https://www.geeksforgeeks.org/union-c/)** :和[结构](https://www.geeksforgeeks.org/structures-c/)一样，联合是用户自定义的数据类型。在联合中，所有成员共享相同的内存位置。例如，在下面的 C 程序中，x 和 y 共享同一个位置。如果我们改变 x，我们可以看到变化反映在 y 中。

    ```cpp
    #include <iostream>
    using namespace std;

    // Declaration of union is same as the structures
    union test {
        int x, y;
    };

    int main()
    {
        // A union variable t
        union test t;

        // t.y also gets value 2
        t.x = 2;

        cout << "After making x = 2:"
             << endl
             << "x = " << t.x
             << ", y = " << t.y
             << endl;

        // t.x is also updated to 10
        t.y = 10;

        cout << "After making Y = 10:"
             << endl
             << "x = " << t.x
             << ", y = " << t.y
             << endl;

        return 0;
    }
    ```

    **输出:**

    ```cpp
    After making x = 2:
    x = 2, y = 2
    After making Y = 10:
    x = 10, y = 10

    ```

4.  **[Enumeration](https://www.geeksforgeeks.org/enumeration-enum-c/)**: Enumeration (or enum) is a user defined data type in C. It is mainly used to assign names to integral constants, the names make a program easy to read and maintain.

    **语法:**

    ```cpp
    enum State {Working = 1, Failed = 0}; 
    ```

    ```cpp
    // Program to demonstrate working
    // of enum in C++

    #include <iostream>
    using namespace std;

    enum week { Mon,
                Tue,
                Wed,
                Thur,
                Fri,
                Sat,
                Sun };

    int main()
    {
        enum week day;

        day = Wed;

        cout << day;

        return 0;
    }
    ```

    **Output:**

    ```cpp
    2

    ```

5.  **Typedef** : C++ allows you to define explicitly new data type names by using the keyword typedef. Using typedef does not actually create a new data class, rather it defines a name for an existing type. This can increase the portability(the ability of a program to be used across different types of machines; i.e., mini, mainframe, micro, etc; without much changes into the code)of a program as only the typedef statements would have to be changed. Using typedef one can also aid in self-documenting code by allowing descriptive names for the standard data types.

    **语法:**

    ```cpp
    typedef type name;
    ```

    其中*类型*为任意 C++ 数据类型，*名称*为该数据类型的新名称。
    这为 C++ 的标准*类型*定义了另一个名称。

    **示例:**

    ```cpp
    // C++ program to demonstrate typedef
    #include <iostream>
    using namespace std;

    // After this line BYTE can be used
    // in place of unsigned char
    typedef unsigned char BYTE;

    int main()
    {
        BYTE b1, b2;
        b1 = 'c';
        cout << " " << b1;
        return 0;
    }
    ```

    **Output:**

    ```cpp
    c

    ```