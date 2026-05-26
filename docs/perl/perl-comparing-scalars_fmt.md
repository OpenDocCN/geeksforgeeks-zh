# Perl | 比较标量

> 原文: [https://www.geeksforgeeks.org/perl-comparing-scalars/](https://www.geeksforgeeks.org/perl-comparing-scalars/)

## 先决条件: [Perl 中的标量](https://www.geeksforgeeks.org/perl-scalars/)

Perl 有两种类型的比较运算符集。就像其他数学运算符一样，这些运算符不是执行运算，而是比较标量。有两种类型的 Perl 比较运算符集。
一个是**数值标量值**，一个是**字符串标量值**。下表说明了这两种类型:

| 数字的 | 线 | 描述 |
| --- | --- | --- |
| `==` | `eq` | 等于 |
| `!=` | `ne` | 不等于 |
| `<` | `lt` | 小于 |
| `>` | `gt` | 大于 |
| `<=` | `le` | 小于或等于 |
| `>=` | `ge` | 大于或等于 |

**以上数值和字符串标量比较运算符的说明:**

### `==` and `eq`

This operator is used to check the equality. In the following code, outputs of codes after using `==` and `eq` is compared and showing how it work for numeric and string scalars differently.

**例 1:**

```perl
# Perl program to illustrate
# == operator

# taking two numeric scalars
$x = 5;
$y = 5;

# using "==" operator
if($x == $y)
{
    print "== works with numeric value!";
}
```

**输出:**

```perl
== works with numeric value!
```

**例 2:**

```perl
# Perl program to illustrate
# == and eq operator

# string scalar
$str = "geekforgeeks";

if($str == "GEEKSFORGEEKS")
{
    print "== doesn't work with string values!";
}

# comparing with capital string
if($str eq "GEEKSFORGEEKS")
{
    print "eq works with string values!";
}
```

**输出:**

```perl
== doesn't work with string values!
```

**说明:** 在示例 2 的输出中，因为`$str`和`GEEKSFORGEEKS`不相等，所以不会执行 Last print 语句。另外，“G”和“G”的 ASCII 码是不同的。因此，`==`适用于数值，但不适用于字符串值，`eq`仅适用于字符串标量。

### `!=` and `ne`

在下面的代码中，比较了使用后的输出`!=`和`ne`，并显示了哪一个适合字符串，哪一个适合数值标量值。

**例 1:**

```perl
# Perl program to demonstrate the 
# != operator

# numeric scalars
$x = 5;
$y = 10;

# using != operator
if($x != $y)
{
    print "!= works with numeric value!";
}
```

**输出:**

```perl
!= works with numeric value!
```

**例 2:**

```perl
# Perl program to demonstrate the 
# != and ne operator

# string scalar
$str = "geekforgeeks";

# using != operator
if($str != "GEEKSFORGEEKS")
{
    print "\n!= doesn't work with string values!";
}

# comparing with capital string
if($str ne "GEEKSFORGEEKS")
{
    print"ne works with string values!";
}
```

**输出:**

```perl
ne works with string values!
```

**说明:** 在第二个例子中，不会执行第一个 print 语句，因为`!=`将两个字符串都转换为 0。因此`!=`适用于数值，但不适用于字符串值，`ne`适用于字符串标量。

### `(> or gt)` And `(< or lt)`

在下面的代码中，我们将比较使用(`> or gt`)和(` < or lt`)。

**例 1:**

```perl
# Perl program to demonstrate the 
# (> or gt) And (< or lt)
# operator

# numeric scalars
$x = 4;
$y = 5;

# using (> or gt) And (< or lt)
if(($x < $y) and ($x lt $y) )
{
    print "< and lt works with numeric value!";
}

if(($y > $x) and ($y gt $x) )
{
    print "\n> and gt works with numeric value!";
}
```

**输出:**

```perl
< and lt works with numeric value!
> and gt works with numeric value!
```

**例 2:**

```perl
# Perl program to demonstrate the 
# (> or gt) And (< or lt)
# operator

# string scalar
$str = "geekforgeeks";

if($str < "GEEKSFORGEEKS")
{
    print "< doesn't work with string values!";
}

# comparing with capital string
if($str lt "GEEKSFORGEEKSZZZ")
{
    print"lt works with string values!";
}

# comparing with capital string
if($str gt "GEEKSFORGEEKSZZZ")
{
    print"gt works with string values!";
}

# comparing with capital string
if($str lt "kEEKSFORGEEKS")
{
    print"\nlt works with string values!";
}
```

**输出:**

```perl
gt works with string values!
lt works with string values!
```

**解释:** 上面的代码告诉我们一些关于 Perl 如何处理字符串的有趣的事情。第一个例子的输出非常明显，因为字符串和数值运算符都以同样的方式对待数值标量。
但是在第二个输出中，“lt”并没有像我们预期的那样表现。假设 Perl 的“lt”运算符不区分大小写，但我们甚至在后面加上了“ZZZ”，即使在这种情况下,`$str`也不小于引号中的字符串，下一个输出显示它更大。从第二个例子输出的第二行
可以清楚地看到这一点，Perl 的字符串运算符只需首先检查字符串的第一个字符，然后比较 ASCII 码。因为在 ASCII 表中，大写字母排在第一位。Perl 编译器匹配第一个字母，然后匹配其余字母。

### `(>= or ge)` And `(<= or le)`

这些操作符也处理 ASCII 值，在字符串操作符的情况下进行检查。如果是数值运算符，则检查该值。

**示例:**

```perl
# Perl program to demonstrate the 
# (>= or ge) And (<= or le)
# operator

# numeric scalars
$x = 5;
$y = 10;

if(($x <= $y) and ($y >= $x))
{
    print "<= and>= works";
}

# string scalar
$str= "geeksforgeeks";

if (($str le "keeksforgeeks") and ($str ge "feeksforgeeks"))
{
    print "\nle and ge works!";
}
```

**输出:**

```perl
<= and>= works
le and ge works!
```

**需要记住的要点:**

### 数值运算符会将字符串值转换为 0

当我们用数值运算符（如`==`、`>=`或`<=`）比较两个字符串标量时，它总是会将标量转换为 0 或 0.0。因为它们不是字符串。因此，在`==`、`>=`或`<=`的情况下它将为真，如下例所示:

```perl
# Perl program to illustrate 
# above point

# numeric scalars
$x = "BBB";
$y = "aaa";

if (($x == $y and ($x <= $y) and ($x >= $y)))
{
    print "True";
}
```

**输出:**

```perl
True
```

**解释:** 在上面的代码中，“aaa”在各个方面都小于 BBB(小写，也是 ASCII 的 a 大于 B)，但是两个字符串仍然是相等的，因为数值比较运算符将字符串转换为 0。

### 字符串运算符不比较数值，而是比较它们的 ASCII 值

字符串运算符比较数值的 ASCII 值。在下面的例子中，“9 gt 17”为真，但“17 gt 9”的结果为假。

```perl
# Perl program to illustrate 
# above point

# numeric scalar
$x = 9;
$y = 17;

if ($x gt $y)
{
    print "True";
}
```

**输出:**

```perl
True
```