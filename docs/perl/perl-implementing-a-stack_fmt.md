# Perl 实现堆栈

> 原文: [https://www.geeksforgeeks.org/perl-implementing-a-stack/](https://www.geeksforgeeks.org/perl-implementing-a-stack/)

[Perl](https://www.geeksforgeeks.org/introduction-to-perl/) 中的堆栈是一种线性数据结构，遵循**后进先出**（LIFO）或 **FILO**（先进后出）的顺序。
简单来说，栈是一个数组，其中插入和删除只发生在称为栈顶的一端。
**推入（Push）** 是将元素插入堆栈的过程。
**弹出（Pop）** 是移除堆栈最顶层元素的过程。

## 创建堆栈

用 Perl 创建堆栈相当简单。我们只需要声明一个数组。
堆栈可以是空的，如下所示：

```perl
@stack;
```

或者它可以被初始化：

```perl
@stack = (1, 2, 3);
```

## 向堆栈推入元素

可以使用 `push()` 函数或 `splice()` 函数进行推入。

### 使用 `push()` 推入

> **语法:** `push(@stack, list);`
> **参数:**
> *   `@stack` – 要在其上执行推入操作的堆栈。
> *   `list` – 要推入堆栈的元素。这些元素可以是标量、数组、散列或它们的任意组合。

**示例:**

```perl
#!/usr/bin/perl

# Intitialising the Stack
@stack = (1..3);

# Original stack
print "Original Stack: @stack";

# Scalar to be pushed
$scalar = "scalar";

# Array to be pushed
@array = ("a", "r", "r", "a", "y");

# Hash to be pushed
%hash = ("Geeks" => 10, 
         "for Geeks" => 20);

# scalars, arrays and hashes can be
# inserted at the same time
push(@stack, ($scalar, @array, %hash));

# Updated Stack after 
# Push operations
print("\nUpdated Stack: @stack");
```

**输出:**

```perl
Original Stack: 1 2 3
Updated Stack: 1 2 3 scalar a r r a y Geeks 10 for Geeks 20
```

### 使用 `splice()` 推入

> **语法:** `splice(@stack, scalar(@stack), 0, list);`
> **参数:**
> *   函数的作用是：在 `@stack` 的末尾追加 `list`。
> *   `list` 可以是标量、数组或哈希。

**示例:**

```perl
#!/usr/bin/perl

# Intitialising the Stack
@stack = (1..3);

# Original stack
print "Original Stack: @stack";

# Scalar to be pushed
$scalar = "scalar";

# Array to be pushed
@array = ("a", "r", "r", "a", "y");

# Hash to be pushed
%hash = ("Geeks" => 10, 
         "for Geeks" => 20);

# scalars, arrays and hashes can be
# inserted at the same time
splice(@stack, scalar(@stack), 0, 
       ($scalar, @array, %hash));

# Updated Stack after 
# Push operations
print("\nUpdated Stack: @stack");
```

**输出:**

```perl
Original Stack: 1 2 3
Updated Stack: 1 2 3 scalar a r r a y Geeks 10 for Geeks 20
```

## 从堆栈弹出元素

可以使用 `pop()` 函数或 `splice()` 函数进行弹出。

### 使用 `pop()` 弹出

> **语法:** `$popped_element = pop(@stack);`
> **参数:**
> *   函数的作用是：返回弹出的元素。
> *   `$popped_element` 包含从堆栈中弹出的元素。

**示例:**

```perl
#!/usr/bin/perl

# Intitialising the Stack
@stack = (1..3);

# Original stack
print "Original Stack: @stack";

# Topmost element i.e. 3 is 
# removed and returned
$popped_element = pop(@stack);

# Printing popped element
print "\nPopped element: $popped_element";

# Updated Stack after 
# Pop operation
print("\nUpdated Stack: @stack");
```

**输出:**

```perl
Original Stack: 1 2 3
Popped element: 3
Updated Stack: 1 2
```

*   如果堆栈为空，则返回 `undef`。`undef` 类似于 Java 中的 `NULL` 和 Python 中的 `None`。但是，不会引发错误。

**示例:**

```perl
#!/usr/bin/perl

# Creating a Stack
@stack;

# undef is returned since the 
# stack is empty. 
# No error is raised.
$popped_element = pop(@stack);

# Printing popped element
# Since it contains no value,
# hence a blank space is returned
print "Popped element: $popped_element";
```

**输出:**

```perl
Popped element:
```

### 使用 `splice()` 弹出

> **语法:** `$popped_element = splice(@stack, -1);`
> **参数:**
> *   函数的作用是：移除堆栈的最后一个元素，然后返回。
> *   `$popped_element` 存储返回值。

**示例:**

```perl
#!/usr/bin/perl

# Intitialising the Stack
@stack = (1..3);

# Original stack
print "Original Stack: @stack";

# popping using splice()
$popped_element = splice(@stack, -1);

# Printing popped element
print "\nPopped element: $popped_element";

# Updated Stack after 
# Pop operation
print("\nUpdated Stack: @stack");
```

**输出:**

```perl
Original Stack: 1 2 3
Popped element: 3
Updated Stack: 1 2
```

*   如果堆栈为空，则会引发错误。以下代码会引发错误：

```perl
use warnings;
#!/usr/bin/perl

use warnings;

# Creating a Stack
@stack;

# popping using splice()
# An error is raised here
$popped_element = splice(@stack, -1);

# Printing popped element
print "\nPopped element: $popped_element";

# Updated Stack after 
# Pop operation
print("\nStack: @stack");
```

**运行时错误:**

> Useless use of a variable in void context at /home/59c7c19979aa9e46564cd145d5fe5601.pl line 6.
> Modification of non-creatable array value attempted, subscript -1 at /home/59c7c19979aa9e46564cd145d5fe5601.pl line 10.