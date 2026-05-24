# 将学生记录存储为结构并按名称排序的程序

> 原文:[https://www . geesforgeks . org/c-程序到商店-学生-记录-结构-按名称排序/](https://www.geeksforgeeks.org/c-program-to-store-student-records-as-structures-and-sort-them-by-name/)

给定学生的记录，每条记录包含学生的 id、姓名和年龄。编写一个 C 程序来读取这些记录，并按名称的排序顺序显示它们。

**例:**

```cpp
Input: Student Records= {
{Id = 1, Name = bd, Age = 12 },
{Id = 2, Name = ba, Age = 10 },
{Id = 3, Name = bc, Age = 8 },
{Id = 4, Name = aaz, Age = 9 },
{Id = 5, Name = az, Age = 10 } }

Output:
{{Id = 4, Name = aaz, Age = 9 },
{Id = 5, Name = az, Age = 10 },
{Id = 2, Name = ba, Age = 10 },
{Id = 3, Name = bc, Age = 8 },
{Id = 1, Name = bd, Age = 12 } }

```

**方法:**这个问题通过以下步骤解决:

*   Create a structure with field id, name and age.
*   Reading structure
*   Students' records in, the comparator is defined by setting comparison rules. Here, the names can be sorted by the [strcmp ()](https://www.geeksforgeeks.org/strcmp-in-c-cpp/) method.
*   Now, with the help of [qsort ()](https://www.geeksforgeeks.org/comparator-function-of-qsort-in-c/) method, the structures are sorted according to the defined comparators.
*   Printed student records.

**程序:**

```cpp
// C program to read Student records
// like id, name and age,
// and display them in sorted order by Name

#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// struct person with 3 fields
struct Student {
    char* name;
    int id;
    char age;
};

// setting up rules for comparison
// to sort the students based on names
int comparator(const void* p, const void* q)
{
    return strcmp(((struct Student*)p)->name,
                  ((struct Student*)q)->name);
}

// Driver program
int main()
{
    int i = 0, n = 5;

    struct Student arr[n];

    // Get the students data
    arr[0].id = 1;
    arr[0].name = "bd";
    arr[0].age = 12;

    arr[1].id = 2;
    arr[1].name = "ba";
    arr[1].age = 10;

    arr[2].id = 3;
    arr[2].name = "bc";
    arr[2].age = 8;

    arr[3].id = 4;
    arr[3].name = "aaz";
    arr[3].age = 9;

    arr[4].id = 5;
    arr[4].name = "az";
    arr[4].age = 10;

    // Print the Unsorted Structure
    printf("Unsorted Student Records:\n");
    for (i = 0; i < n; i++) {
        printf("Id = %d, Name = %s, Age = %d \n",
               arr[i].id, arr[i].name, arr[i].age);
    }
    // Sort the structure
    // based on the specified comparator
    qsort(arr, n, sizeof(struct Student), comparator);

    // Print the Sorted Structure
    printf("\n\nStudent Records sorted by Name:\n");
    for (i = 0; i < n; i++) {
        printf("Id = %d, Name = %s, Age = %d \n",
               arr[i].id, arr[i].name, arr[i].age);
    }

    return 0;
}
```

**输出:**

```cpp
Unsorted Student Records:
Id = 1, Name = bd, Age = 12 
Id = 2, Name = ba, Age = 10 
Id = 3, Name = bc, Age = 8 
Id = 4, Name = aaz, Age = 9 
Id = 5, Name = az, Age = 10 

Student Records sorted by Name:
Id = 4, Name = aaz, Age = 9 
Id = 5, Name = az, Age = 10 
Id = 2, Name = ba, Age = 10 
Id = 3, Name = bc, Age = 8 
Id = 1, Name = bd, Age = 12

```

**注**:结构可以根据**任意字段**排序，基于比较器函数中定义的规则。了解更多比较器功能。参见 C 中 qsort()的[比较器功能](https://www.geeksforgeeks.org/comparator-function-of-qsort-in-c/)