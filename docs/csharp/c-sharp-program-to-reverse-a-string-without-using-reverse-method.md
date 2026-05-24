# C# 程序不使用 Reverse()方法反转字符串

> 原文:[https://www . geeksforgeeks . org/c-sharp-program-to-reverse-a-string-not-use-reverse-method/](https://www.geeksforgeeks.org/c-sharp-program-to-reverse-a-string-without-using-reverse-method/)

C# 有一个反转字符串的内置函数。首先，使用 ToCharArray()将字符串转换为字符数组，然后使用 Reverse()将字符数组反转，但是在本文中，我们将了解如何在不使用 Reverse()的情况下反转字符串。

**例**T0】

**方法 1:使用 for 循环反转字符串。**

声明一个空字符串，并将其命名为 ReversedString。输入字符串将从右向左迭代，每个字符都被附加到反转字符串中。迭代结束时，ReversedString 将存储反向字符串。

## c#

T0】**输出**

```cs
skeeGroFskeeG
```