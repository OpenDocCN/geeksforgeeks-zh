# Scala 中的链式包装条款

> 原文:[https://www . geesforgeks . org/chained-package-子句-in-scala/](https://www.geeksforgeeks.org/chained-package-clauses-in-scala/)

**是解决包成员可见性的方法。这是由 Martin Odersky 在 Scala 2.8 中介绍的，假设我们有如下代码。**

**让我们破解代码，了解这里发生了什么。**

```scala
package x.z
object a {
  b  //object b
}
object b{
  a  //object a
} 
```

**或者我们可以编写如下代码**

```scala
// but this is not a good and short way of writing package clauses
// let's just stick to the first style.
package x{
   package z{
      object a {
      }
      object b{
      }
  }
} 
```

**这里对象 a 和 b 是在目录 x 中的目录 z 中定义的。包 z 的可见性是成员 a 和 b，而不是成员 x。我们还可以将这些对象写入不同的 scala 文件，如下所示。**

```scala
// a.scala
package x.z
object a {
  b //object b still visible
} 
```

```scala
// b.scala
package x.z
object b{
  a // object a still visible
} 
```

```scala
// files would created like this
+x
  +z
    +a.scala
    +b.scala 
```

****Why the chaining of package clauses were introduced?****

**更改 package 子句的含义，并在导入文件时缩短 package 子句，以便我们在处理包含多个不同嵌套子包的较大项目时不必编写整个包名。**

**让我们用一个 eg 来理解它，它的目录结构是这样的**

```scala
+company
      +ceo
         +Ceo.scala
         +directors
               +Director.scala
               +managers
                     +hrManager.scala
                     +techManager.scala
                     +employees
                             +employee.scala 
```

```scala
// employee.scala
package company.ceo.directors.managers

package employees{
    object employee extends Enumeration{
      val employee1= Value
      val employee2= Value
      val employee3= Value
    }
} 
```

```scala
// hrManager.scala
package company.ceo.directors.managers

//short form to import employee3
**import employees.employee.employee3**  
object hrManager extends Enumeration{
  val hR1, hR2 = Value
  val hrAssociate= employee3
} 
```

```scala
// techManager.scala
package company.ceo.directors.managers

// short form to import employee1
**import employees.employee.employee1**  
object techManager extends Enumeration{
val tmanager= Value
val techAssociate=employee1

// directly specifying employee2
val Assistant= employees.employee.employee2  
val x=Director
} 
```

**所以在上面的文件中不要写如下的整个 package 子句。**

> **import company . CEO . directors . manager . employee . employee 1//tech manager . Scala
> import company . CEO . directors . manager . employee . employee 2//tech manager . Scala
> import company . CEO . directors . manager . employee . employee 3//hrmanager . Scala**

**我们编写了目录名，它与导入的文件在当前/相同的基础上**

```scala
+hrManager.scala        //file
+techManager.scala      //file
+employees              //directory 
```

**这 3 个文件在同一范围内，因此我们在范围内看到**人力资源经理**或**技术经理**或**员工**，因此我们使用它们&在范围内看不到其他文件。因此，对于导入多个文件，我们可以在点的末尾包含一个' _ '来导入所有成员，而无需指定所有成员。从第一个例子中，对象 a &和对象 b 处于同一级别的范围内，因此我们可以看到并使用它们。**