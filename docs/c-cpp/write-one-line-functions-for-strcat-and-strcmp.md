# 为 strcat()和 strcmp()

编写一行函数

> 原文:[https://www . geesforgeks . org/write-one-line-functions-for-strcat-and-strcmp/](https://www.geeksforgeeks.org/write-one-line-functions-for-strcat-and-strcmp/)

递归可以用来在一行中完成两个任务。下面是 stracat()和 strcmp()的单行实现。

```cpp
/* my_strcat(dest, src) copies data of src to dest.  To do so, it first reaches end of the string dest using recursive calls my_strcat(++ dest, src).  Once end of dest is reached, data is copied using 
(*dest++ = *src++)?  my_strcat(dest, src). */
void my_strcat(char *dest, char *src)
{
  (*dest)? my_strcat(++ dest, src): (*dest++ = *src++)? my_strcat(dest, src): 0 ;
}

/* driver function to test above function */
int main()
{
  char dest[100] = "geeksfor";
  char *src = "geeks";
  my_strcat(dest, src);
  printf(" %s ", dest);
  getchar();
}    
```

函数 my_strcmp()与 my_strcmp()相比很简单。

```cpp
/* my_strcmp(a, b) returns 0 if strings a and b are same, otherwise 1.   It recursively increases a and b pointers. At any point if *a is not equal to *b then 1 is returned.  If we reach end of both strings at the same time then 0 is returned. */
int my_strcmp(char *a, char *b)
{
  return (*a == *b && *b == '\0')? 0 : (*a == *b)? my_strcmp(++ a, ++ b): 1;
} 

/* driver function to test above function */
int main()
{
  char *a = "geeksforgeeks";
  char *b = "geeksforgeeks";
  if(my_strcmp(a, b) == 0)
     printf(" String are same ");
  else  
     printf(" String are not same ");  

  getchar();
  return 0;
}    
```

上述函数进行非常基本的字符串连接和字符串比较。这些函数不提供与标准库函数相同的功能。

如果你发现上面的代码不正确，请写评论，或者找到更好的方法来解决同样的问题。