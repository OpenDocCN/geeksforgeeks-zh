# Scala List dropWhile()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-list-drop while-method-with-example/](https://www.geeksforgeeks.org/scala-list-dropwhile-method-with-example/)

**dropWhile()** 方法用于丢弃满足所述条件的元素的最长前缀。

> **方法定义:**def drop while(p:(A)=>Boolean:List[A]
> 
> **返回类型:**返回列表中除删除元素以外的所有元素。

**示例#1:**

```scala
// Scala program of dropWhile()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(1, 3, 5, 4, 2)

        // Applying dropWhile method
        val res = m1.dropWhile(x=>{x % 2 != 0})

        // Displays output
        println(res)

    }
}
```

**Output:**

```scala
List(4, 2)

```

**例 2:**

```scala
// Scala program of dropWhile()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(3, 6, 5, 4, 2)

        // Applying dropWhile method
        val res = m1.dropWhile(x=>{x % 3 == 0})

        // Displays output
        println(res)

    }
}
```

**Output:**

```scala
List(5, 4, 2)

```