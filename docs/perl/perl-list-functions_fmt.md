# Perl 列表函数

> 原文: [https://www.geeksforgeeks.org/perl-list-functions/](https://www.geeksforgeeks.org/perl-list-functions/)

Perl 中的列表是标量值的集合。我们可以使用索引访问列表的元素。索引以 0 开始（第 0 个索引指列表的第一个元素）。我们使用括号和逗号运算符来构造一个列表。在 Perl 中，标量变量以 `$` 符号开始，而列表变量以 `@` 符号开始。

列表提供了各种预定义的功能，可以轻松执行操作。其中一些功能如下：

## `join()` 函数

`join()` 函数用于将列表的元素组合成一个字符串，并使用提供的分隔符来分隔每个元素。此函数返回连接后的字符串。分隔符只能在元素对之间工作，不能放置在字符串的任一端。为了在没有分隔符的情况下连接字符串，需要向函数传递一个空参数。

> **语法:** `join(分隔符, 列表)`
>
> **参数:**
> *   **分隔符:** 用于在连接时分隔每个元素。
> *   **列表:** 要转换为单个字符串的列表。
>
> **返回:** 一个连接字符串。

**示例:**

```perl
#!/usr/bin/perl

# Initializing list with alphabets A to Z
@list = (A..Z);

# Printing the original list
print "List: @list\n";

# Using join function introducing
# hyphen between each alphabets
print "\nString after join operation:\n";
print join("-", @list);
```

**输出:**

```
List: A B C D E F G H I J K L M N O P Q R S T U V W X Y Z

String after join operation:
A-B-C-D-E-F-G-H-I-J-K-L-M-N-O-P-Q-R-S-T-U-V-W-X-Y-Z
```

## `reverse()` 函数

Perl 中的 `reverse()` 函数在列表上下文中以相反的顺序返回列表的元素。而在标量上下文中，它返回列表值的连接字符串，所有字符顺序相反。它在标量上下文中返回字符串，在列表上下文中返回列表。

> **语法:** `reverse(列表)`
>
> **参数:**
> *   **列表:** 待反转的列表。
>
> **返回:** 以相反顺序排列的元素。

**示例:**

```perl
# Initializing a list
@list = ("Raj", "E123", 12000);

# Reversing the list
@rname = reverse(@list);

# Printing the reversed list
print "Reversed list is @rname";

# Initializing a scalar
$string = "GeeksforGeeks";

# Reversing a scalar
$r = reverse($string);
print "\nReversed string is $r";
```

**输出:**

```
Reversed list is 12000 E123 Raj
Reversed string is skeeGrofskeeG
```

## `map()` 函数

Perl 中的 `map()` 函数对列表的每个元素计算作为参数提供的操作符。在每次迭代中，`$_` 保存当前元素的值，也可以被赋值以允许更新元素的值。`map()` 函数对数组的每个元素运行一个表达式，并返回一个包含更新结果的新数组。它在标量上下文中返回生成的元素总数，在列表上下文中返回值列表。

> **语法:** `map(操作, 列表)`
>
> **参数:**
> *   **操作:** 对列表元素执行的操作。
> *   **列表:** 需要更改其元素的列表。

**示例:**

```perl
# Initializing a list
@Dept = ('comp', 'inft', 'extc', 'mech');

# Converting first character capital
@upd1 = map(ucfirst, @Dept);

# Printing list
print "List with First char capital: ";
foreach $i (@upd1)
{
   print "$i, ";
}

# Converting all characters capital
@upd2 = map(uc, @Dept);

# Printing list
print "\nList with all char capital: ";
foreach $i (@upd2)
{
   print "$i, ";
}
```

**输出:**

```
List with First char capital: Comp, Inft, Extc, Mech, 
List with all char capital: COMP, INFT, EXTC, MECH, 
```

## `sort()` 函数

Perl 中的 `sort()` 函数用于根据指定给函数的排序条件来排列列表。如果未指定条件，则它按正常的字母顺序排序。如果指定了条件，则函数根据该条件对列表进行排序。

> **语法:** `sort(条件, 列表)`

**示例:**

```perl
# Initializing two lists
@country = ('India', 'Qatar', 'Bangladesh', 'France', 'Italy');
@capital = ('Delhi', 'Lahore', 'Dhaka', 'Paris', 'Rome');

# Printing countries in sorted order
print"Countries in sorted order: \n";
print sort @country;
print "\n";

# Printing sorted country and capital values
print "\nCombining both the lists in sorted order:\n";
print sort @country, @capital;
print "\n";

# Initializing a list with number
@list = (19, 4, 54, 33, 99, 2);

# Sorting in descending order
@s = sort{$b <=> $a} @list;
print "\nPrinting numbers in sorted order:\n";
foreach $i(@s)
{
    print "$i, ";
}
```

**输出:**

```
Countries in sorted order: 
BangladeshFranceIndiaItalyQatar

Combining both the lists in sorted order:
BangladeshDelhiDhakaFranceIndiaItalyLahoreParisQatarRome

Printing numbers in sorted order:
99, 54, 33, 19, 4, 2, 
```