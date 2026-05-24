# C |字符串|问题 13

> 原文:[https://www.geeksforgeeks.org/c-string-question-13/](https://www.geeksforgeeks.org/c-string-question-13/)

```cpp
int main()
{
    char p[] = "geeksquiz";
    char t;
    int i, j;
    for(i=0,j=strlen(p); i<j; i++)
    {
        t = p[i];
        p[i] = p[j-i];
        p[j-i] = t;
    }
    printf("%s", p);
    return 0;
}
```

输出？
**(A)**
**(B)**屏幕上什么都没有打印
**(C)** 极客 squiz

**(D)**gggggg

**答案:** **(B)**

**解释:**字符串终止字符“\0”被赋给数组 p 的第一个元素【】

[本题竞猜](https://www.geeksforgeeks.org/c-language-2-gq/string-gq/)