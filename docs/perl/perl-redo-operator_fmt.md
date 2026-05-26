# Perl | redo运算符

> 原文: `https://www.geeksforgeeks.org/perl-redo-operator/`

在 [`Perl`](https://www.geeksforgeeks.org/introduction-to-perl/) 中的 `redo` 运算符从给定的标签重新开始，不计算条件语句。一旦调用了 `redo`，那么就不会在该块中执行更多的语句。即使有 `continue` 块，在 `redo` 调用后也不会执行。如果使用 `redo` 操作符给定了一个标签，那么执行将从标签指定的循环开始。

> **语法:** `redo LABEL`
>
> **返回:**
> 无值

**例 1:**

```perl
#!/usr/bin/perl -w

$a = 1;

# Assigning label to loop
GFG: {
   $a = $a + 5;
   redo GFG if ($a < 10);
}

# Printing the value
print ($a);
```

**Output:**

```perl

```

**示例 2(重做循环):**

```perl
#!/usr/bin/perl -w

$a = 1;

# Assigning label to loop
$count = 1;
GFG: while($count < 10) {
   $a = $a + 5;
   $count++;
   redo GFG if ($a < 100);
}

# Printing the value
print ("$a $count");
```

**Output:**

```perl
101 21
```