# Scala List takeWhile()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-list-take while-method-with-example/](https://www.geeksforgeeks.org/scala-list-takewhile-method-with-example/)

只要满足所述条件，就利用 **takeWhile()** 方法从列表中找到元素。

> **方法定义:**def take while(p:(A)=>Boolean:List[A]
> 
> **返回类型:**只要满足所述条件，就从列表中返回元素。

**示例#1:**

```scala
// Scala program of takeWhile()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(1, 2, 3, 4, 5, 7)

        // Applying takeWhile method
        val result = m1.takeWhile(_ < 5)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
List(1, 2, 3, 4)

```

**例 2:**

```scala
// Scala program of takeWhile()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(1, 2, 3, 4, 5, 7)

        // Applying takeWhile method
        val result = m1.takeWhile(_ > 4)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
List()

```