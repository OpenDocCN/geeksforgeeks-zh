# Perl | 删除前导和尾随空格（修剪）

> 原文：[https://www.geeksforgeeks.org/perl-removing-leading-and-trailing-white-spaces-trim/](https://www.geeksforgeeks.org/perl-removing-leading-and-trailing-white-spaces-trim/)

从字符串中删除不需要的空格可用于仅存储所需的数据和删除不必要的尾随空格。这可以使用 Perl 中的 `trim` 函数来完成。`trim` 函数使用正则表达式来移除空格。它不是库函数，而是由用户在需要时定义的。修剪函数的类型有：

## 修剪类型

*   **左修剪（`~ s/^\s+//`）**：从字符串最左侧开始移除多余的空格，直到实际文本开始。从最左侧开始，字符串包含一个或多个空格（`\s+`），并且不替换任何内容。
*   **右修剪（`~ s/\s+$/`）**：从字符串最右侧开始移除多余的空格，直到实际文本结束。从最右侧开始，字符串包含一个或多个空格（`\s+`），并且不替换任何内容。
*   **修剪（`~ s/^\s+|\s+$//`）**：移除字符串两侧的多余空格。

## 示例

以下代码演示了 Perl 中的左修剪、右修剪和修剪：

```perl
# Perl program for removing leading and
# trailing white spaces using trim

#!/usr/bin/perl

# Original String
$str1 = "     Geeks----";

print "The Original String is:\n";
print "${str1}\n\n";

# Applying left trim to str1
print "After Lefttrim Str1:\n";
$str1 =~ s/^\s+//;
print "${str1}\n\n";

# again initializing the 
# value to string
$str1 = "----Geeks     ";

# Applying right trim to str1
print "After Righttrim Str1:\n";
$str1 =~ s/\s+$//;
print "${str1}\n\n";

# again initializing the 
# value to strings
$str1="      Geeks      ";

# Applying trim to str1
print "After trim Str1:\n";
$str1 =~ s/^\s+|\s+$//g;
print "${str1}\n";
```

**输出：**

```perl
The Original String is:
     Geeks----

After Lefttrim Str1:
Geeks----

After Righttrim Str1:
----Geeks

After trim Str1:
Geeks
```