# Perl 数组（push、pop、shift、unshift）

> 原文：[https://www.geeksforgeeks.org/perl-arrays-push-pop-shift-unshift/](https://www.geeksforgeeks.org/perl-arrays-push-pop-shift-unshift/)

Perl 提供了各种内置函数来添加和移除数组中的元素。

| 功能 | 描述 |
| :--- | :--- |
| `push` | 在数组末尾插入列表值 |
| `pop` | 移除数组的最后一个值 |
| `shift` | 左移数组的所有值 |
| `unshift` | 将列表元素添加到数组的前面 |

## `push` 函数

该函数将列表中给出的值插入到数组的末尾。可以插入多个值，用逗号分隔。这个函数增加了数组的大小。它返回新数组中的元素数。

> **语法：** `push(ARRAY, LIST)`

**例：**

```perl
#!/usr/bin/perl

# Initializing the array
@x = ('Java', 'C', 'C++');

# Print the Initial array
print "Original array: @x \n";

# Pushing multiple values in the array
push(@x, 'Python', 'Perl');

# Printing the array
print "Updated array: @x";
```

**输出：**

```
Original array: Java C C++ 
Updated array: Java C C++ Python Perl
```

## `pop` 函数

此函数用于移除数组的最后一个元素。在执行 `pop` 函数后，数组的大小减少一个元素。如果列表为空，此函数返回 `undef`，否则返回数组的最后一个元素。

> **语法：** `pop(ARRAY)`

**例：**

```perl
#!/usr/bin/perl

# Initializing the array
@x = ('Java', 'C', 'C++');

# Print the Initial array
print "Original array: @x \n";

# Prints the value returned by pop
print "Value returned by pop: ", pop(@x);

# Prints the array after pop operation
print "\nUpdated array: @x";
```

**输出：**

```
Original array: Java C C++ 
Value returned by pop: C++
Updated array: Java C
```

## `shift` 函数

此函数返回数组中的第一个值，将其移除，并将数组列表的元素向左移动 1。`shift` 操作删除了类似 `pop` 的值，但从数组的开头而不是 `pop` 中的结尾开始。如果数组为空，此函数返回 `undef`，否则返回数组的第一个元素。

> **语法：** `shift(ARRAY)`

**例：**

```perl
#!/usr/bin/perl

# Initializing the array
@x = ('Java', 'C', 'C++');

# Print the Initial array
print "Original array: @x \n";

# Prints the value returned
# by shift function
print "Value returned by shift: ", shift(@x);

# Array after shift operation
print "\nUpdated array: @x";
```

**输出：**

```
Original array: Java C C++ 
Value returned by shift: Java
Updated array: C C++
```

## `unshift` 函数

该函数将给定的元素列表放在数组的开头。从而向右移动数组中的所有值。使用此操作可以取消多个值的偏移。此函数返回数组中新元素的数量。

> **语法：** `unshift(ARRAY, LIST)`

**例：**

```perl
#!/usr/bin/perl

# Initializing the array
@x = ('Java', 'C', 'C++');

# Print the Initial array
print "Original array: @x \n";

# Prints the number of elements
# returned by unshift
print "No of elements returned by unshift: ", unshift(@x, 'PHP', 'JSP');

# Array after unshift operation
print "\nUpdated array: @x";
```

**输出：**

```
Original array: Java C C++ 
No of elements returned by unshift: 5
Updated array: PHP JSP Java C C++
```