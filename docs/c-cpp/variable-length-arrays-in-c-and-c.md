# C 和 C++ 中的可变长度数组

> 原文:[https://www . geesforgeks . org/可变长度数组 in-c-and-c/](https://www.geeksforgeeks.org/variable-length-arrays-in-c-and-c/)

可变长度数组是我们可以分配可变大小的自动数组(在堆栈上)的一个特性。c 支持 C99 标准的可变大小数组。例如，下面的程序在 c 语言中编译并运行良好。

还要注意的是在 [C99](https://en.wikipedia.org/wiki/C99) 或 [C11](https://en.wikipedia.org/wiki/C11_(C_standard_revision)) 标准中，有一个名为[“柔性阵元”](https://en.wikipedia.org/wiki/Flexible_array_member)的特性，其工作原理同上。

```cpp
void fun(int n)
{
  int arr[n];
  // ......
} 
int main()
{
   fun(6);
}
```

但是 C++ 标准(直到 [C++ 11](https://en.wikipedia.org/wiki/C%2B%2B11) )不支持可变大小数组。C++ 11 标准提到数组大小是一个常量表达式参见(参见 [N3337](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3337.pdf) 第 179 页的 8.3.4)。所以上面的程序可能不是有效的 C++ 程序。程序可能在 GCC 编译器中工作，因为 GCC 编译器提供了一个扩展来支持它们。

顺便提一下，最新的 [C++ 14](https://en.wikipedia.org/wiki/C%2B%2B14) (参见 [N3690](https://isocpp.org/files/papers/N3690.pdf) 第 184 页 8.3.4)提到数组大小是一个简单的表达式(不是常量表达式)。

**实施**

```cpp
//C program for variable length members in structures in GCC before C99.
#include<string.h>
#include<stdio.h>
#include<stdlib.h>

//A structure of type student
struct student
{
   int stud_id;
   int name_len;
   int struct_size;
   char stud_name[0]; //variable length array must be last.
};

//Memory allocation and initialisation of structure
struct student *createStudent(struct student *s, int id, char a[])
{
    s = malloc( sizeof(*s) + sizeof(char) * strlen(a) );

    s->stud_id = id;
    s->name_len = strlen(a);
    strcpy(s->stud_name, a);

    s->struct_size = ( sizeof(*s) + sizeof(char) * strlen(s->stud_name) );

    return s;    
}

// Print student details
void printStudent(struct student *s)
{
  printf("Student_id : %d\n"
         "Stud_Name  : %s\n"
         "Name_Length: %d\n"
         "Allocated_Struct_size: %d\n\n",
          s->stud_id, s->stud_name, s->name_len, s->struct_size); 

        //Value of Allocated_Struct_size here is in bytes.
}

//Driver Code
int main()
{
    struct student *s1, *s2;

    s1=createStudent(s1, 523, "Sanjayulsha");
    s2=createStudent(s2, 535, "Cherry");

    printStudent(s1);
    printStudent(s2);

    //size in bytes
    printf("Size of Struct student: %lu\n", sizeof(struct student));
    //size in bytes
    printf("Size of Struct pointer: %lu", sizeof(s1));

    return 0;
}
```

输出:

```cpp
Student_id : 523
Stud_Name : Sanjayulsha
Name_Length: 11
Allocated_Struct_size: 23 

Student_id : 535
Stud_Name : Cherry
Name_Length: 6
Allocated_Struct_size: 18

Size of Struct student: 12
Size of Struct pointer: 8

```

**参考文献:**
[http://stackoverflow . com/questions/1887097/变长数组 c](http://stackoverflow.com/questions/1887097/variable-length-arrays-in-c)
[https://gcc.gnu.org/onlinedocs/gcc/Variable-Length.html](https://gcc.gnu.org/onlinedocs/gcc/Variable-Length.html)

本文由**阿沛·拉提****桑杰·卡纳**供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论