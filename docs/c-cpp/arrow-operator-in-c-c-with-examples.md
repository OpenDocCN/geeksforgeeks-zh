# 箭头运算符- >用 C/C++ 举例

> 原文:[https://www . geesforgeks . org/arrow-operator-in-c-c-with-examples/](https://www.geeksforgeeks.org/arrow-operator-in-c-c-with-examples/)

C/C++ 中的**箭头操作符允许访问[结构](https://www.geeksforgeeks.org/structures-in-cpp/)和[联合](https://www.geeksforgeeks.org/union-c/)中的元素。它与指向结构或联合的[指针变量一起使用。箭头运算符由减号和大于号组成，如下所示。
**语法:**](https://www.geeksforgeeks.org/self-referential-structures/)**

```cpp
(pointer_name)->(variable_name)
```

**操作:**C 或 C++ 中的- >运算符将变量 _name 持有的值赋予结构或联合变量指针 _name。
T3】点(。)和箭头(- >)操作符:

*   点(。)运算符通常用于访问结构或联合的成员。
*   Arrow(->)运算符用于使用指针访问结构或联合的成员。

**示例:**

*   **结构中的箭头运算符:**

## C++

```cpp
// C++ program to show Arrow operator
// used in structure
#include <iostream>
using namespace std;

// Creating the structure
struct student {
    char name[80];
    int age;
    float percentage;
};

// Creating the structure object
struct student* emp = NULL;

// Driver code
int main()
{

    // Assigning memory to struct variable emp
    emp = (struct student*)
        malloc(sizeof(struct student));

    // Assigning value to age variable
    // of emp using arrow operator
    emp->age = 18;

    // Printing the assigned value to the variable
    cout <<" "<< emp->age;

    return 0;
}

// This code is contributed by shivanisinghss2110
```

## C

```cpp
// C program to show Arrow operator
// used in structure

#include <stdio.h>
#include <stdlib.h>

// Creating the structure
struct student {
    char name[80];
    int age;
    float percentage;
};

// Creating the structure object
struct student* emp = NULL;

// Driver code
int main()
{
    // Assigning memory to struct variable emp
    emp = (struct student*)
        malloc(sizeof(struct student));

    // Assigning value to age variable
    // of emp using arrow operator
    emp->age = 18;

    // Printing the assigned value to the variable
    printf("%d", emp->age);

    return 0;
}
```

**Output:** 

```cpp
18
```

*   **联合中的箭头运算符:**

## C++

```cpp
// C++ program to show Arrow operator
// used in structure
#include <iostream>
using namespace std;

// Creating the union
union student {
    char name[80];
    int age;
    float percentage;
};

// Creating the union object
union student* emp = NULL;

// Driver code
int main()
{
    // Assigning memory to struct variable emp
    emp = (union student*)
        malloc(sizeof(union student));

    // Assigning value to age variable
    // of emp using arrow operator
    emp->age = 18;

    // DIsplaying the assigned value to the variable
    cout <<""<< emp->age;
}

// This code is contributed by shivanisinghss2110
```

## C

```cpp
// C program to show Arrow operator
// used in structure

#include <stdio.h>
#include <stdlib.h>

// Creating the union
union student {
    char name[80];
    int age;
    float percentage;
};

// Creating the union object
union student* emp = NULL;

// Driver code
int main()
{
    // Assigning memory to struct variable emp
    emp = (union student*)
        malloc(sizeof(union student));

    // Assigning value to age variable
    // of emp using arrow operator
    emp->age = 18;

    // DIsplaying the assigned value to the variable
    printf("%d", emp->age);
}
```

**Output:** 

```cpp
18
```