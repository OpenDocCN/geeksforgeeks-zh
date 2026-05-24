# 斯卡拉包装

> 原文:[https://www.geeksforgeeks.org/packages-in-scala/](https://www.geeksforgeeks.org/packages-in-scala/)

Scala 中的 Package 是一种封装一组类、子包、特征和包对象的机制。它基本上提供了命名空间，将我们的代码放在不同的文件和目录中。包是维护代码的一种简单方法，可以防止不同包的成员之间的命名冲突。为包的成员提供访问控制，如私有的、受保护的、特定于包的控制范围，限制了成员对其他包的访问，而没有修饰符的成员可以在任何其他有引用的包中使用。

#### 包装声明

包被声明为 Scala 文件顶部的第一条语句。
**语法:**

```scala
package package_name
// Scala classes
// traits
// objects..

```

定义包可以用不同的方式完成:-

*   [**Chained methods**](https://www.geeksforgeeks.org/chained-package-clauses-in-scala/)

    ```scala
    package x.y.z
    // members of z

    ```

    或者可以用作:-

    ```scala
    package x
    package y
    package z
    // member of z

    ```

*   **筑巢包**

    ```scala
    package x{
       // members of x {as required}
       package y{
          // members of y{as required}
          package z{
             // members of z{as required}
          }
       }
    }

    ```

#### 包是如何工作的

包将数据绑定在一个文件中，或者作为数据封装，当保存一个文件时，它位于默认包下或文件顶部指定的包名下。包名和目录结构密切相关。例如，如果包名是 college.student.cse，那么将有 3 个目录，college、student 和 cse。使得 cse 存在于学生中，学生存在于大学中。

```scala
college
     +student
          +cse

```

这样做的目的是确保在使用包时，文件在目录中很容易找到。
域名的包命名约定与 org . geesforgeks . practice、org . geesforgeks . contribute 的顺序相反。

#### 向包中添加成员

我们可以在一个包中添加任意数量的成员，比如类、子类、特征、包含主方法和子包的对象。与 java 包不同，我们可以在不同的 scala 文件中添加一个声明的包，也就是说，可以为同一个包编写不同的 scala 文件。
**例:**

```scala
// file named as faculty.scala
package college
class faculty{
   def faculymethod(){}
}

```

```scala
// file named as student.scala
// containing the main method

// using the college package name again
package college 
class student
{
    def studentmethod(){}
} 

// Creating object
object Main
{

    // Main method
    def main(args: Array[String])
    {
        val stu= new student()
        val fac= new faculty() 
        // faculty class can be accessed while
        // in different file but in same package.
    }
}
```

目录结构中实际创建的内容如下

```scala
college
     +faculty.scala
     +student.scala

```

#### 使用包

包可以在程序中以不同的方式使用。Scala 中的 Import 子句比 java 中的更灵活。比如 import 子句可以在程序中的任何地方作为独立语句使用，在程序中使用关键字 **import** ，Java 不允许这样。

```scala
// base.scala
// bb directory
package bb 

// creating a class
class geek
{ 
    private var id=0
    def method()
    {
        println("welcome to geek class")
        println("id="+id)
    }
} 
```

下面是使用导入条款的包的示例。

```scala
// main.scala
// aa directory
package aa 

// Creating object
object Main
{
    // Main method
    def main(args: Array[String])
    {
        // importing in main method
        import bb.geek 

        // using the member injected using import statement
        val obj = new geek() 
        obj.method();
    }
}
```

#### 使用导入语句的不同方式

*   正在导入包的所有公共成员。

    ```scala
    import college._
    //imports all college members students, faculties, houseKeeping etc.

    ```

*   仅导入包中选定的成员。

    ```scala
    import college.{faculty, houseKeeping}
    //member student is not selected hence cannot be used in current file

    ```

*   导入并重命名成员。

    ```scala
    import college.{student => stu}
    //stu is used in-place of student

    ```