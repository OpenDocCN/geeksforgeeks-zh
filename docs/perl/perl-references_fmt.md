### 参考创建

您可以为[标量](https://www.geeksforgeeks.org/perl-scalars/)值、散列、数组、函数等创建引用。为了创建一个引用，定义一个新的标量变量，并通过在它前面加一个反斜杠来为它指定变量的名称(您想要创建它的引用)。

**示例:**引用不同的数据类型:

```perl
# Array Reference

# defining array 
@array = ('1', '2', '3');

# making reference of array variable  
$reference_array = \@array;

```

```perl
# Hash Reference

# defining hash
%hash = ('1'=>'a', '2'=>'b', '3'=>'c');

# make reference of the hash variable
$reference_hash = \%hash;

```

```perl
# Scalar Value Reference

# defining scalar
$scalar_val = 1234;

# making reference of scalar variable
$reference_scalar = \$scalar_val;

```

**注:**

*   一个对匿名[**hash**](https://www.geeksforgeeks.org/perl-hashes/)的引用可以使用花括号`{}`围绕键值对来创建。

**示例:**

```perl
    # creating reference to anonymous hash
    $ref_to_anonymous_hash = {'GFG' => '1', 'Geeks' => '2'};

```

*   一个对匿名数组的引用可以使用方括号`[]`来创建。

**示例:**

```perl
    # creating reference to an anonymous array
    $ref_to_anonymous_array = [20, 30, ['G', 'F', 'G']];

```

*   一个对匿名子程序的引用也可以借助`sub`来创建。这里`sub`将没有名称。

**示例:**

```perl
    # creating reference to an anonymous subroutine
    $ref_to_anonymous_subroutine = sub { print "GeeksforGeeks\n"};

```

*   无法创建对输入/输出句柄的引用，即目录句柄和文件句柄。

### 取消引用

现在，在我们进行了引用之后，我们需要使用它来访问值。**取消引用**是访问引用所指向的内存中的值的方式。为了取消引用，我们根据变量的类型使用前缀`$`、`@`、`%`或`&` (引用可以指向数组、标量或散列等)。

**例 1:**

```perl
# Perl program to illustrate the 
# Dereferencing of an Array

# defining an array
@array = ('1', '2', '3');

# making an reference to an array variable
$reference_array = \@array;

# Dereferencing
# printing the value stored 
# at $reference_array by prefixing 
# @ as it is a array reference
print @$reference_array;
```

**Output:**

```perl
123
```

**例 2:**

```perl
# Perl program to illustrate the 
# Dereferencing of a Hash

# defining hash
%hash = ('1'=>'a', '2'=>'b', '3'=>'c');

# creating an reference to hash variable
$reference_hash = \%hash;

# Dereferencing
# printing the value stored 
# at $reference_hash by prefixing 
# % as it is a hash reference
print %$reference_hash;
```

**Output:**

```perl
3c2b1a
```

**例 3:**

```perl
# Perl program to illustrate the 
# Dereferencing of a Scalar

# defining a scalar
$scalar = 1234;

# creating an reference to scalar variable 
$reference_scalar = \$scalar;

# Dereferencing
# printing the value stored 
# at $reference_scalar by prefixing 
# $ as it is a Scalar reference
print $reference_scalar;
```

**Output:**

```perl
1234
```