# 结构指针

> 原文:[https://www.geeksforgeeks.org/structure-pointer/](https://www.geeksforgeeks.org/structure-pointer/)

[**结构**](https://www.geeksforgeeks.org/structures-c/) [**指针**](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/) **:** 它被定义为指向存储一个[结构的内存块的地址的](https://www.geeksforgeeks.org/structures-c/)[指针](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/)被称为结构指针。下面是同一个例子:
**例子:**

```cpp
struct point
{
   int value;
};

// Driver Code
int main()
{
    struct point s;
    struct point *ptr = &s;
    return 0;
}
```

> 在上面的代码中 **s** 是结构点的一个实例， **ptr** 是结构指针，因为它存储的是结构点的地址。

下面是说明上述概念的程序:

## C

```cpp
// C program to illustrate the
// structure pointer

#include <stdio.h>

// Structure declaration for
// vertices
struct point {
    int x;
    int y;
};

// Structure declaration for
// rectangle
struct rect {

    // An object left is declared
    // with 'point'
    struct point left;

    // An object right is declared
    // with 'point'
    struct point right;
};

// Function to calculate area of
// the given rectangle
void areaOfRectangle(struct rect r)
{
    // Find the area of the rectangle
    // using variables of point
    // structure where variables of
    // point structure is accessed
    // by left and right objects
    int area
        = (r.right.x - r.left.x)
          * (r.right.y - r.left.y);

    // Print the area
    printf("%d", area);
}

// Driver Code
int main()
{
    // Initialize variable 'r'
    // with vertices of rectangle
    struct rect r = { { 0, 0 }, { 1, 1 } };

    // Function Call
    areaOfRectangle(r);

    return 0;
}
```

## C++

```cpp
// C++ program to illustrate the
// structure pointer
#include <iostream>
#include <stdio.h>
using namespace std;

// Structure declaration for
// vertices
struct point {
    int x;
    int y;
};

// Structure declaration for
// rectangle
struct rect {

    // An object left is declared
    // with 'point'
    struct point left;

    // An object right is declared
    // with 'point'
    struct point right;
};

// Function to calculate area of
// the given rectangle
void areaOfRectangle(struct rect r)
{
    // Find the area of the rectangle
    // using variables of point
    // structure where variables of
    // point structure is accessed
    // by left and right objects
    int area
        = (r.right.x - r.left.x)
          * (r.right.y - r.left.y);

    // Print the area
    cout << area;
}

// Driver Code
int main()
{
    // Initialize variable 'r'
    // with vertices of rectangle
    struct rect r = { { 0, 0 }, { 1, 1 } };

    // Function Call
    areaOfRectangle(r);

    return 0;
}
```

**Output:** 

```cpp
1
```