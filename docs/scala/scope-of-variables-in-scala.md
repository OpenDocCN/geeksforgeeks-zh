# Scala 中变量的范围

> 原文:[https://www.geeksforgeeks.org/scope-of-variables-in-scala/](https://www.geeksforgeeks.org/scope-of-variables-in-scala/)

变量声明指定将存储在内存中的变量的名称，并且可以使用该变量名称进一步访问内存。Scala 变量有三种作用域。

*   田野。
*   方法参数。
*   局部变量。

让我们详细讨论每一个。

<center>**菲尔兹**</center>

我们可以从对象中的每个方法访问这些类型的变量&如果我们用正确的访问修饰符声明了它们，就可以从对象外部访问它们。一个字段可以是*可变的*或*不可变的*，他们可以使用**【var】**或**【val】**来定义它们。
**示例:**

```scala
// Scala program of field 
// scope for Scala variable

// class created with field 
// variables x and y.
class disp 
{
    var x = 10.3f
    var y = 7f
    def windet() 
    {
        println("Value of x : "+x)
    }
        println("Value of y : "+y);
}

object Example 
{
    // Main method
    def main(args:Array[String]) 
    {
        val Example = new disp()
        Example.windet()
    }
}
```

**输出:**

```scala
Value of y : 7.0
Value of x : 10.3
```

上面的例子显示 disp 类是用字段变量 x 和 y 创建的。这些变量可以在方法中访问，并通过创建引用从对象中调用。因此，下面是获得的输出。

<center>**方法参数**</center>

当我们想要在调用方法时在方法内部传递一个值时，我们使用这些变量。如果有从方法外部对对象的引用，则可以在方法内部和方法外部访问它们。这些变量*总是可变的*与**【瓦尔】**关键字一起使用。

**示例:**

```scala
// Scala program of Method 
// scope for Scala variable

// class created with Method 
// variables s1 and s2.
class rect 
{
    def mult(s1: Int, s2: Int)
    {
        var result = s1 * s2
       println("Area is: " + result);
    }
}

object Area 
{
    // Main method
    def main(args:Array[String])
    {
        val su = new rect()
        su.mult(5, 10)
    }
}
```

**输出:**

```scala
Area is: 50
```

上例显示`rect class` 是通过`mult method`接受两个方法参数变量 s1 和 s2 而创建的。创建 Area 对象，并通过将值传递给变量 s1 和 s2 来调用 rect 方法。因此，下面是获得的输出。

<center>**【本地变量】**</center>

这些类型的变量在方法内部声明，并且只能在方法内部访问。使用**‘var’**&**‘val’**关键词，这些变量既可以是*可变的&也可以是不可变的*。

**示例:**

```scala
// Scala program of Method 
// scope for Scala variable

// class created with Local
// variables s1 and s2.
class Area 
{
    def mult() 
    {
        var(s1, s2) = (3, 80);
        var s = s1 * s2;
        println("Area is: " + s)
    }
}

object Test 
{
    // Main method
    def main(args:Array[String]) 
    {
        val ex = new Area()
        ex.mult()
    }
}
```

**输出:**

```scala
Area is: 240
```

上面的例子显示了类 Area 在方法 mult 中有局部变量 s1，s2 & s。这些变量在方法之外是不可访问的。因此获得的输出如下。