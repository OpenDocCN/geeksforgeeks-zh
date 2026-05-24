# Scala |上限

> 原文:[https://www.geeksforgeeks.org/scala-upper-bound/](https://www.geeksforgeeks.org/scala-upper-bound/)

Scala 对类型参数或类型变量有一些限制，即(类型界限)**上限**就是其中之一。通过实现类型界限，我们可以解释类型变量的约束，这些类型界限限制了类型变量的确定值，并揭示了关于这些类型的成员的更多细节。上限是在类型参数上定义的。
**语法**

```scala
[T <: S]
```

其中，‘T’是类型参数，‘S’是类型”【T <: s="" means="" this="" type="" parameter="" t="" must="" be="" either="" same="" as="" or="" sub-type="" of="" s.=""/>
我们用例子来理解上界。
**例**

```scala
// Scala Program To Demonstrate Scala Upper Bound
class GeeksforGeeks
class Author extends GeeksforGeeks
class Geeks extends Author

class ComputerSciencePortal
{
    // Declaration of upper bound
    def display [T <: Author](d : T)
    {
        println(d)
    }
}

// Object created
object ScalaUpperBounds
{
    // Driver code
    def main(args: Array[String])
    {

        val geeksforgeeks = new GeeksforGeeks
        val author = new Author
        val geeks = new Geeks

        val computerscienceportal = new ComputerSciencePortal

    // computerscienceportal.display(geeksforgeeks)
    computerscienceportal.display(geeks)
    computerscienceportal.display(author)
    }
}
```

**Output:**

```scala
Geeks@506e1b77
Author@4fca772d

```

这里，*上界*是在 ComputerSciencePortal 类中定义的，GeeksforGeeks 是作者的超级类，所以不接受。

**例**

```scala
// Scala Program To Demonstrate Scala Upper Bound
class  Principal
class Teacher extends Principal
class Student extends Teacher

class School
{
    // Declaration of upper bound
    def display [T <: Teacher](t: T)
    {
        println(t)
    }
}

// Object created
object ScalaUpperBounds
{
    // Driver code
    def main(args: Array[String])
    {
        // Defined new variable
        val principal = new Principal
        val teacher = new Teacher
        val student = new Student

        val school = new School

        // school.display(principal)
        school.display(teacher)
        school.display(student)
  }
}
```

**Output:**

```scala
Teacher@506e1b77
Student@4fca772d

```

这里我们已经定义了*上界*在类*学校*即【T <:教师】这意味着**显示**方法接受*教师*类对象或其子类(即学生)，这意味着教师的超类将不被接受。所以，如果老师的超级班级，即*校长*没有被评论，那么就会显示*类型不匹配*错误。