# 程序打印最后 10 行

> 原文:[https://www . geesforgeks . org/print-最后 10 行给定文件/](https://www.geeksforgeeks.org/print-last-10-lines-of-a-given-file/)

给定一个字符串中的一些文本行，每行由“\n”字符分隔。打印最后十行。如果行数小于 10，则打印所有行。

来源:[微软访谈|第 10 集](https://www.geeksforgeeks.org/microsoft-interview-set-10/)

以下是步骤
**1)** 查找 DELIM 或“\n”
**的最后一次出现 2)** 将目标位置初始化为“\n”的最后一次出现并计数为 0，并在计数的同时执行以下操作< 10
…… **2.a)** 查找“\ n”的下一个实例并更新目标位置
….. **2.b)** 跳过“\n”并增加“\n”的计数，更新目标位置
**3)** 从目标位置打印子字符串。

## C++

```cpp
// C++ Program to print the last 10 lines. 
// If number of lines is less than 10,
// then print all lines. 
#include <bits/stdc++.h>
using namespace std; 
#define DELIM '\n' 

/* Function to print last n lines of a given string */
void print_last_lines(char *str, int n) 
{ 
    /* Base case */
    if (n <= 0) 
    return; 

    size_t cnt = 0; // To store count of '\n' or DELIM 
    char *target_pos = NULL; // To store the output position in str 

    /* Step 1: Find the last occurrence of DELIM or '\n' */
    target_pos = strrchr(str, DELIM); 

    /* Error if '\n' is not present at all */
    if (target_pos == NULL) 
    { 
        cout << "ERROR: string doesn't contain '\\n' character\n"; 
        return; 
    } 

    /* Step 2: Find the target position from
       where we need to print the string */
    while (cnt < n) 
    { 
        // Step 2.a: Find the next instance of '\n' 
        while (str < target_pos && *target_pos != DELIM) 
            --target_pos; 

        /* Step 2.b: skip '\n' and increment count of '\n' */
        if (*target_pos == DELIM) 
            --target_pos, ++ cnt; 

        /* str < target_pos means str has 
        less than 10 '\n' characters, so break from loop */
        else
            break; 
    } 

    /* In while loop, target_pos is decremented 2 times, 
    that's why target_pos + 2 */
    if (str < target_pos) 
        target_pos += 2; 

    // Step 3: Print the string from target_pos 
    cout << target_pos << endl; 
} 

// Driver Code
int main(void) 
{ 
    char *str1 ="str1\nstr2\nstr3\nstr4\nstr5\nstr6\nstr7\nstr8\nstr9"
                "\nstr10\nstr11\nstr12\nstr13\nstr14\nstr15\nstr16\nstr17"
                "\nstr18\nstr19\nstr20\nstr21\nstr22\nstr23\nstr24\nstr25"; 
    char *str2 ="str1\nstr2\nstr3\nstr4\nstr5\nstr6\nstr7"; 
    char *str3 ="\n"; 
    char *str4 = ""; 

    print_last_lines(str1, 10); 
    cout << "-----------------\n"; 

    print_last_lines(str2, 10); 
    cout << "-----------------\n";

    print_last_lines(str3, 10); 
    cout << "-----------------\n";; 

    print_last_lines(str4, 10); 
    cout << "-----------------\n";

    return 0; 
} 

// This is code is contributed by rathbhupendra
```

## C

```cpp
/* Program to print the last 10 lines. If number of lines is less
   than 10, then print all lines. */

#include <stdio.h>
#include <string.h>
#define DELIM   '\n'

/* Function to print last n lines of a given string */
void print_last_lines(char *str, int n)
{
    /* Base case */
    if (n <= 0)
       return;

    size_t cnt  = 0; // To store count of '\n' or DELIM
    char *target_pos   = NULL; // To store the output position in str

    /* Step 1: Find the last occurrence of DELIM or '\n' */
    target_pos = strrchr(str, DELIM);

    /* Error if '\n' is not present at all */
    if (target_pos == NULL)
    {
        fprintf(stderr, "ERROR: string doesn't contain '\\n' character\n");
        return;
    }

    /* Step 2: Find the target position from where we need to print the string */
    while (cnt < n)
    {
        // Step 2.a: Find the next instance of '\n'
        while (str < target_pos && *target_pos != DELIM)
            --target_pos;

         /* Step 2.b: skip '\n' and increment count of '\n' */
        if (*target_pos ==  DELIM)
            --target_pos, ++ cnt;

        /* str < target_pos means str has less than 10 '\n' characters,
           so break from loop */
        else
            break;
    }

    /* In while loop, target_pos is decremented 2 times, that's why target_pos + 2 */
    if (str < target_pos)
        target_pos += 2;

    // Step 3: Print the string from target_pos
    printf("%s\n", target_pos);
}

// Driver program to test above function
int main(void)
{
    char *str1 = "str1\nstr2\nstr3\nstr4\nstr5\nstr6\nstr7\nstr8\nstr9"
                 "\nstr10\nstr11\nstr12\nstr13\nstr14\nstr15\nstr16\nstr17"
                 "\nstr18\nstr19\nstr20\nstr21\nstr22\nstr23\nstr24\nstr25";
    char *str2 = "str1\nstr2\nstr3\nstr4\nstr5\nstr6\nstr7";
    char *str3 = "\n";
    char *str4 = "";

    print_last_lines(str1, 10);
    printf("-----------------\n");

    print_last_lines(str2, 10);
    printf("-----------------\n");

    print_last_lines(str3, 10);
    printf("-----------------\n");

    print_last_lines(str4, 10);
    printf("-----------------\n");

    return 0;
}
```

输出:

```cpp
str16
str17
str18
str19
str20
str21
str22
str23
str24
str25
-----------------
str1
str2
str3
str4
str5
str6
str7
-----------------

-----------------
ERROR: string doesn't contain '\n' character
-----------------
```

**注意:**以上程序可以修改为通过传递 N 而不是 10 来打印最后 N 行。n 可以存储任何整数值。
本文由**纳伦德拉·康拉尔卡尔**整理。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。