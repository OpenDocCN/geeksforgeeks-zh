# 格朗和红宝石的区别

> 原文:[https://www . geesforgeks . org/golang-and-ruby 之间的差异/](https://www.geeksforgeeks.org/difference-between-golang-and-ruby/)

在进入一个新的项目之前，软件开发团队会进行严格的讨论，以便为他们的项目选择最好的语言。正如我们所意识到的，不同的技术各有利弊，同样，一个项目看起来充满活力的技术可能是其他项目所缺乏的。这就是为什么宣称某个特定的东西没有价值是不合理的。但是在本文中，我们将讨论两种语言之间的基本差异。

[**【戈朗】**](https://www.geeksforgeeks.org/golang/) **<u>:</u>** 它是由罗伯特·格里森、罗布·派克和肯·汤普森在谷歌设计的一种静态类型和编译的编程语言。它的开发始于 2007 年的谷歌，并于 2009 年向公众推出。它是开源的，可供公众使用。Go 在语法上类似于 C，这将消除诸如 C++等语言的“无关垃圾”。因此，Go 包含了其他现代语言的许多特性，例如方法和运算符重载、指针算法和类型继承。它提供了并发机制，使得开发面向多核和网络的机器级程序变得容易。这是一种具有丰富库的解释型快速执行语言。这种语言经常被称为“Golang”，因为它的域名是 golang.org，但这种语言的专有名称是 Go。

## 走

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

**输出:**

```go
a is less than 2000

```

[**【Ruby】**](https://www.geeksforgeeks.org/ruby-programming-language/)**:**它是一种开源的**面向对象编程**语言，本质上是动态的。Ruby 有一个非常简洁的语法，读起来很自然，写起来也很容易。它是由日本的松本幸弘(Yukihiro Matz)于 1990 年创建的，他将自己最喜欢的语言(即 Perl、Smalltalk、Eiffel、Ada 和 Lisp)的各个部分结合起来，以形成一种平衡函数式编程和命令式编程的新语言。Ruby 是一种从头开始构建的脚本语言，用于前端和后端 web 开发以及类似的应用程序。它是一种健壮的、动态类型的、面向对象的语言，语法非常容易理解，是一种高级语言。它于 1995 年发布供公众使用。

## 红宝石

```go
# Simple Ruby program
marks = 20

if marks >= 50
    puts"Candidate has cleared the examination!"
else 
  puts"Candidate hasn't cleared the examination!"
end
```

**输出:**

```go
Candidate hasn't cleared the examination!

```

## **格朗(Go)和鲁比** 的区别

<figure class="table">

| 

<u>Go</u>lang(Go)

 | 

Ruby

 |
| --- | --- |
| Golang was developed in Google in 2009 by the teams of Rob Pike, Robert Griesemer and Ken Thompson in the United States. | Ruby was developed by one person, Matsumoto, in Japan in 1991 by Jihong "Matz". |
| It is a static type of language. | Is a dynamic type language. |
| Golang is not suitable for testing purposes to a greater extent, because it does not have attributes like Ruby. | Ruby is the best if there is a requirement from the perspective of testing, because Ruby has a great testing framework, and it is also an agile methodology based on project development. |
| In terms of speed, Golang beat Ruby, a programming language much faster than Ruby. | There is no programming language as fast as Ruby Golang, because Golang does not need to explain. |
| Golang is not a completely object-oriented language, but the types and methods possessed by Go allow it to act as a mild object-oriented programming. | Ruby is a pure object-oriented language. |
| Golang has automatic memory management, which is called automatic garbage collection and automatic memory allocation. | Ruby, the memory allocation is sorted from time to time with the release of small pools. |
| Golang is the first choice to solve complex and simple multithreaded tasks. | Good at creating small business blogs, business projects and personal pages. |
| Dropbox of Yi Bei, Uber and Google itself are all developed by using Golang. | Airbnb, Github and Shopify are all examples of web applications developed using Ruby. |
| Compared with another C-based language, writing the same code requires more lines. | It has a simple and clean grammar and is easier to read and write. |

</figure>