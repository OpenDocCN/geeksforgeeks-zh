# C++ 程序检查字符串是否相互旋转

> 原文：[https://www.geeksforgeeks.org/cpp-program-to-check-if-strings-are-rotations-of-each-other-or-not/](https://www.geeksforgeeks.org/cpp-program-to-check-if-strings-are-rotations-of-each-other-or-not/)

给定一个字符串 `s1` 和一个字符串 `s2`，写一个片段来说明 `s2` 是否是 `s1` 的旋转？
(如给定 `s1 = ABCD`，`s2 = CDAB`，返回真，给定 `s1 = ABCD`，`s2 = ACBD`，返回假)

## 算法：`rotate(str1, str2)`

1.  创建一个临时字符串 `temp`，并将 `str1` 与自身连接的结果存储在 `temp` 中。
    `temp = str1 + str1`
2.  如果 `str2` 是 `temp` 的子字符串，那么 `str1` 和 `str2` 就是彼此的旋转。

示例：
`str1 = "ABACD"`
`str2 = "CDABA"`
`temp = str1 + str1 = "ABACDABACD"`
由于 `str2` 是 `temp` 的子字符串，所以 `str1` 和 `str2` 是彼此的旋转。

## C++ 实现

```cpp
// C++ program to check if two given strings
// are rotations of each other
# include <bits/stdc++.h>
using namespace std;

/* Function checks if passed strings (str1
   and str2) are rotations of each other */
bool areRotations(string str1, string str2)
{
   /* Check if sizes of two strings are same */
   if (str1.length() != str2.length())
        return false;

   string temp = str1 + str1;
   return (temp.find(str2) != string::npos);
}

/* Driver program to test areRotations */
int main()
{
   string str1 = "AACD", str2 = "ACDA";
   if (areRotations(str1, str2))
      printf("Strings are rotations of each other");
   else
      printf("Strings are not rotations of each other");
   return 0;
}
```

**输出：**

```cpp
Strings are rotations of each other
```

## 使用的库函数

`strstr`：
`strstr` 在字符串中查找子字符串。
原型：`char *strstr(const char *S1, const char *S2);`
见 [http://www.lix.polytechnique.fr/Labo/Leo.Liberti/public/computing/prog/c/C/MAN/strstr.htm](http://www.lix.polytechnique.fr/Labo/Leo.Liberti/public/computing/prog/c/C/MAN/strstr.htm) 了解更多详情。

`strcat`：
`strcat` 串联两个字符串。
原型：`char *strcat(char *dest, const char *src);`
见 [http://www.lix.polytechnique.fr/Labo/Leo.Liberti/public/computing/prog/c/C/MAN/strcat.htm](http://www.lix.polytechnique.fr/Labo/Leo.Liberti/public/computing/prog/c/C/MAN/strcat.htm) 了解更多详情。

## 时间复杂度

这个问题的时间复杂度取决于 `strstr` 函数的实现。
如果使用 KMP 匹配器实现 `strstr`，那么上述程序的复杂度为 `O(n1 + n2)`，其中 `n1` 和 `n2` 是字符串的长度。KMP 匹配器花费 `O(n)` 时间在长度为 `n` 的字符串中找到子字符串，其中假设子字符串的长度小于该字符串。

详情请参考 [A program to check if strings are rotations of each other](https://www.geeksforgeeks.org/a-program-to-check-if-strings-are-rotations-of-each-other/) 的完整文章！