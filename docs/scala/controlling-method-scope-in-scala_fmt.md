# Scala 中的控制方法范围

> 原文：[https://www.geeksforgeeks.org/controlling-method-scope-in-scala/](https://www.geeksforgeeks.org/controlling-method-scope-in-scala/)

顾名思义，[访问修饰符](https://www.geeksforgeeks.org/access-modifiers-in-scala/)有助于限制类、变量、方法或数据成员的范围。在 Scala 中控制方法范围有助于限制方法或数据成员的范围。Scala 中有五种类型的控制方法范围：

1.  公共范围
2.  私有范围
3.  受保护范围
4.  对象私有范围
5.  特定包装

## Public Scope

*   当没有为类、方法或数据成员指定访问修饰符时，默认情况下它被称为具有默认访问修饰符。
*   未使用任何访问修饰符声明的数据成员、类或方法（即具有默认访问修饰符）可以在任何地方通过包和导入或创建新实例来访问。

**示例：**

```scala
// Scala program of Public Scope
// package testA
class classA
{
    def method1(): Unit=
    {
        println("method1")
    }
}

// Creating object
object GfG
{ 
    // Main method
    def main(args: Array[String])
    {
        // classA in the same package 
        // as the main method 
        var x = new classA
        x.method1()
    }
}
```

**输出：**

```scala
method1
```

## Private Scope

*   `private`修饰符与 Java 中的 `private` 相同。通过将方法或变量标记为私有，当前类及其成员以及同一类的任何实例都可以使用它。
*   同一包的任何其他对象/类将无法访问私有成员。
*   这是通过使用 `private` 访问修饰符完成的。

**示例：**

```scala
// Scala program of Private Scope
// package testA
class classA 
{
    var x = 1
    private def method1: Unit =
    {
        println("method1")
    }
}

// Creating object
object GfG
{
    // Main method
    def main(arg: Array[String])
    {
        var obj1 = new classA
        printf("x = "+obj1.x)
        // println(obj1.method1) error: method 
        // method1 in class classA cannot 
        // be accessed in classA
    }
}
```

**输出：**

```scala
x = 1
```

## Protected Scope

*   Scala `protected` 不同于 Java 中的 `protected`。要将成员标记为受保护，请在类或变量前使用关键字 `protected`。
*   受保护的成员只能由同一包中的子类访问。

**示例：**

```scala
// Scala program of Protected Scope
// package test
class classab
{
    protected var ab: Int=4
    var ad: Int =1
}

// Creating object
object GfG extends classab
{ 
    // sub class
    // Main method
    def main(args: Array[String])
    {
        println(ab) //can be accessed
        println(ad) //can be accessed
    }
}
```

**输出：**

```scala

```

*   受保护的成员不能被其他包中的其他成员访问，即使使用了 `import`。

**示例：**

```scala
// Scala program of Protected Scope
// package testA
package testA
{
    class classA 
    {
        protected var ab: Int=4
        var ad: Int =1
    }
}

// another package testB
package testB
{
    // importing all the members 
    // from testA package
    import testA._

    // Creating object
    object GfG
    {
        // Main method
        def main(args: Array[String])
        {
            var ta= new classA
            ta.ad
            ta.ab //error
        }
    }
}
```

**输出：**

> 错误：类 classA 中的变量 ab 无法在 testA.classA 中访问
> 不允许访问受保护的方法 ab，因为 package testB 中的
> 封闭对象 GfG 不是 package testA 中定义了目标的
> 类 classA 的子类
> ta . ab//错误
> ^
> 发现一个错误

## Object Private/Protected Scope

*   对象私有与私有相同，唯一的区别是，成员声明的对象私有将仅在定义该成员时可用，即没有对象可以访问它，因此命名为对象私有。
*   受保护的对象与受保护的对象相同，唯一的区别是该成员仅在定义它的情况下或子类中可用，而对对象不可用。
*   要将成员对象标记为私有，请使用关键字 `private[this]`。
*   要将成员对象标记为受保护，请使用关键字 `protected[this]`，其中 `this` 指向当前对象。

**示例：**

```scala
// Scala program of Object Private/Protected Scope
// package test1.test11
class class11 
{
    private[this] var x = 1
    private var t = 2
    var z = 3
    def method11(other: class11): Unit =
    {
        println(x)
        println(t)
        println(z)
        // println(other.x)
        println(other.t)
        println(other.z)
    }
}
// here on line14 x can only be
// accessed from inside in which 
// it is defined

// Creating object
object GfG
{
    // Main method
    def main(arg: Array[String])
    {
        var obj11 = new class11() //current instance created
        var y = 2
        println(obj11.method11(obj11))
        println(obj11.z)
        //println(obj11.t) //error: t cannot be accessed
        //println(obj11.x) //error: x is not a member of class11
        //according to obj11 x is not a member
    }
}
```

**输出：**

```scala

()
```

## Package Specific

*   当我们希望一个成员可以享受整个套餐时。它来声明该成员为 `private[package_name]`。
*   包中的所有成员都可以访问该成员。
*   成员可以由名称被限定为的任何其他包访问。

**示例：**

```scala
// Scala program of Package Specific
package aa
class geek
{
    class g1
    {   
        // inner class
        // private to class g1
        private var a = 0
        // available to package aa
        private[aa] var b = 0 
        def method()
        {
            a = a + 1
            b = b + 1
            println("welcome to inner class g1")
            println("a= "+a)
        }
    }
}

// Creating object
object Main
{
    // Driver code
    def main(args: Array[String])
    {
        val obj = new geek()
        val o = new obj.g1
        o.method();
        println("b= "+o.b);
    }
}
```

**输出：**

```scala
welcome to inner class g1
a= 1
b= 1
```