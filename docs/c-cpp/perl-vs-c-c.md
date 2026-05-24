# Perl vs C/C++

> 原文:[https://www.geeksforgeeks.org/perl-vs-c-c/](https://www.geeksforgeeks.org/perl-vs-c-c/)

[Perl](https://www.geeksforgeeks.org/introduction-to-perl/) 是一种通用、高级解释的动态编程语言。它是拉里·沃尔在 1987 年开发的。Perl 没有正式的首字母缩略词，但最常用的首字母缩略词是“实用提取和报告语言”。一些程序员也将 Perl 称为“病态的折衷垃圾列表者”或“几乎所有真正讨人喜欢的东西”。首字母缩略词“实用提取和报告语言”被广泛使用，因为 Perl 最初是为文本处理而开发的，比如从指定的文本文件中提取所需的信息，以及将文本文件转换成不同的形式。它支持过程式和面向对象编程。
[C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 是一种通用编程语言，现在广泛用于竞技编程。它具有命令式、面向对象和泛型编程特性。C++ 运行在很多平台上，如视窗、Linux、Unix、Mac 等。
*下面是 Perl 和 c/c++ 的一些主要区别:*

<figure class="table">

| trait | Perl 语言 | C/c++ |
| --- | --- | --- |
| **Driving function (main ())** | There is no need for explicit driver functions in Perl. | C/C++ code needs the main () function to execute, otherwise the code will not compile. |
| **Compilation process** | Perl is an interpretive programming language. | C++ is a general object-oriented programming (OOP) language. |
| **closure** | Perl can use private data unreachable closures as objects. | C/C++ does not support closures, where closures can be considered as functions that can be stored as variables. |
| **File extension** | Perl scripts are saved using. Pl extension. E.g. perlDocument.pl | This. And C. The cpp file extension is used to store C and c++ codes respectively. Examples: myFile.c and myfile.cpp. |
| **brace** | In Perl, you must put braces around the "then" part of the if statement.
ex:
if (condition)
{statement; } | In C/C++, there is no need to enlarge brackets after if and lopps.
ex:
if (conditional)
statement; |
| **String declaration** | Use Perl single quotation marks to declare strings. Use double quotation marks to force the content in the string to be evaluated.
Example: $ x =' geeksforgeeks | C/C++ uses double quotation marks to declare strings.
Example: string s = "geeksforgeeks" |
| **Note** | For inline comments, we use the # sign in Perl.
For example, the comment
in # Inline-Perl | C/C++ Use//for Inline annotation.
For example, the note in//Inline -C/c++.
 |

</figure>

**c++ 和 Perl 中两个数相加的程序**T2】

## C++

```cpp
// C++ program to add two numbers
#include <stdio.h>

// Function to perform addition
// operation
int add(int x, int y)
{
    int res = x + y;
    return res;
}

// Driver Code
int main()
{
    int choice = 3;
    int choice2 = 5;

    int res = add(choice, choice2);
    printf("The result is %d", res);
    return 0;
}
```

## Perl 语言

```cpp
#!/usr/bin/perl

# Perl program to add two numbers
$choice = 3;
$choice2 = 5;
$res = add($choice, $choice2);
print "The result is $res";

# Subroutine to perform
# addition operation
sub add
{
    ($x, $y) = @_;
    $res = $x + $y;
    return $res;
}
```

**输出:**

```cpp
The result is 8
```