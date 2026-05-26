# Perl | splice()–多功能功能

> 原文: [https://www.geeksforgeeks.org/perl-splice-the-versatile-function/](https://www.geeksforgeeks.org/perl-splice-the-versatile-function/)

在 [Perl](https://www.geeksforgeeks.org/introduction-to-perl/) 中，`splice()`函数用于从数组中移除并返回一定数量的元素。可以插入元素列表来代替移除的元素。

## 语法

> `splice(@array, $offset, $length, $replace_list)`

## 参数

*   `@array` – 要操作的数组。
*   `$offset` – 移除元素的起始偏移量。
*   `$length` – 从偏移量开始要移除的元素数量（包括偏移量处的元素）。
*   `$replace_list` – 用于替换被移除元素的列表。

## 例

```perl
#!/usr/bin/perl

# an array of numbers from 0 to 7
@array = (0..7);

# Original array
print "Original Array: @array\n";

# splice() replaces elements from
# 2 to 4 with a to c
@array2 = splice(@array, 2, 3, (a..c));

# Printing the Updated Array
print("Elements of Updated \@array are @array\n");

# array2 contains elements removed
# from array i.e. 2, 3 and 4
print("Removed elements are @array2");
```

## 输出

```perl
Original Array: 0 1 2 3 4 5 6 7
Elements of Updated @array are 0 1 a b c 5 6 7
Removed elements are 2 3 4
```