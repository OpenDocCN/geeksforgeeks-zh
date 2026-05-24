# Scala 映射包含()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-map-contains-method-with-example/](https://www.geeksforgeeks.org/scala-map-contains-method-with-example/)

Scala 的 **contains()** 方法相当于 Scala 的 *isDefinedAt* 方法，但唯一的区别是在所有 *PartialFunction* 类上都观察到了 *isDefinedAt* ，而 *contains* 则明确定义到 Scala 的 *Map* 界面。它检查所述映射是否包含密钥绑定。

*   **Method Definition:**

    ```scala
    def contains(key: K): Boolean

    ```

    其中， *k* 是关键。

*   **返回类型:**
    如果所述映射中的键有绑定，则返回真，否则返回假。

**示例:**

```scala
// Scala program of contains()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val map: Map[Int,Int] = Map(2 -> 3)

        // Applying contains method
        val result = map.contains(2)

        // Displays output
        println(result)

    }
}                                         

```

**Output:**

```scala
true

```

这里，*包含*方法有一个与上述地图中存在的键相同的键，因此，它返回 true。
T3】例:

```scala
// Scala program of contains()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val map: Map[Int,Int] = Map(4 -> 7)

        // Applying contains method
        val result = map.contains(5)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```

这里，*包含*方法有一个与上述地图中存在的键不同的键，因此它返回 false。