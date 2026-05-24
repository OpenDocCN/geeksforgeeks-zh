# C 小测验–109 |问题 1

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-109-question-1/](https://www.geeksforgeeks.org/c-c-quiz-109-question-1/)

在下面的程序片段中，s1 和 s2 都是如下定义的结构类型的变量，不会有任何编译问题。

```cpp
typedef struct Student
{
 int rollno;
 int total;
} Student;

Student s1;
struct Student s2;
```

**(A)** 真
**(B)** 假

**答案:** **(A)**

**解释:**起初，似乎拥有相同的‘struct tag name’和‘typedef name’会在这里引起问题。但他们俩同名完全没问题。s1 是使用 typedef 名称 Student 定义的，而 s2 是使用结构标记名称 Student 定义的。

[本题小考](https://www.geeksforgeeks.org/c-quiz-109-gq/)