# C |数组|问题 6

> 原文:[https://www.geeksforgeeks.org/c-arrays-question-6/](https://www.geeksforgeeks.org/c-arrays-question-6/)

假设下面的 C 变量声明

```cpp
int *A [10], B[10][10];  
```

下列表达式中
I A[2]
II A[2][3]
III B[1]
IV B[2][3]
如果用作 C 程序(GATE CS 2003)中赋值语句的左侧，不会产生编译时错误？

**(甲)**仅一、二、四
**(乙)**仅二、三、四

**(C)** II、IV 仅
**(D)** IV 仅

**答案:** **(A)**

**解释:**详见下文解释。

```cpp
int main() 
{ 
  int *A[10], B[10][10]; 
  int C[] = {12, 11, 13, 14}; 

  /* No problem with below statement as A[2] is a pointer 
     and we are assigning a value to pointer */
  A[2] = C;  

  /* No problem with below statement also as array style indexing 
      can be done with pointers*/
  A[2][3] = 15; 

  /* Simple assignment to an element of a 2D array*/
  B[2][3]  = 15; 

  printf("%d %d", A[2][0], A[2][3]); 
  return 0;
}
```

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)