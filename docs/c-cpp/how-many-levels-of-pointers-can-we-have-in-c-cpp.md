# 在 C/C++

中我们可以有多少级指针

> 原文:[https://www . geeksforgeeks . org/多少级指针-我们可以拥有-in-c-cpp/](https://www.geeksforgeeks.org/how-many-levels-of-pointers-can-we-have-in-c-cpp/)

**先决条件:**[C 和 C++ 中的指针](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/)[C 中的双指针(指向指针的指针)](https://www.geeksforgeeks.org/double-pointer-pointer-pointer-c/)

**指针**用于指向变量的存储位置。指针存储变量的地址，变量的值可以通过指针的解引用来访问。
指针通常初始化为:

```cpp
datatype *variable name;

```

上面的声明是一个指针，但还可以有更多的指针。这被称为指针的**级**。根据 ANSI C，每个编译器必须至少有 **12 级**的指针。这意味着我们可以使用带有变量名的 12 *符号。

**<u>C/c++ </u>中指针的级别:**
指针或说链的级别可以根据内存大小上升到 N 级。如果要创建**级-5** 的指针，需要在声明时在指针变量名前加 5 个星号 **(*)** 。

**语法:**

```cpp
// level-1 pointer declaration
datatype *pointer; 

// level-2 pointer declaration
datatype **pointer; 

// level-3 pointer declaration
datatype ***pointer; 
.
.
and so on

```

指针的级别取决于声明时指针变量前面有多少星号。

**申报:**

```cpp
int *pointer_1;
int **pointer_2;
int ***pointer_3;
.
.
and so on

```

下面是说明不同级别指针的程序:

**节目 1:**

## C

```cpp
// C program to illustrate levels of pointer
#include <stdio.h>

// Driver Code
int main()
{
    int var = 10;

    // Pointer level-1
    // Declaring pointer to  var
    int* ptr1;

    // Pointer level-2
    // Declaring pointer to pointer
    // variable *ptr1
    int** ptr2;

    // Pointer level-3
    // Declaring pointer to double
    // pointer **ptr2
    int*** ptr3;

    // Storing address of var
    // to pointer variable ptr1
    ptr1 = &var;

    // Storing address of pointer
    // ptr1 to level-2 ptr2
    ptr2 = &ptr1;

    // Storing address of level-2
    // ptr2 to level-3 pointer ptr3
    ptr3 = &ptr2;

    // Displaying values
    printf("Value of variable "
           "var = %d\n",
           var);
    printf("Value of variable var using"
           " pointer ptr1 = %d\n",
           *ptr1);
    printf("Value of variable var using"
           " pointer ptr2 = %d\n",
           **ptr2);
    printf("Value of variable var using"
           " pointer ptr3 = %d\n",
           ***ptr3);

    return 0;
}
```

## C++

```cpp
// C++ program to illustrate
// levels of pointer
#include <bits/stdc++.h>
using namespace std;

// Driver Code
int main()
{
    int var = 10;

    // Pointer level-1
    // Declaring pointer to  var
    int* ptr1;

    // Pointer level-2
    // Declaring pointer to pointer
    // variable *ptr1
    int** ptr2;

    // Pointer level-3
    // Declaring pointer to double
    // pointer **ptr2
    int*** ptr3;

    // Storing address of var
    // to pointer variable ptr1
    ptr1 = &var;

    // Storing address of pointer
    // ptr1 to level-2 ptr2
    ptr2 = &ptr1;

    // Storing address of level-2
    // ptr2 to level-3 pointer ptr3
    ptr3 = &ptr2;

    // Displaying values
    cout << "Value of variable var is "
         << var << endl;

    cout << "Value of variable var "
         << "using pointer ptr1 is "
         << *ptr1 << endl;

    cout << "Value of variable var "
         << "using pointer ptr2 is "
         << **ptr2 << endl;

    cout << "Value of variable var "
         << "using pointer ptr3 is "
         << ***ptr3 << endl;

    return 0;
}
```

**Output:**

```cpp
Value of variable var = 10
Value of variable var using pointer ptr1 = 10
Value of variable var using pointer ptr2 = 10
Value of variable var using pointer ptr3 = 10

```

**节目 2:**

## C

```cpp
// C program to illustrate
// levels of pointer
#include <stdio.h>

// Driver Code
int main()
{
    float var = 23.564327;

    // Declaring pointer variables
    // upto level_4
    float *ptr1, **ptr2, ***ptr3, ****ptr4;

    // Iinitializing pointer
    // variables
    ptr1 = &var;
    ptr2 = &ptr1;
    ptr3 = &ptr2;
    ptr4 = &ptr3;

    // Printing values
    printf("Value of var = %f\n", var);
    printf("Value of var using level-1"
           " pointer = %f\n",
           *ptr1);

    printf("Value of var using level-2"
           " pointer = %f\n",
           **ptr2);

    printf("Value of var using level-3"
           " pointer = %f\n",
           ***ptr3);

    printf("Value of var using level-4"
           " pointer = %f\n",
           ****ptr4);

    return 0;
}
```

## C++

```cpp
// C++ program to illustrate
// levels of pointer
#include <bits/stdc++.h>
using namespace std;

// Driver Code
int main()
{
    float var = 23.564327;

    // Declaring pointer variables
    // upto level_4
    float *ptr1, **ptr2, ***ptr3, ****ptr4;

    // Iinitializing pointer
    // variables
    ptr1 = &var;
    ptr2 = &ptr1;
    ptr3 = &ptr2;
    ptr4 = &ptr3;

    // Printing values
    cout << "Value of var is "
         << var << endl;

    cout << "Value of var using level-1"
         << " pointer is "
         << *ptr1 << endl;

    cout << "Value of var using level-2"
         << " pointer is "
         << **ptr2 << endl;

    cout << "Value of var using level-3"
         << " pointer is "
         << ***ptr3 << endl;

    cout << "Value of var using level-4"
         << " pointer is "
         << ****ptr4 << endl;

    return 0;
}
```

**Output:**

```cpp
Value of var = 23.564327
Value of var using level-1 pointer = 23.564327
Value of var using level-2 pointer = 23.564327
Value of var using level-3 pointer = 23.564327
Value of var using level-4 pointer = 23.564327

```

**解释:**
上面的代码中我们已经取了变量的 float 数据类型，所以现在我们也要为指针链取相同的数据类型。作为指针和变量，它所指向的应该具有相同的数据类型。

**节目 3:**

## C

```cpp
// C program to illustrate
// levels of pointer
#include <stdio.h>

// Driver Code
int main()
{
    // Initializing integer variable
    int var = 10;

    // Declaring pointer variables
    // upto level-3
    int *ptr1, **ptr2, ***ptr3;

    // Iinitializing pointer variables
    ptr1 = &var;
    ptr2 = &ptr1;
    ptr3 = &ptr2;

    // Printing values BEFORE updation
    printf("Before:\n");
    printf("Value of var = %d\n", var);

    printf("Value of var using level-1"
           " pointer = %d\n",
           *ptr1);

    printf("Value of var using level-2"
           " pointer = %d\n",
           **ptr2);

    printf("Value of var using level-3"
           " pointer = %d\n",
           ***ptr3);

    // Updating var's value using
    // level-3 pointer
    ***ptr3 = 35;

    // Printing values AFTER updation
    printf("After:\n");
    printf("Value of var = %d\n", var);

    printf("Value of var using level-1"
           " pointer = %d\n",
           *ptr1);

    printf("Value of var using level-2"
           " pointer = %d\n",
           **ptr2);

    printf("Value of var using level-3"
           " pointer = %d\n",
           ***ptr3);

    return 0;
}
```

## C++

```cpp
// C++ program to illustrate
// levels of pointer
#include <bits/stdc++.h>
using namespace std;

// Driver Code
int main()
{
    // Initializing integer variable
    int var = 10;

    // Declaring pointer variables
    // upto level-3
    int *ptr1, **ptr2, ***ptr3;

    // Iinitializing pointer variables
    ptr1 = &var;
    ptr2 = &ptr1;
    ptr3 = &ptr2;

    // Printing values BEFORE updation
    cout << "Before:" << endl;

    cout << "Value of var is " << var
         << endl;

    cout << "Value of var using level-1"
         << " pointer is "
         << *ptr1 << endl;

    cout << "Value of var using level-2"
         << " pointer is "
         << **ptr2 << endl;

    cout << "Value of var using level-3"
         << " pointer is "
         << ***ptr3 << endl;

    // Updating var's value using
    // level-3 pointer
    ***ptr3 = 35;

    // Printing values AFTER updation
    cout << "After:" << endl;

    cout << "Value of var is " << var
         << endl;

    cout << "Value of var using level-1"
         << " pointer is "
         << *ptr1 << endl;

    cout << "Value of var using level-2"
         << " pointer is "
         << **ptr2 << endl;

    cout << "Value of var using level-3"
         << " pointer is "
         << ***ptr3 << endl;

    return 0;
}
```

**Output:**

```cpp
Before:
Value of var = 10
Value of var using level-1 pointer = 10
Value of var using level-2 pointer = 10
Value of var using level-3 pointer = 10
After:
Value of var = 35
Value of var using level-1 pointer = 35
Value of var using level-2 pointer = 35
Value of var using level-3 pointer = 35

```

**解释:**
正如我们已经知道的，指针指向一个变量的地址位置，所以当我们访问指向该变量值的指针的值时。现在要更新变量的值，我们可以使用任何级别的指针，因为最终每个指针都直接或间接指向该变量。它将直接改变变量地址位置的值。