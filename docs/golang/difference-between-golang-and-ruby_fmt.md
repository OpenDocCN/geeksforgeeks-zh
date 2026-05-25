# 格朗和红宝石的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-golang-and-ruby/](https://www.geeksforgeeks.org/difference-between-golang-and-ruby/)

在进入一个新的项目之前，软件开发团队会进行严格的讨论，以便为他们的项目选择最好的语言。正如我们所意识到的，不同的技术各有利弊，同样，一个项目看起来充满活力的技术可能是其他项目所缺乏的。这就是为什么宣称某个特定的东西没有价值是不合理的。但是在本文中，我们将讨论两种语言之间的基本差异。

## [戈朗](https://www.geeksforgeeks.org/golang/)

它是由罗伯特·格里森、罗布·派克和肯·汤普森在谷歌设计的一种静态类型和编译的编程语言。它的开发始于 2007 年的谷歌，并于 2009 年向公众推出。它是开源的，可供公众使用。`Go` 在语法上类似于 `C`，这将消除诸如 `C++` 等语言的“无关垃圾”。因此，`Go` 包含了其他现代语言的许多特性，例如方法和运算符重载、指针算法和类型继承。它提供了并发机制，使得开发面向多核和网络的机器级程序变得容易。这是一种具有丰富库的解释型快速执行语言。这种语言经常被称为“`Golang`”，因为它的域名是 `golang.org`，但这种语言的专有名称是 `Go`。

### 走

```go
// Simple Go program
package main

import "fmt"

func main() {
    var a int = 100

    if(a < 2000) {
        fmt.Printf("a is less than 2000\n")
    } else {
        fmt.Printf("a is greater than 2000\n")
    }
}
```

**输出：**

```go
a is less than 2000
```

## [Ruby](https://www.geeksforgeeks.org/ruby-programming-language/)

它是一种开源的**面向对象编程**语言，本质上是动态的。`Ruby` 有一个非常简洁的语法，读起来很自然，写起来也很容易。它是由日本的松本幸弘(Yukihiro Matz)于 1990 年创建的，他将自己最喜欢的语言(即 `Perl`、`Smalltalk`、`Eiffel`、`Ada` 和 `Lisp`)的各个部分结合起来，以形成一种平衡函数式编程和命令式编程的新语言。`Ruby` 是一种从头开始构建的脚本语言，用于前端和后端 `web` 开发以及类似的应用程序。它是一种健壮的、动态类型的、面向对象的语言，语法非常容易理解，是一种高级语言。它于 1995 年发布供公众使用。

### 红宝石

```ruby
# Simple Ruby program
marks = 20

if marks >= 50
    puts "Candidate has cleared the examination!"
else
    puts "Candidate hasn't cleared the examination!"
end
```

**输出：**

```ruby
Candidate hasn't cleared the examination!
```

## 格朗(Go)和鲁比的区别

| 特性 | Golang (Go) | Ruby |
| :--- | :--- | :--- |
| **开发者** | 由 Rob Pike、Robert Griesemer 和 Ken Thompson 的团队于 2009 年在美国谷歌开发。 | 由松本幸弘(Matsumoto)于 1991 年在日本开发。 |
| **类型系统** | 静态类型语言。 | 动态类型语言。 |
| **测试适用性** | 在较大程度上不适合测试目的，因为它没有像 `Ruby` 那样的属性。 | 从测试角度来看是最好的选择，因为 `Ruby` 拥有出色的测试框架，并且它也是基于敏捷方法的项目开发。 |
| **执行速度** | 在速度方面胜过 `Ruby`，是一种比 `Ruby` 快得多的编程语言。 | 没有像 `Ruby Golang` 这样快的编程语言，因为 `Golang` 不需要解释执行。 |
| **面向对象** | 不是完全的面向对象语言，但 `Go` 所拥有的类型和方法允许它充当轻度的面向对象编程。 | 纯粹的面向对象语言。 |
| **内存管理** | 具有自动内存管理，称为自动垃圾回收和自动内存分配。 | 内存分配通过定期释放小池来排序。 |
| **擅长领域** | 是解决复杂和简单的多线程任务的首选。 | 擅长创建小型商业博客、商业项目和个人页面。 |
| **知名应用** | `Yi Bei`、`Uber` 和谷歌自身都是使用 `Golang` 开发的。 | `Airbnb`、`Github` 和 `Shopify` 都是使用 `Ruby` 开发的 `web` 应用程序示例。 |
| **代码量** | 与另一个基于 `C` 的语言相比，编写相同的代码需要更多的行数。 | 具有简单干净的语法，更易于阅读和编写。 |