# c++ 中的数组类型操作

> 原文:[https://www.geeksforgeeks.org/array-type-manipulation-in-c/](https://www.geeksforgeeks.org/array-type-manipulation-in-c/)

本文演示了一些可以用来查询和操作数组类型的内置函数，甚至是多维数组。这些函数在我们需要信息或操作不同维度的数组时非常有用。这些函数在头文件中定义。一些函数包括:

1.  **is _ array ():** As the name implies, the only purpose of this function is to check whether a variable is of array type. It is worth noting here that according to this function, even [STD:: array](https://www.geeksforgeeks.org/array-class-c/) is not regarded as an array. The "value" member constant returns true if the type is an array, otherwise it returns false.
2.  **is_same() :** 此功能是检查**类型关系**，如果两个类型具有完全相同的特征，则返回 true。如果类型相同，“value”成员常量返回 true，否则返回 false。

    ```cpp
    // C++ code to demonstrate the working of 
    // is_array() and is_same()

    #include<type_traits>
    #include<iostream>
    #include<array>
    #include<string>
    using namespace std;

    int main()
    {
        // checking which is array using is_array
        cout << "Is Integer an array? : " << is_array<int>::value << endl;

        cout << "Is Array an array? : " << is_array<int[10]>::value << endl;

        cout << "Is 2D Array an array? : " 
        << is_array<int[10][10]>::value << endl;

        cout << "Is String an array? : " << is_array<string>::value << endl;

        cout << "Is Character Array an array? : " 
        << is_array<char[10]>::value << endl;

        cout << "Is Array class type an array? : " 
        << is_array<array<int,3>>::value << endl;

        cout << endl;

        // checking for same types using is_same()
        cout << "Is 2D array same as 1D array? : " << 
        is_same<int[10],int[10][10]>::value << endl;

        cout << "Is Character array same as Integer array? : " 
        << is_same<int[10],char[10]>::value << endl;

        cout << "Is 1D array same as 1D array (Different sizes) ? : " 
        << is_same<int[10],int[20]>::value << endl;

        cout << "Is 1D array same as 1D array? (Same sizes): " 
        << is_same<int[10],int[10]>::value << endl;
        return 0;
    }
    ```

    输出:

    ```cpp
    Is Integer an array? : 0
    Is Array an array? : 1
    Is 2D Array an array? : 1
    Is String an array? : 0
    Is Character Array an array? : 1
    Is Array class type an array? : 0

    Is 2D array same as 1D array? : 0
    Is Character array same as Integer array? : 0
    Is 1D array same as 1D array (Different sizes) ? : 0
    Is 1D array same as 1D array? (Same sizes): 1

    ```

3.  **Rank ():** This is a **attribute query function** , which returns the rank of the array. Is the **dimension of the grade index group. The value constant returns the level of the object.

    ```cpp
    // C++ code to demonstrate the working of 
    // rank()

    #include<type_traits> // for array query functions
    #include<iostream>
    using namespace std;

    int main()
    {
        // checking rank of different types
        cout << "The rank of integer is : " << rank<int>::value << endl;

        cout << "The rank of 1D integer array is : " 
        << rank<int[10]>::value << endl;

        cout << "The rank of 2D integer array is : " 
        << rank<int[20][10]>::value << endl;

        cout << "The rank of 3D integer array is : " 
        << rank<int[20][10][40]>::value << endl;

        cout << "The rank of 1D character array is : " 
        << rank<char[10]>::value << endl;

        cout << endl;

    }
    ```

    Output:

    ```cpp
    The rank of integer is : 0
    The rank of 1D integer array is : 1
    The rank of 2D integer array is : 2
    The rank of 3D integer array is : 3
    The rank of 1D character array is : 1

    ```** 
4.  ****Range ():** Range and removal range are both **composite type changes** , which can be applied to arrays in C++. This function returns the size of a specific dimension of the array. This function has two parameters, array type and size. There are also member constant values for printing values.**
5.  ****Remove _ extend ():** This function deletes the first dimension from the left in the declared matrix/array.**
***   **Remove _ all _ extends ():** This function removes all dimensions of a matrix/array and converts them into basic data types. [T2】 T40] Output:

    ```cpp
    The extent of 1st dimension of 3D integer array is  : 20
    The extent of 2nd dimension of 3D integer array is  : 10
    The extent of 3rd dimension of 3D integer array is  : 40
    The extent of 4th dimension of 3D integer array is  : 0

    The rank after removing 1 extent is : 2
    The extent of 1st after removing 1 extent is : 10

    The rank after removing all extents is : 0
    The extent of 1st after removing all extents is : 0

    ```

    T41] T42 T44 T46**

如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论