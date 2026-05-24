# Scala map isDefinedAt()方法示例

> 原文:[https://www . geesforgeks . org/Scala-map-is definedat-method-with-example/](https://www.geeksforgeeks.org/scala-map-isdefinedat-method-with-example/)

方法**是*部分函数*的抽象值成员，与方法*包含*相同，在*部分函数*的所有类中都可以观察到。它检查一个值是否包含在函数的域中。**

*   **Method Definition:**

    ```scala
    abstract def isDefinedAt(x: A): Boolean

    ```

    其中， **x** 为待测值。

*   **返回类型:**
    如果 **x** 出现在该函数的域中，则返回真，否则返回假。

**示例:**

```scala
// Scala program of isDefinedAt()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating partial function
        val par : PartialFunction[Int,Int] =
        { 
            case 1 => 1
        }

        // Applying isDefinedAt() method
        val result = par.isDefinedAt(1)

        // Displays output
        println(result)

    }
}                                         

```

**Output:**

```scala
true

```

这里，值，即上面定义的 *x* 存在于函数域中，所以它返回真。
T3】例:

```scala
// Scala program of isDefinedAt()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val map: Map[Int,Int] = Map(2 -> 3)

        // Applying isDefinedAt() method
        val result = map.isDefinedAt(5)

        // Displays output
        println(result)

    }
}     
```

**Output:**

```scala
false

```

这里，上面定义的值，即 *x* 不存在于函数域中，所以它返回假。