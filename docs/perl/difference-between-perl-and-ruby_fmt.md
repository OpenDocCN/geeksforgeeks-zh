# Perl 和 Ruby 的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-perl-and-ruby/](https://www.geeksforgeeks.org/difference-between-perl-and-ruby/)

[**Perl**](https://www.geeksforgeeks.org/introduction-to-perl/) 是一种通用的、高级解释的动态编程语言。它是拉里·沃尔在 1987 年开发的。Perl 最初是为文本处理而开发的，比如从指定的文本文件中提取所需的信息，以及将文本文件转换成不同的形式。Perl 支持过程式和面向对象编程。Perl 在语法上与 C 非常相似，对于有 C、C++知识的用户来说很容易。

## Perl

```perl
# Simple Perl program
#!/usr/bin/perl

# Below line will print
# "Welcome to GeeksforGeeks!"
print "Welcome to GeeksforGeeks!\n";
```

**输出:**

```
Welcome to GeeksforGeeks!
```

[**Ruby**](https://www.geeksforgeeks.org/ruby-programming-language-introduction/) 是由松本幸弘(在 Ruby 社区中也被称为 Matz)于 20 世纪 90 年代中期在日本开发的纯面向对象语言。Ruby 中的所有东西都是一个对象，除了块，但是也有它的替代物，即 `procs` 和 `lambda`。Ruby 开发的目标是让它成为人类程序员和底层计算机器之间的合理缓冲。Ruby 的语法类似于 C 和 Java 等许多编程语言，因此 Java 和 C 程序员很容易学习。它几乎支持所有平台，如视窗、苹果、Linux。

## Ruby

```ruby
# Simple Ruby program
puts "Welcome to GeeksforGeeks!"
```

**输出:**

```
Welcome to GeeksforGeeks!
```

### Perl 和 Ruby 的区别

| Perl | Ruby |
| :--- | :--- |
| Perl 是一种高级、通用、可解释、动态的编程语言。 | Ruby 是一种动态、面向对象和反射性的通用编程语言。 |
| 它是一种不太面向对象的语言。 | 它是一种纯粹且高度面向对象的语言。 |
| Perl 的库比 Ruby 少。 | 与 Perl 相比，Ruby 的库更多。 |
| 它对 Unicode 的支持比 Ruby 强得多。 | 它对 Unicode 的支持不如 Perl 强。 |
| Perl 的文件扩展名是 `.pl`。 | Ruby 使用文件扩展名 `.rb`。 |
| 说到支持正则表达式的它有非常多的库。 | 与 Perl 相比，它对正则表达式的支持较少。 |
| Perl 语言的框架是 `Catalyst`。 | Ruby 的框架是 `Ruby on Rails`。 |
| 支持多种变量类型。 | 它只有一种变量类型。 |
| Perl 执行速度非常快。 | Ruby 的脚本执行速度足够快。 |
| Perl 最常用于 `CGI`（通用网关接口）脚本中，与 C 一起用于 web 服务器，因此在服务器技术领域被广泛使用。 | Ruby 在元编程方面非常强大，这允许创建诸如 `Vagrant` 之类的神奇产品。 |