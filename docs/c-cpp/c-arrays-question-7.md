# C |数组|问题 7

> 原文:[https://www.geeksforgeeks.org/c-arrays-question-7/](https://www.geeksforgeeks.org/c-arrays-question-7/)

考虑以下 C 语言中“二维数组”的声明:

```cpp
char a[100][100]; 
```

假设主存储器是字节可寻址的，并且阵列是从存储器地址 0 开始存储的，则[40][50]的地址是(GATE CS 2002)

**(A)**4040
**(B)**4050
**(C)**5040
**(D)**5050

**回答:****(B)**

**说明:**

```cpp
Address of a[40][50] = Base address + 40*100*element_size + 50*element_size
                      = 0 + 4000*1 + 50*1
                     = 4050
```

```cpp
Based on row major or column major
if row major then the result will be 4050
if column major then 
            Address of a[40][50] = Base address + 50*100*element_size + 40*element_size
                      = 0 + 5000*1 + 40*1
                     = 5040
```

[本题小考](https://www.geeksforgeeks.org/c-language-2-gq/arrays-pointers-gq/)