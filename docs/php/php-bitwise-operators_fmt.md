# PHP 按位运算符

> 原文: [https://www.geeksforgeeks.org/php-bitwise-operators/](https://www.geeksforgeeks.org/php-bitwise-operators/)

按位运算符用于对操作数执行位级运算。运算符首先转换为位级，然后对操作数执行计算。加法、减法、乘法等数学运算可以在位级执行，以实现更快的处理。在 PHP 中，在位级别工作的运算符是:

## & (Bitwise AND)

这是一个二元运算符，即对两个操作数起作用。PHP 中的按位 AND 运算符将两个数字作为操作数，并对两个数字的每一位进行 AND 运算。AND 的结果是 1，仅当两位都是 1 时。

**语法**:

```php
$First & $Second
```

这将返回另一个数字，其位在 `First` 和 `Second` 的对应位都被设置时才会被设置。

**示例**:

```php
Input: $First = 5, $Second = 3

Output: The bitwise & of both these value will be 1.

Explanation:
Binary representation of 5 is 0101 and 3 is 0011.
Therefore their bitwise & will be 0001 (i.e. set
if both first and second have their bit set.)
```

## | (Bitwise OR)

这也是一个二元运算符，即对两个操作数起作用。按位“或”运算符将两个数字作为操作数，并对两个数字的每一位进行“或”运算。“或”的结果是 1，如果两位中的任何一位是 1。

**语法**:

```php
$First | $Second
```

这将返回另一个数字，其位在 `First` 或 `Second` 的对应位被设置时就会被设置。

**示例**:

```php
Input: First = 5, Second = 3

Output: The bitwise | of both these value will be 7.

Explanation:
Binary representation of 5 is 0101 and 3 is 0011.
Therefore their bitwise | will be 0111 (i.e. set
if either first or second have their bit set.)
```

## ^ (Bitwise XOR)

这也是一个二元运算符，即对两个操作数起作用。这也被称为异或运算符。按位 XOR 将两个数字作为操作数，并对两个数字的每一位进行 XOR 运算。如果两位不同，则 XOR 的结果为 1。

**语法**:

```php
$First ^ $Second
```

这将返回另一个数字，其位在 `First` 或 `Second` 中有一个被设置但并非两者都被设置时才会被设置。

**示例**:

```php
Input: First = 5, Second = 3

Output: The bitwise ^ of both these value will be 6.

Explanation:
Binary representation of 5 is 0101 and 3 is 0011.
Therefore their bitwise ^ will be 0110 (i.e. set
if either first or second have their bit set but
not both.)
```

## ~ (Bitwise NOT)

这是一个一元运算符，即只对一个操作数起作用。按位 NOT 运算符接受一个数字并反转其所有位。

**语法**:

```php
~$number
```

这将反转 `$number` 的所有位。

**示例**:

```php
Input: number = 5

Output: The bitwise '~' of this number will be -6.

Explanation:
Binary representation of 5 is 0101. Therefore the
bitwise ~ of this will be 1010 (inverts all the
bits of the input number)
```

## << (Bitwise Left Shift)

这是一个二元运算符，即对两个操作数起作用。按位左移运算符接受两个数字，将第一个操作数的位向左移动，第二个操作数决定移动的位数。

**语法**:

```php
$First << $Second
```

这将把 `$First` 的位向左移动。`$Second` 决定位将被移动的次数。

**示例**:

```php
Input: First = 5, Second = 1

Output: The bitwise << of both these value will be 10.

Explanation:
Binary representation of 5 is 0101. Therefore,
bitwise << will shift the bits of 5 one times
towards the left (i.e. 01010)
```

**注**: 一位按位左移相当于与 2 相乘。

## >> (Bitwise Right Shift)

这也是一个二元运算符，即对两个操作数起作用。按位右移运算符接受两个数字，将第一个操作数的位向右移动，第二个操作数决定移动的位数。

**语法**:

```php
$First >> $Second
```

这将把 `$First` 的位向右移动。`$Second` 决定位将被移动的次数。

**示例**:

```php
Input: First = 5, Second = 1

Output: The bitwise >> of both these value will be 2.

Explanation:
Binary representation of 5 is 0101. Therefore,
bitwise >> will shift the bits of 5 one times
towards the right(i.e. 010)
```

**注**: 一位按位右移相当于除以 2。

下面是按位运算符在 PHP 中的实现:

```php
<?php
// PHP code to demonstrate Bitwise Operator.

// Bitwise AND
$First = 5;
$second = 3;
$answer = $First & $second;

print_r("Bitwise & of 5 and 3 is $answer");

print_r("\n");

// Bitwise OR
$answer = $First | $second;
print_r("Bitwise | of 5 and 3 is $answer");

print_r("\n");

// Bitwise XOR
$answer = $First ^ $second;
print_r("Bitwise ^ of 5 and 3 is $answer");

print_r("\n");

// Bitwise NOT
$answer = ~$First;
print_r("Bitwise ~ of 5 is $answer");

print_r("\n");

// Bitwise Left shift
$second = 1;
$answer = $First << $second;
print_r("5 << 1 will be $answer");

print_r("\n");

// Bitwise Right shift
$answer = $First >> $second;
print_r("5 >> 1 will be $answer");

print_r("\n");
?>
```

**输出**:

```
Bitwise & of 5 and 3 is 1
Bitwise | of 5 and 3 is 7
Bitwise ^ of 5 and 3 is 6
Bitwise ~ of 5 is -6
5 << 1 will be 10
5 >> 1 will be 2
```