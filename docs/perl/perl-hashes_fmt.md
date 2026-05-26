# Perl 哈希

> 原文: [https://www.geeksforgeeks.org/perl-hashes/](https://www.geeksforgeeks.org/perl-hashes/)

一组**键/值**对被称为哈希。哈希结构中的每个键都是唯一的，并且是类型字符串。与这些键相关联的值是[**标量**](https://www.geeksforgeeks.org/perl-scalars/)。这些值可以是数字、字符串或引用。哈希是使用 `my` 关键字声明的。变量名前面是美元符号 `$`，后面是花括号下的键和与该键关联的值。每个键都与一个值相关联。

**例:**

```perl
my %rateof{mango} = 45;
```

## 什么时候用数组，什么时候用哈希？

*   如果事情是有序的，那么去数组。例如:

```perl
1. A list of people in a bank queue.
2. A list of people in railway reservation line.
3. A list of files to read.
```

*   如果我们拥有的东西不合适，那就去找哈希吧。例如:

```perl
1. An index of surname looked up by the first name.
2. An index showing the size of files looked up by name.
```

## 空哈希

没有任何键的哈希变量称为**空哈希**。

*   **例:**

```perl
my %rateof;
```

*   这里的 `%rateof` 是哈希变量。

## 将键/值对插入哈希

键总是字符串类型，值总是标量类型。

*   **例:**

```perl
$rateof{'mango'} = 45;
```

*   这里的键是 `'mango'`，数值是 `45`。

## 哈希的初始化与获取元素

哈希变量可以在其声明期间用键/值对进行初始化。有两种方法可以初始化哈希变量。一种是使用 `=>`，称为**胖箭**或**胖逗号**。第二种是将键/值对放入由逗号 `,` 分隔的**双引号 `""`** 中。使用胖逗号提供了另一种选择，因为您可以在键周围留下双引号。

要从哈希中访问单个元素，可以使用美元符号 `$` 后跟哈希变量，再跟花括号下的键。在访问键/值对时，如果您传递了不存在的键，那么它将返回一个未定义的值，或者如果您打开了警告，它将显示警告。

*   **例:**

```perl
# Perl program to demonstrate the
# Fetching an element of a Hash

# creating hash
%rateof = ('Mango' => 45, 'Orange' => 30, 'Grapes' => 40);

# Fetching an element of Hash
print "$rateof{'Mango'}\n";
print "$rateof{'Orange'}\n";
print "$rateof{'Grapes'}\n";
```

*   **输出:**

```perl
45
30
40
```

*   **解释:** 要访问 `'Mango'`、`'Orange'`、`'Grapes'` 三个键，并打印与之相关的值，只需使用 `$` 后跟键。`print` 语句将打印与该键关联的值。

## 哈希中的空值

通常，不能将空值分配给哈希的键。但是在 Perl 中，有一种方法可以为哈希提供空值。通过使用 [**undef**](https://www.geeksforgeeks.org/perl-undef-and-the-defined-function/) 功能。`undef` 可以根据用户的需要分配给新的或现有的键。将 `undef` 放在双引号中会使其成为字符串而不是空值。

```perl
# Perl program to demonstrate the
# empty values of a Hash

#use warnings;

# creating hash
%rateof = ('Mango' => 45, 'Orange' => undef, 'Grapes' => 40);

# Fetching an element of Hash
print "$rateof{'Mango'}\n";
print "$rateof{'Orange'}\n";
print "$rateof{'Grapes'}\n";
```

**输出:**

```perl
45

40
```

## 迭代哈希

要访问哈希中的值，用户必须知道与该值相关联的键。如果一个哈希的键事先不知道，那么在 `keys` 函数的帮助下，用户可以获得键列表，并可以迭代这些键。

**例:**

```perl
my @fruits = keys %rateof;
for my $fruit (@fruits) {
    print "The color of '$fruit' is $rateof{$fruit}\n";
}
```

## 哈希的大小

键/值对的数量被称为哈希的大小。要获得大小，第一个用户必须创建一个键或值的数组，然后他可以获得数组的大小。

*   **语法:**

```perl
print scalar keys %hash_variable_name;
```

*   **例:**

```perl
# Perl program to find the size of a Hash

#use warnings;

# creating hash
%rateof = ('Mango' => 64, 'Apple' => 54, 'Grapes' => 44, 'Strawberry'=>23);

# creating array of keys
@keys = keys %rateof;
$size = @keys;
print "Hash size using Keys is: $size\n";

# creating array of values
@values = values %rateof;
$size = @values;
print "Hash size using Values is: $size\n";
```

*   **输出:**

```perl
Hash size using Keys is: 4
Hash size using Values is: 4
```

## 在哈希中添加和移除元素

用户可以使用简单的赋值运算符轻松地将新的一对键/值添加到哈希中。

*   **示例 1:** 在哈希中添加元素

```perl
# Perl program to add an element in a hash

#use warnings;

# creating hash
%rateof = ('Mango' => 64, 'Apple' => 54, 'Grapes' => 44, 'Strawberry'=>23);

# array of keys
@keys = keys %rateof;

$size = @keys;
print "SIZE OF HASH BEFORE ADDING:  is $size\n";

# Adding new key/value pair into hash
$rateof{'Potato'} = 20;

# array of keys
@keys= keys %rateof;

$size = @keys;
print "SIZE OF HASH AFTER ADDING:  is $size\n";
```

*   **输出:**

```perl
SIZE OF HASH BEFORE ADDING:  is 4
SIZE OF HASH AFTER ADDING:  is 5
```

*   **示例 2:** 使用 `delete` 功能从哈希中删除元素

```perl
# Perl program to delete an element from hash

#use warnings;

# creating hash
%rateof = ('Mango' => 64, 'Apple' => 54, 'Grapes' => 44, 'Strawberry'=>23);

# creating array of keys
@keys= keys %rateof;

# finding size of hash
$size = @keys;
print "SIZE OF HASH BEFORE DELETING: $size\n";

# using delete function
delete $rateof{'Mango'};

# creating array of keys
@keys= keys %rateof;

# finding size of hash
$size = @keys;
print "SIZE OF HASH AFTER DELETING: $size\n";
```

*   **输出:**

```perl
SIZE OF HASH BEFORE DELETING: 4
SIZE OF HASH AFTER DELETING: 3
```