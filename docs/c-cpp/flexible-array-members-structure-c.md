# C

结构中的柔性阵列构件

> 原文:[https://www . geesforgeks . org/flexible-array-members-structure-c/](https://www.geeksforgeeks.org/flexible-array-members-structure-c/)

灵活数组成员(FAM)是 C 编程语言的 C99 标准中引入的一个特性。

*   对于 C99 标准以后的 C 编程语言中的[结构](https://www.geeksforgeeks.org/structures-c/)，我们可以声明一个没有维度的数组**，其大小本质上是灵活的。**
*   结构内部的这种数组最好被声明为结构的最后一个成员**，并且它的大小是可变的(可以在运行时更改)。**
*   **除了灵活数组成员之外，该结构还必须包含至少一个命名成员。**

****下面的结构一定有多大？****

```cpp
struct student
{
   int stud_id;
   int name_len;
   int struct_size;
   char stud_name[];
};
```

```cpp
The size of structure is = 4 + 4 + 4 + **0** = 12
```

**在上面的代码片段中，数组“stud_name”的大小(即长度)不是固定的，而是一个 FAM。**

**对于上面的例子，使用灵活的数组成员(按照 C99 标准)的内存分配可以如下进行:**

```cpp
 struct student *s = malloc( sizeof(*s) + sizeof(char [strlen(stud_name)])  ); 
```

****注意:**在结构中使用柔性数组成员时，定义了一些关于成员实际大小的约定。
在上面的例子中，惯例是成员“stud_name”具有字符大小。**

****例如，考虑以下结构:****

```cpp
Input : id = 15, name = "Kartik" 
Output : Student_id : 15
         Stud_Name  : Kartik
         Name_Length: 6
         **Allocated_Struct_size: 18** 
```

****上述结构的内存分配:****

```cpp
struct student *s = 
        malloc( sizeof(*s) + sizeof(char [strlen("Kartik")])); 
```

**其结构表示等于:**

```cpp
struct student
{
   int stud_id;
   int name_len;
   int struct_size;
   char stud_name[6]; //character array of length 6
};
```

****实施****

```cpp
// C program for variable length members in
// structures in GCC
#include<string.h>
#include<stdio.h>
#include<stdlib.h>

// A structure of type student
struct student
{
    int stud_id;
    int name_len;

    // This is used to store size of flexible
    // character array stud_name[]
    int struct_size;

    // Flexible Array Member(FAM)
    // variable length array must be last
    // member of structure
    char stud_name[];
};

// Memory allocation and initialisation of structure
struct student *createStudent(struct student *s,
                              int id, char a[])
{
    // Allocating memory according to user provided
    // array of characters
    s =
        malloc( sizeof(*s) + sizeof(char) * strlen(a));

    s->stud_id = id;
    s->name_len = strlen(a);
    strcpy(s->stud_name, a);

    // Assigning size according to size of stud_name
    // which is a copy of user provided array a[].
    s->struct_size =
        (sizeof(*s) + sizeof(char) * strlen(s->stud_name));

    return s;
}

// Print student details
void printStudent(struct student *s)
{
    printf("Student_id : %d\n"
           "Stud_Name : %s\n"
           "Name_Length: %d\n"
           "Allocated_Struct_size: %d\n\n",
           s->stud_id, s->stud_name, s->name_len,
           s->struct_size);

    // Value of Allocated_Struct_size is in bytes here
}

// Driver Code
int main()
{
    struct student *s1 = createStudent(s1, 523, "Cherry");
    struct student *s2 = createStudent(s2, 535, "Sanjayulsha");

    printStudent(s1);
    printStudent(s2);

    // Size in struct student
    printf("Size of Struct student: %lu\n",
                    sizeof(struct student));

    // Size in struct pointer
    printf("Size of Struct pointer: %lu",
                              sizeof(s1));

    return 0;
}
```

**输出:**

```cpp
Student_id : 523
Stud_Name : SanjayKanna
Name_Length: 11
Allocated_Struct_size: 23

Student_id : 535
Stud_Name : Cherry
Name_Length: 6
Allocated_Struct_size: 18

Size of Struct student: 12
Size of Struct pointer: 8 
```

****要点:****

1.  **相邻的内存位置用于在内存中存储结构成员。**
2.  **在以前的 C 编程语言标准中，我们能够声明零大小的数组成员来代替灵活的数组成员。C89 标准的 GCC 编译器认为它是零大小数组。**

**本文由海得拉巴 **[JNTUH 工程学院](http://jntuhceh.ac.in/)**Sanjay Kumar Ulsha 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。**

**如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**