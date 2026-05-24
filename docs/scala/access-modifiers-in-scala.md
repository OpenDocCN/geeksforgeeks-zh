# Scala 中的访问修饰符

> 原文:[https://www.geeksforgeeks.org/access-modifiers-in-scala/](https://www.geeksforgeeks.org/access-modifiers-in-scala/)

**scala 中的访问修饰符**用于定义 Scala 中包、类或对象成员的访问字段。要使用访问修饰符，必须在包、类或对象的成员定义中包含它的关键字。这些修饰符将把对成员的访问限制在代码的特定区域。
Scala 中有三种类型的访问修饰符:

1.  私人的
2.  保护
3.  公众

**表:**

| 修饰语 | 班级 | 同伴 | 亚纲 | 包裹 | 世界 |
| --- | --- | --- | --- | --- | --- |
| 不修改/公开 | 是 | 是 | 是 | 是 | 是 |
| **受保护** | 是 | 是 | 是 | 否* | 不 |
| **私人** | 是 | 是 | 不 | 否* | 不 |

 **上表中的同伴是什么？**它是一个与类同名的单例对象。

**1。私有:**当一个成员被声明为私有时，我们只能在定义类内部或者通过它的一个对象来使用它。

**示例:**

```scala
// Scala program of private access modifier
class abc
{ 
    private var a:Int = 123
    def display()
    {
        a = 8
        println(a)
    }
}

object access extends App
{
    // class abc is accessible 
    // because this is in the same enclosing scope
    var e = new abc()
    e.display()
}
```

**输出:**

```scala
8
```

这里我们声明了一个变量“a”private，现在只能在它的定义类中或者通过 class 对象来访问它。

**2。受保护:**它们只能从定义了成员的基类的子类中访问。

**示例:**

```scala
// Scala program of protected access modifier

class gfg
{ 
    // declaration of protected member
    protected var a:Int = 123
    def display()
    {
        a = 8
        println(a)
    }
}

// class new1 extends by class gfg
class new1 extends gfg
{
    def display1()
    {
        a = 9
        println(a)
    }
}

object access extends App
{
    // class abc is accessible because this
    // is in the same enclosing scope
    var e = new gfg()
    e.display()
    var e1 = new new1()
     e1.display1()

}
```

**输出:**

```scala
8
9
```

当我们在类 new1 中扩展 abc 时，受保护变量 a 现在可以被修改，因为 new1 是类 abc 的子类。

**3。public:**Scala 中没有 **public** 关键字。默认访问级别(未指定修饰符时)对应于 Java 的公共访问级别。我们可以在任何地方找到这些。

```scala
// Scala program of protected access modifier

class gfg
{
    var a:Int = 123
}
object access extends App
{
    var e = new gfg()
    e.a = 444    
    println(e.a)
}
```

**输出:**

```scala
444
```