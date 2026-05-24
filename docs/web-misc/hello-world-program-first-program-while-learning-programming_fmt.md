# 你好世界程序：学习编程时的第一个程序

> 原文：[https://www.geeksforgeeks.org/hello-world-program-first-program-while-learning-programming/](https://www.geeksforgeeks.org/hello-world-program-first-program-while-learning-programming/)

这篇文章向我们介绍了如何编写第一个跨多种语言的“你好，世界”计算机程序。与程序一起，提供注释是为了更好地理解程序中使用的术语和关键词。

学习任何编程语言都可以简化为：

*   在文本编辑器中编写程序，并以正确的扩展名保存它（`.cpp`、`.c`、`.cs`、`.java` 等）。
*   使用编译器或[在线 IDE](https://ide.geeksforgeeks.org/) 编译程序。
*   理解基本术语。

“你好世界”程序是学习任何编程语言的第一步，也是你将学习的最简单的程序之一。你所要做的就是在屏幕上显示信息“你好，世界”。现在让我们看看大多数语言的程序。

以下是所有不同语言的“Hello World”程序的链接：

1.  [**C 语言中的 Hello World**](https://www.geeksforgeeks.org/c-hello-world-program/)

## C

```c
// Simple C program to
// display "Hello World"

// Header file for
// input output functions
#include <stdio.h>

// main function -
// where the execution of
// program begins
int main()
{

    // prints hello world
    printf("Hello World");

    return 0;
}
```

2.  [**C++ 中的 Hello World**](https://www.geeksforgeeks.org/writing-first-c-program-hello-world-example/)

## C++

```cpp
// Simple C++ program to
// display "Hello World"

// Header file for
// input output functions
#include <iostream>

using namespace std;

// main function -
// where the execution of
// program begins
int main()
{
    // prints hello world
    cout << "Hello World";

    return 0;
}
```

3.  [**C# 中的 Hello World**](https://www.geeksforgeeks.org/hello-world-in-c-sharp/)

## C#

```csharp
// C# program to print Hello World!

using System;

// namespace declaration
namespace HelloWorldApp {

// Class declaration
class Geeks {

    // Main Method
    static void Main(string[] args)
    {

        // statement
        // printing Hello World!
        Console.WriteLine("Hello World");

        // To prevents the screen from
        // running and closing quickly
        Console.ReadKey();
    }
}
}
```

4.  [**Java 中的 Hello World**](https://www.geeksforgeeks.org/beginning-java-programming-with-hello-world-example/)

## Java

```java
// This is a simple Java program.
// FileName : "HelloWorld.java"

class HelloWorld {

    // Your program begins
    // with a call to main().
    // Prints "Hello, World"
    // to the terminal window.
    public static void main(
        String args[])
    {
        System.out.println("Hello World");
    }
}
```

5.  [**Python 中的 Hello World**](https://www.geeksforgeeks.org/python-3-basics/)

## Python

```python
# Python code for "Hello World"

print("Hello World")
```

6.  [**Perl 中的 Hello World**](https://www.geeksforgeeks.org/hello-world-program-in-perl/)

## Perl

```perl
#!/usr/bin/perl

# Modules used
use strict;
use warnings;

# Print function
print("Hello World\n");

# To run the code refer:
# http://bit.ly/2qLYVTG
```

7.  [**Scala 中的 Hello World**](https://www.geeksforgeeks.org/hello-world-in-scala/)

## Scala

```scala
// Scala program to print Hello World!

object Geeks
{

    // Main Method
    def main(args: Array[String])
    {

        // prints Hello World
        println("Hello World")
    }
}
```

8.  [**Go 语言中的 Hello World**](https://www.geeksforgeeks.org/hello-world-in-golang/)

## Go

```go
// Go program to print Hello World!

package main

    import "fmt"

    // Main function
    func
    main()
{

    // prints Hello World
    fmt.Println("!... Hello World ...!")
}
```

9.  [**PHP 中的 Hello World**](https://www.geeksforgeeks.org/php-basic-syntax/)

## PHP

```php
<!DOCTYPE html>
<html>
<body>

<?php
echo "Hello World";
?>

</body>
</html>
```

10. [**HTML 中的 Hello World**](https://www.geeksforgeeks.org/html-course-first-web-page-printing-hello-world/)

## HTML

```html
<html>
<header><title></title></header>
<body>
Hello World
</body>
</html>
```

11. [**JavaScript 中的 Hello World**](https://www.geeksforgeeks.org/javascript-course-printing-hello-world-in-javascript/)

## JavaScript

```javascript
<script>

// using console.log
console.log('Hello World');
</script>
```

12. [**Julia 中的 Hello World**](https://www.geeksforgeeks.org/hello-world-in-julia/)

## Julia

```julia
// Julia program
println("Hello World")
```

13. [**R 语言中的 Hello World**](https://www.geeksforgeeks.org/hello-world-in-r-programming/)

## R

```r
# Code
cat('Hello World')
```

14. [**Ruby 中的 Hello World**](https://www.geeksforgeeks.org/hello-world-in-ruby/)

## Ruby

```ruby
# code
puts "Hello World"
```

15. **Solidity 中的 Hello World**

## Solidity

```solidity
pragma solidity ^0.5.0;

contract helloGeeks {
 function renderHelloGeeks () public pure returns (string) {
   return 'Hello World';
 }
}
```

16. **XML 中的 Hello World**

## XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<text>
  <para>Hello World</para>
</text>
```

17. **Objective-C 中的 Hello World**

## Objective-C

```objective-c
#import
#import

int main(void)
{
    NSLog(@"Hello World
");
    return 0;
}
```

18. **Kotlin 中的 Hello World**

## Kotlin

```kotlin
fun main(args: Array<String>) {
    println("Hello World")
}
```

19. **Dart 中的 Hello World**

## Dart

```dart
void main() {
  print('Hello World');
}
```

以下是所有语言的代码汇总：

## C

```c
// Simple C program to
// display "Hello World"

// Header file for
// input output functions
#include <stdio.h>

// main function -
// where the execution of
// program begins
int main()
{

    // prints hello world
    printf("Hello World");

    return 0;
}
```

## C++

```cpp
// Simple C++ program to
// display "Hello World"

// Header file for
// input output functions
#include <iostream>

using namespace std;

// main function -
// where the execution of
// program begins
int main()
{
    // prints hello world
    cout << "Hello World";

    return 0;
}
```

## C#

```csharp
// C# program to print Hello World!

using System;

// namespace declaration
namespace HelloWorldApp {

// Class declaration
class Geeks {

    // Main Method
    static void Main(string[] args)
    {

        // statement
        // printing Hello World!
        Console.WriteLine("Hello World");

        // To prevents the screen from
        // running and closing quickly
        Console.ReadKey();
    }
}
}
```

## Java

```java
// This is a simple Java program.
// FileName : "HelloWorld.java"

class HelloWorld {

    // Your program begins
    // with a call to main().
    // Prints "Hello, World"
    // to the terminal window.
    public static void main(
        String args[])
    {
        System.out.println("Hello World");
    }
}
```

## Python

```python
# Python code for "Hello World"

print("Hello World")
```

## Perl

```perl
#!/usr/bin/perl

# Modules used
use strict;
use warnings;

# Print function
print("Hello World\n");

# To run the code refer:
# http://bit.ly/2qLYVTG
```

## 斯卡拉

```scala
// Scala program to print Hello World!

object Geeks
{

    // Main Method
    def main(args: Array[String])
    {

        // prints Hello World
        println("Hello World")
    }
}
```

## 超文本标记语言

```html
<html>
<header><title></title></header>
<body>
Hello World
</body>
</html>
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```php
<!DOCTYPE html>
<html>
<body>

<?php
echo "Hello World";
?>

</body>
</html>
```

## 朱莉娅

```julia
println("Hello World")
```

## 红宝石

```ruby
puts "Hello World"
```

## 稀有

```r
cat('Hello World')
```

## 去

```go
package main

import "fmt"

// Main function
func main() {

    fmt.Println("Hello World")
}
```

## java 描述语言

```javascript
<script>

// using console.log
console.log('Hello World');
</script>
```

## 固态

```solidity
pragma solidity ^0.5.0;

contract helloGeeks {
 function renderHelloGeeks () public pure returns (string) {
   return 'Hello World';
 }
}
```

## 可扩展标记语言

```xml
<?xml version="1.0" encoding="UTF-8"?>
<text>
  <para>Hello World</para>
</text>
```

## 客观的

```objectivec
#import
#import

int main(void)
{
    NSLog(@"Hello World
");
    return 0;
}
```

## 我的锅

```kotlin
fun main(args: Array<String>) {
    println("Hello World")
}
```

## 镖

```d
void main() {
  print('Hello World');
}
```

输出:

```text
Hello World
```