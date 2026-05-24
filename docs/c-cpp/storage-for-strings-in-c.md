# 字符串在 C 中的存储

> 原文:[https://www.geeksforgeeks.org/storage-for-strings-in-c/](https://www.geeksforgeeks.org/storage-for-strings-in-c/)

在 C 语言中，可以使用字符指针或字符数组来引用字符串。
**字符串作为字符数组**

## C

```cpp
char str[4] = "GfG"; /*One extra for string terminator*/
/*    OR    */
char str[4] = {‘G’, ‘f’, ‘G’, '\0'}; /* '\0' is string terminator */
```

当字符串被声明为字符数组时，它们像其他类型的数组一样存储在 c 中。例如，如果 str[]是一个[自动变量](http://icecube.wisc.edu/~dglo/c_class/vstorage.html)，那么字符串存储在堆栈段中，如果它是一个全局或静态变量，那么存储在[数据段](http://en.wikipedia.org/wiki/Data_segment)中，等等。

**使用字符指针的字符串**
使用字符指针的字符串可以通过两种方式存储:

**1)** 共享段中的只读字符串。
在大多数编译器中，当一个字符串值被直接赋给一个指针时，它被存储在一个只读块中(通常在数据段中)，该块在函数之间共享。

## C

```cpp
char *str  =  "GfG";  
```

在上一行中，“GfG”存储在共享只读位置，但指针字符串存储在读写存储器中。您可以更改字符串以指向其他内容，但不能更改当前字符串的值。所以这种字符串应该只在程序后期不想修改字符串的时候使用。

**2)** 在堆段中动态分配。

字符串像其他动态分配的东西一样存储在 C 语言中，可以在函数之间共享。

## C

```cpp
char *str;
int size = 4; /*one extra for ‘\0’*/
str = (char *)malloc(sizeof(char)*size);
*(str+0) = 'G'; 
*(str+1) = 'f';  
*(str+2) = 'G';  
*(str+3) = '\0';  
```

让我们看一些例子来更好地理解上述存储字符串的方法。

**示例 1(尝试修改字符串)**
下面的程序可能会崩溃(给出分段错误错误)，因为行*(str+1) = 'n '试图写入只读内存。

## C

```cpp
int main()
{
 char *str; 
 str = "GfG";     /* Stored in read only part of data segment */
 *(str+1) = 'n'; /* Problem:  trying to modify read only memory */
 getchar();
 return 0;
}
```

由于 str[]存储在可写堆栈段中，下面的程序运行得非常好。

## C

```cpp
int main()
{
 char str[] = "GfG";  /* Stored in stack segment like other auto variables */
 *(str+1) = 'n';   /* No problem: String is now GnG */
 getchar();
 return 0;
}
```

由于 str 处的数据存储在可写堆段中，下面的程序也能很好地工作。

## C

```cpp
int main()
{
  int size = 4;

  /* Stored in heap segment like other dynamically allocated things */
  char *str = (char *)malloc(sizeof(char)*size);
  *(str+0) = 'G'; 
  *(str+1) = 'f';  
  *(str+2) = 'G';    
  *(str+3) = '\0';  
  *(str+1) = 'n';  /* No problem: String is now GnG */
   getchar();
   return 0;
}     
```

**示例 2(尝试从函数中返回字符串)**
下面的程序运行得非常好，因为字符串存储在共享段中，即使在返回 getString()之后，存储的数据仍然保留在那里

## C

```cpp
char *getString()
{
  char *str = "GfG"; /* Stored in read only part of shared segment */

  /* No problem: remains at address str after getString() returns*/
  return str;  
}     

int main()
{
  printf("%s", getString());  
  getchar();
  return 0;
}
```

由于字符串存储在堆段中，并且即使在返回 getString()之后，存储在堆段中的数据仍然存在，因此下面的程序也可以很好地工作

## C

```cpp
char *getString()
{
  int size = 4;
  char *str = (char *)malloc(sizeof(char)*size); /*Stored in heap segment*/
  *(str+0) = 'G'; 
  *(str+1) = 'f';  
  *(str+2) = 'G';
  *(str+3) = '\0';  

  /* No problem: string remains at str after getString() returns */    
  return str;  
}     
int main()
{
  printf("%s", getString());  
  getchar();
  return 0;
}
```

但是，下面的程序可能会打印一些垃圾数据，因为字符串存储在函数 getString()的堆栈框架中，并且在 getString()返回后数据可能不在那里。

## C

```cpp
char *getString()
{
  char str[] = "GfG"; /* Stored in stack segment */

  /* Problem: string may not be present after getString() returns */
  /* Problem can be solved if write static before char, i.e. static char str[] = "GfG";*/
  return str; 
}     
int main()
{
  printf("%s", getString());  
  getchar();
  return 0;
}
```

如果你在上面的文章中发现任何不正确的地方，请写评论，或者你想分享更多关于字符串存储的信息