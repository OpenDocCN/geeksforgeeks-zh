# Perl 多行字符串与Here-Document

> 原文：[https://www.geeksforgeeks.org/perl-multi-line-strings-here-document/](https://www.geeksforgeeks.org/perl-multi-line-strings-here-document/)

Perl 中的字符串是一个标量变量，它可以包含字母、数字和特殊字符。字符串可以由一个单词、一组单词或多行段落组成。在用户想要一个完整的段落或一组段落作为字符串的情况下，需要多行字符串，为此，他或她需要保留空格和换行符。可以使用各种方法创建多行字符串。

## 使用单引号和双引号的多行字符串

用户可以使用单引号（`'`）和双引号（`"`）创建多行字符串。使用双引号会导致字符串中嵌入的变量被其内容替换，而单引号中的变量名称保持不变。

**示例：**

```perl
# Perl code to illustrate the multiline
# string using single quotes and
# double quotes

# consider a string scalar
$GeeksforGeeks = 'GFG';

# multiline string using double quotes
$mline = "This is multiline

string using double quotes

on $GeeksforGeeks";

# displaying result
print "$mline\n\n\n\n";

# multiline string using single quotes
$multi_line = 'This is multiline

string using single quotes

on $GeeksforGeeks';

# displaying result
print "$multi_line\n";
```

**输出：**

```perl
This is multiline

string using double quotes

on GFG

This is multiline

string using single quotes

on $GeeksforGeeks
```

## 使用Here-Document的多行字符串

Here-Document 是多行打印报表的替代方式。Here-Document 也可以用于多行字符串。它在开始处声明一个分隔符，以知道字符串需要在哪里输入。Here-Document 以 `<<` 开头，后跟用户选择的分隔符。字符串读取代码，直到再次出现分隔符，并且其间的所有文本都被视为字符串。

**示例：**

```perl
# Perl code to illustrate the multiline
# string using Here-Document

# consider a string scalar
$GeeksforGeeks = 'GFG';

# defining multiline string using
# ending delimiter without any quotes
$deli = <<string_ending_delimiter;

Multiline string using

Here-Document on

$GeeksforGeeks

string_ending_delimiter

# displaying result
print "$deli\n\n";

# defining multiline string using
# ending delimiter with double quotes
$deli = <<"string_ending_delimiter";

Multiline string using

Here-Document on

$GeeksforGeeks

string_ending_delimiter

# displaying result
print "$deli\n\n";

# defining multiline string using
# ending delimiter with single quotes
$deli = <<'string_ending_delimiter';

Multiline string using

Here-Document on

$GeeksforGeeks

string_ending_delimiter

# displaying result
print "$deli\n\n";
```

**输出：**

```perl
Multiline string using

Here-Document on

GFG

Multiline string using

Here-Document on

GFG

Multiline string using

Here-Document on

$GeeksforGeeks
```

### 解释

在上面的代码中，如果分隔符被放入双引号中，那么嵌入在字符串中的变量将被它们的内容替换，如变量 `$GeeksforGeeks` 被 `GFG` 替换，这被称为**插值Here-Document**。如果分隔符被放入单引号中，那么嵌入在字符串中的变量将不会被它们的内容替换，这被称为**非插值Here-Document**。请记住，如果分隔符没有放入任何引号中，那么默认情况下会被视为插值（即双引号）。

### 注意事项

建议在字符串末尾使用与开头完全相同的分隔符，这意味着分隔符之前不应该有空格，分隔符之后也不应该有空格。否则，Perl 将无法识别它，并将给出错误。换句话说，用户不能缩进结束标记来匹配代码的其余部分。

**示例：**

```perl
# Perl code to illustrate the error by
# changing the ending delimiter

# consider a string scalar
$GeeksforGeeks = 'GFG';

# defining multiline string using
# ending delimiter without any quotes
$deli = <<string_ending_delimiter;

Multiline string using

Here-Document on

$GeeksforGeeks

string_ending_delimiter
```

**运行时错误：**

> 在 /home/1873B0a5dae105B4BFA82E3c79f156c5.pl 第 9 行的 EOF 之前的任何位置都找不到字符串结束符“string_ending_delimiter”。