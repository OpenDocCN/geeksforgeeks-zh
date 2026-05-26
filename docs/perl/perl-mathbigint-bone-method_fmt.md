# Perl Math::BigInt模块的bone()方法

> 原文: [https://www.geeksforgeeks.org/perl-mathbigint-bone-method/](https://www.geeksforgeeks.org/perl-mathbigint-bone-method/)

`Math::BigInt` Perl 中的模块提供了用任意精度和重载算术运算符表示整数的对象。

`bone()` 方法属于 `Math::BigInt` 模块，用于创建一个值为 1 的新对象，如果在现有对象上使用，它会将其设置为 1。

## 语法

```
Math::BigInt->bone()
```

## 参数

*   **sign**: 将一的符号设置为 `+` 或 `-`。

## 返回值

返回一个值为 1 的对象。

## 示例

### 示例 1

```perl
#!/usr/bin/perl

# Import Math::BigInt module 
use Math::BigInt;

# Create a BigInt object 
$x = Math::BigInt->bone();

# Object created with bone()
print("$x\n");

# Create a BigInt object 
$x = Math::BigInt->bone('-');

# Object created with bone()
print("$x");
```

**输出:**

```perl

```

### 示例 2

```perl
#!/usr/bin/perl

# Import Math::BigInt module 
use Math::BigInt;

# Specify number 
$num = 78215936043546;

# Create BigInt object 
$x = Math::BigInt->new($num);

# Object before function call
print("Before function call: $x\n");

# Calling the function
$x->bone();

# Object after function call
print("After function call: $x");
```

**输出:**

```perl
Before function call: 78215936043546
After function call: 1
```

### 示例 3

```perl
#!/usr/bin/perl

# Import Math::BigInt module 
use Math::BigInt;

# Specify number 
$num = 78215936043546;

# Create BigInt object 
$x = Math::BigInt->new($num);

# Object before function call
print("Before function call: $x\n");

# Calling the function with '-' sign
$x->bone('-');

# Object after function call
print("After function call: $x");
```

**输出:**

```perl
Before function call: 78215936043546
After function call: -1
```