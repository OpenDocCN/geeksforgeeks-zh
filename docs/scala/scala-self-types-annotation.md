# Scala |自身类型注释

> 原文:[https://www.geeksforgeeks.org/scala-self-types-annotation/](https://www.geeksforgeeks.org/scala-self-types-annotation/)

一个[特质](https://www.geeksforgeeks.org/scala-traits/)的一个**自身类型注释**是**这个**的假定类型，在一个特质内，被使用的接收者。任何融入特质的具体类都必须确保其自身类型符合被融入的特质。这意味着使用自身类型不会将局部变量和方法暴露给它的子类和子特征。把一个大班级分成几个特征是自我类型最常见的用法。自我类型是一种声明一个特征必须混合到另一个特征或类中的方式，即使它没有直接扩展它，这使得那些混合在特征中的依赖成员可以不导入。

要在性状中使用自我类型，在它旁边写下*标识符名称*，在它后面写下要混合的性状的*类型*，并跟随= >符号；如下所示。
**语法:**

```scala
trait A{
    //statements
}
trait B{
    this: A => //here we can use methods & variables of trait A
}

```

我们来讨论一些例子。
**例:**

```scala
// Scala Program that uses self type
trait with_powers
{ 
    var mind ="extra-ordinary"; 

}
trait without_powers
{
    var mind="ordinary";
}
trait person
{ 
    def brain();
}

// class extend trait
class extraordinary_person extends person
{   
    // reassign this
    this: with_powers => 
    override def brain() = println(s"super hero brain is $mind!");
}

// class extend trait
class ordinary_person extends person
{   
    // reassign this
    this: without_powers => 
    override def brain() = println(s"normal human brain is $mind.");
}

// Creating object
object GFG
{
    // Main method
    def main(args:Array[String])
    {
        val hero = new extraordinary_person() with with_powers;
        val mohan = new ordinary_person() with without_powers;

        //val mohan= new ordinary_person() with with_powers; ERROR
        //does not conform to ordinary_person's self type
        hero.brain();
        mohan.brain();
    }
}
```

**输出:**

```scala
super hero brain is extra-ordinary!.
normal human brain is ordinary.

```

在上面的例子中，我们创造了有力量、没有力量和人的特征。这里类非凡的人延伸特质的人。同样类普通人也延伸特质人。自我型标注发生在两个类中通过使用这个特质名=>
val mohan= new 平凡 _ person()with _ power；显示一个不符合普通人自我类型的错误。
**例:**

```scala
// Scala Program that uses self type
trait A
{ 
    def x = 1;
}

// trait extend another trait
trait B extends A
{
    override def x = super.x * 5;
}

// trait extend another trait
trait C1 extends B
{
    override def x = 2;
}

// trait extend another trait
trait C2 extends A
{ 
    this: B=> override def x = 2; 

}

// Creating object
object GFG
{
    // Main method
    def main(args:Array[String])
    {
        println((new C1 with B).x);
        println((new C2 with B).x);
    }
}
```

**输出:**

```scala
2
10

```

这里，在上面的例子中，C2 是一个抽象类型，C2 的自我类型与 B 是一致的。(新 C2 与 B)符合 C2 的自我类型与 B(这:B= >)所以，自我类型让你指定什么类型的特征被允许混合。

**示例:**

```scala
// Scala Program that uses self type
trait Being
{
    var name: String
    var age: Int
    var gender: String
}

// Creating trait
trait Sayings
{
    this: Being =>
    def greetings(greet: String) = println(s"$name: $greet");
    def info() = println(s"I am $age years old $gender");
}

// extend both trait with single class
class Person(var r_name: String, var r_age: Int, 
                            var r_gender: String)
extends Sayings with Being
{
    var name = s"Person $r_name";
    var age = r_age;
    var gender = r_gender;
}

// Creating object
object GFG
{
    // Main method
    def main(args: Array[String])
    {
        val person = new Person("Lakshya", 24, "Male");
        person.greetings("hello, hi there!!");
        person.info();
    }
}
```

**输出:**

```scala
Person Lakshya: hello, hi there!!
I am 24 years old Male

```

在上面的例子中(这个:Being = >)，它基本上意味着 Being 的变量名称、年龄、性别现在都在*问候*和*信息方法*的范围内，但是没有将它们暴露给扩展它的任何其他子类或特征。所以自我类型指定了任何具体类的需求，这种类型的特征应该被混合在其中。