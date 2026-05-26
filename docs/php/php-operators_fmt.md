# PHP 运算符

> Original: [https://www.geeksforgeeks.org/php-operators/](https://www.geeksforgeeks.org/php-operators/)

在本文中，我们将了解如何在 PHP 中使用运算符&各种可用的运算符，并通过示例了解它们的实现。

运算符用于对某些值执行运算。 换句话说，我们可以将运算符描述为接受一些值、对它们执行某些操作并给出结果的东西。 例如，表达式`'+'`中的`“1+2=3”`是一个运算符。 它取两个值`1`和`2`，然后对它们执行加法运算得到`3`。

就像任何其他编程语言一样，PHP 也支持各种类型的运算，如算术运算(加法、减法等)、逻辑运算(AND、OR 等)、增/减运算等。因此，PHP 为我们提供了许多运算符来对各种操作数或变量或值执行此类运算。 这些运算符只不过是执行各种类型操作所需的符号。 下面给出了各种操作员组：

*   算术运算符
*   逻辑运算符或关系运算符
*   比较运算符
*   条件运算符或三元运算符
*   赋值运算符
*   宇宙飞船操作符(在 PHP 7 中引入)
*   数组运算符
*   递增/递减运算符
*   字符串运算符

现在让我们详细了解一下这些运算符。

## 算术运算符

算术运算符用于执行简单的数学运算，如加、减、乘等。下面是 PHP 中的算术运算符及其语法和操作列表。

| operator | name | syntax | Operation |
| --- | --- | --- | --- |
| `+` | 加法 | `$x+$y` | 将操作数 `$x` 和 `$y` 相加 |
| `-` | 减法 | `$x-$y` | 用操作数 `$x` 减去 `$y` |
| `*` | 乘法 | `$x*$y` | 将操作数 `$x` 和 `$y` 相乘 |
| `/` | 除法 | `$x/$y` | 返回操作数 `$x` 除以 `$y` 的商 |
| `**` | 幂 | `$x**$y` | 返回 `$x` 的 `$y` 次幂 |
| `%` | 模 | `$x%$y` | 返回 `$x` 除以 `$y` 的余数 |

**注**：PHP 5.6 中引入了求幂功能。

**示例**：此示例解释 PHP 中的算术运算符。

```php
<?php
  $x = 29; // Variable 1
  $y = 4; // Variable 2

  // Some arithmetic operations on 
  // these two variables
  echo ($x + $y), "\n";
  echo($x - $y), "\n";
  echo($x * $y), "\n";
  echo($x / $y), "\n";
  echo($x % $y), "\n";
?>
```

输出：
```
33
25
116
7.25
1
```

## 逻辑运算符或关系运算符

它们基本上用于条件语句和表达式的操作。 条件语句基于条件。 此外，条件既可以满足，也可以不满足，因此条件语句的结果可以是 `TRUE`，也可以是 `FALSE`。 下面是 PHP 中的逻辑运算符及其语法和操作。

| operator | name | syntax | operation |
| --- | --- | --- | --- |
| `and` | Logical AND | `$x and $y` | 如果两个操作数都为 `true`，则为 `true`；否则为 `false` |
| `or` | Logical OR | `$x or $y` | 如果其中一个操作数为 `true`，则为 `true`；否则为 `false` |
| `xor` | Logical XOR | `$x xor $y` | 如果其中一个操作数为 `true`，但不同时为 `true`，则为 `true` |
| `&&` | Logical AND | `$x && $y` | 如果两个操作数都为 `true`，则为 `true` |
| `\|\|` | Logical OR | `$x \|\| $y` | 如果其中一个操作数为 `true`，则为 `true` |
| `!` | Logical NOT | `!$x` | 如果 `$x` 为 `false`，则为 `true` |

**示例**：此示例描述 PHP 中的逻辑&关系运算符。

```php
<?php
$x = 50;
$y = 30;
  if ($x == 50 and $y == 30)
      echo "and Success \n";

  if ($x == 50 or $y == 20)
      echo "or Success \n";

  if ($x == 50 xor $y == 20)
      echo "xor Success \n";

  if ($x == 50 && $y == 30)
      echo "&& Success \n";

  if ($x == 50 || $y == 20)
      echo "|| Success \n";

  if (!$z)
      echo "! Success \n";
?>
```

输出：
```
and Success 
or Success 
xor Success 
&& Success 
|| Success 
! Success 
```

## 比较运算符

这些运算符用于比较两个元素，并以布尔形式输出结果。 下面是 PHP 中的比较运算符及其语法和操作。

| Operator | Name | Grammar | Operation |
| --- | --- | --- | --- |
| `==` | Equal to | `$x==$y` | 如果两个操作数相等，则返回 `true` |
| `!=` | Not equal to | `$x!=$y` | 如果两个操作数不相等，则返回 `true` |
| `<>` | Not equal to | `$x<>$y` | 如果两个操作数不相等，则返回 `true` |
| `===` | Identical | `$x===$y` | 如果两个操作数相等且类型相同，则返回 `true` |
| `!==` | Not identical | `$x!==$y` | 如果两个操作数不相等或类型不同，则返回 `true` |
| `<` | Less than | `$x<$y` | 如果 `$x` 小于 `$y`，则为 `true` |
| `>` | Greater than | `$x>$y` | 如果 `$x` 大于 `$y`，则为 `true` |
| `<=` | Less than or equal to | `$x<=$y` | 如果 `$x` 小于或等于 `$y`，则为 `true` |
| `>=` | Greater than or equal to | `$x>=$y` | 如果 `$x` 大于或等于 `$y`，则为 `true` |

**示例**：此示例描述 PHP 中的比较运算符。

```php
<?php
  $a = 80;
  $b = 50;
  $c = "80";

  // Here var_dump function has been used to 
  // display structured information. We will learn 
  // about this function in complete details in further
  // articles.
  var_dump($a == $c);
  echo "\n";
  var_dump($a != $b);
  echo "\n";
  var_dump($a <> $b);
  echo "\n";
  var_dump($a === $c);
  echo "\n";
  var_dump($a !== $c);
  echo "\n";
  var_dump($a < $b);
  echo "\n";
  var_dump($a > $b);
  echo "\n";
  var_dump($a <= $b);
  echo "\n";
  var_dump($a >= $b);
?>
```

输出：
```
bool(true)
bool(true)
bool(true)
bool(false)
bool(true)
bool(false)
bool(true)
bool(false)
bool(true)
```

## 条件运算符或三元运算符

这些运算符用于比较两个值并同时获取其中一个结果，具体取决于结果是真还是假。 如果为…，则它们也用作 `if...else` 语句的速记符号，我们将在关于决策的文章中读到。

**语法**：

```php
$var = (condition)? value1 : value2;
```

在这里，`condition` 的计算结果要么为真，要么为假。 如果 `condition` 的计算结果为 `True`，则会将 `value1` 赋给变量 `$var`，否则会将 `value2` 赋给它。

| operator | name | Operation |
| --- | --- | --- |
| `?:` | 三元 | 这意味着如果条件为真，则接受冒号的左边的结果，否则结果在右边。 |

**示例**：此示例描述 PHP 中的条件运算符或三元运算符。

```php
<?php
  $x = -12;
  echo ($x > 0) ? 'The number is positive' : 'The number is negative';
?>
```

输出：
```
The number is negative
```

## 赋值运算符

这些运算符用于将值赋给不同的变量，带或不带中间运算。 以下是 PHP 为操作提供的赋值操作符及其语法和操作。

| operator | name | syntax | Operation |
| --- | --- | --- | --- |
| `=` | 赋值 | `$x=$y` | 左边的操作数获得右边的操作数的值 |
| `+=` | 相加然后赋值 | `$x+=$y` | 简单加法等于 `$x=$x+$y` |
| `-=` | 减法然后赋值 | `$x-=$y` | 简单减法等于 `$x=$x-$y` |
| `*=` | 相乘，然后将 | `$x*=$y` | 简单乘积等于 `$x=$x*$y` |
| `/=` | 除法然后赋值 | `$x/=$y` | 简单除法等于 `$x=$x/$y` |
| `%=` | 除法（余数）后赋值 | `$x%=$y` | 简单取模等于 `$x=$x%$y` |

**示例**：此示例描述 PHP 中的赋值运算符。

```php
<?php
  // Simple assign operator
  $y = 75;
  echo $y, "\n";

  // Add then assign operator
  $y = 100;
  $y += 200;
  echo $y, "\n";

  // Subtract then assign operator
  $y = 70;
  $y -= 10;
  echo $y, "\n";

  // Multiply then assign operator
  $y = 30;
  $y *= 20;
  echo $y, "\n";

  // Divide then assign(quotient) operator
  $y = 100;
  $y /= 5;
  echo $y, "\n";

  // Divide then assign(remainder) operator
  $y = 50;
  $y %= 5;
  echo $y;
?>
```

输出：
```
75
300
60
600
20
0
```

## 数组运算符

这些运算符用于数组。 以下是 PHP 为数组操作提供的数组运算符及其语法和操作。

| operator | name | syntax | Operation |
| --- | --- | --- | --- |
| `+` | Union | `$x+$y` | `$x` 和 `$y` 的并集 |
| `==` | Equality | `$x==$y` | 如果两者具有相同的键值对，则返回 `true` |
| `!=` | Inequality | `$x!=$y` | 如果两者不相等，则返回 `true` |
| `===` | Identity | `$x===$y` | 如果两者具有相同顺序和相同类型的相同键值对，则返回 `true` |
| `!==` | Non-identity | `$x!==$y` | 如果两者不相同，则返回 `true` |
| `<>` | Inequality | `$x<>$y` | 如果两者不相等，则返回 `true` |

**示例**：此示例描述 PHP 中的数组操作。

```php
<?php
  $x = array("k" => "Car", "l" => "Bike");
  $y = array("a" => "Train", "b" => "Plane");

  var_dump($x + $y);
  echo "\n";
  var_dump($x == $y);
  echo "\n";
  var_dump($x != $y);
  echo "\n";
  var_dump($x <> $y);
  echo "\n";
  var_dump($x === $y);
  echo "\n";
  var_dump($x !== $y);
?>
```

输出：
```
array(4) {
  ["k"]=>
  string(3) "Car"
  ["l"]=>
  string(4) "Bike"
  ["a"]=>
  string(5) "Train"
  ["b"]=>
  string(5) "Plane"
}
bool(false)
bool(true)
bool(true)
bool(false)
bool(true)
```

## 递增/递减运算符

这些运算符称为一元运算符，因为它们处理单个操作数。 这些值用于递增或递减值。

| operator | name | syntax | Operation |
| --- | --- | --- | --- |
| `++` | 预增量 | `++$x` | 先将 `$x` 加 1，然后返回 `$x` |
| `--` | 预减量 | `--$x` | 首先将 `$x` 减一，然后返回 `$x` |
| `++` | 后增量 | `$x++` | 首先返回 `$x`，然后递增 1 |
| `--` | 后减量 | `$x--` | 首先返回 `$x`，然后将其减一 |

**示例**：此示例描述 PHP 中的递增/递减运算符。

```php
<?php
  $x = 2;
  echo ++$x, " First increments then prints \n";
  echo $x, "\n";

  $x = 2;
  echo $x++, " First prints then increments \n";
  echo $x, "\n";

  $x = 2;
  echo --$x, " First decrements then prints \n";
  echo $x, "\n";

  $x = 2;
  echo $x--, " First prints then decrements \n";
  echo $x;
?>
```

输出：
```
3 First increments then prints 
3
2 First prints then increments 
3
1 First decrements then prints 
1
2 First prints then decrements 
1
```

## 字符串运算符

此运算符用于使用连接运算符(`.`)连接 2 个或多个字符串。 我们还可以使用连接赋值运算符(`.=`)将右侧的参数附加到左侧的参数。

| operator | name | syntax | Operation |
| --- | --- | --- | --- |
| `.` | Concatenation | `$x.$y` | 连接 `$x` 和 `$y` |
| `.=` | Concatenation and assignment | `$x.=$y` | 连接然后赋值，等同于 `$x = $x . $y` |

**示例**：此示例描述 PHP 中的字符串运算符。

## PHP

```php
<?php
  $x = "Geeks";
  $y = "for";
  $z = "Geeks!!!";
  echo $x . $y . $z, "\n";
  $x .= $y . $z;
  echo $x;
?>
```

发帖主题：Re：Колибри0.7.8.0

```php
GeeksforGeeks!!!
GeeksforGeeks!!!
```

`飞船操作员`：

PHP7 引入了一种新的运算符，称为宇宙飞船运算符。 飞船运算符或组合比较运算符由`<=>`表示。 这些运算符用于比较值，但它返回的不是布尔结果，而是整数值。 如果两个操作数相等，则返回`0`。 如果右操作数较大，则返回`-1`。 如果左操作数更大， 它返回`1`。下表详细显示了它的工作方式：

| 操作符 | 语法 | 操作 |
| --- | --- | --- |
| `$x <=> $y` | `$x <=> $y` | 等于`-1`（右边较大） |
| `$x <=> $y` | `$x <=> $y` | 等于`1`（左边较大） |
| `$x <=> $y` | `$x <=> $y` | 等于`-1`（右边较大）或等于`0`（如果两者相等） |
| `$x <=> $y` | `$x <=> $y` | 等于`1`（如果左边较大）或等于`0`（如果两者相等） |
| `$x == $y` | `$x <=> $y` | 等于`0`（两者相等） |
| `$x != $y` | `$x <=> $y` | 不等于`0` |

`示例`：此示例说明了 PHP 中宇宙飞船操作符的用法。

## PHP

```php
<?php
  $x = 50;
  $y = 50;
  $z = 25;

  echo $x <=> $y;
  echo "\n";

  echo $x <=> $z;
  echo "\n";

  echo $z <=> $y;
  echo "\n";

  // We can do the same for Strings
  $x = "Ram";
  $y = "Krishna";

  echo $x <=> $y;
  echo "\n";

  echo $x <=> $y;
  echo "\n";

  echo $y <=> $x;
?>
```

发帖主题：Re：Колибри0.7.8.0

```php

```

本文由`Chinmoy Lenka`贡献。 如果你喜欢 GeeksforGeek 并想投稿，你也可以使用`write.geeksforgeeks.org`写一篇文章，或者把你的文章邮寄到`Review-team@geeksforgeeks.org`。 看看你的文章出现在 GeeksforGeek 主页上，并帮助其他 Geek。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的主题的信息，请写下评论。