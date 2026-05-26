# Perl–面向对象编程中的属性

> 原文: [https://www.geeksforgeeks.org/perl-attributes-in-object-oriented-programming/](https://www.geeksforgeeks.org/perl-attributes-in-object-oriented-programming/)

在 [`Perl`](https://www.geeksforgeeks.org/introduction-to-perl/) 中，面向对象的概念非常基于引用和*数组/散列*。相对于 Perl 编程，面向对象编程的几个主要术语是对象、类和方法。

*   在 Perl 中，`object`（对象）类似于一个数据类型的引用，它知道其所属的类。对象作为引用存储在`scalar`（标量）变量中。因为标量只包含对对象的引用，所以它甚至可以容纳不同类的不同对象。
*   在 Perl 中，包含创建和操作对象所需相应方法的`package`（包）被称为`class`（类）。
*   在 Perl 中，`method`（方法）是在包中定义的`subroutine`（子程序）。根据方法是作用于当前类还是对象，包名或对象引用是该方法的第一个参数。

## 属性

每个类都可以定义属性。当我们将它们表示为对象时，我们为这些属性赋值。例如，甚至每个“文件”对象都有一个路径。属性也称为属性。

属性通常定义为只读或读写。只读属性只能在创建对象时设置，而读写属性可以随时更改。一个属性值本身可以是另一个对象。并不是每个类都必须有属性和方法。

Perl 没有特殊的属性语法。在后面，属性通常作为键存储在对象的底层散列中。

## Perl 示例

```perl
sub new{
    my ($class, $args) = @_;
    my $self = bless { serial => $args->{serial},
                       name => $args->{name},
                       price => $args->{price}
                     }, $class;
}
```