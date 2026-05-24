# Scala List filterNot()方法示例

> 原文:[https://www . geesforgeks . org/Scala-list-filter not-method-with-example/](https://www.geeksforgeeks.org/scala-list-filternot-method-with-example/)

**filterNot()** 方法用于选择列表中不满足所述谓词的所有元素。

> **方法定义:**def filter not(p:(A)=>Boolean:List[A]
> 
> **返回类型:**它返回一个新列表，该列表包含列表中不满足给定谓词的所有元素。

**示例#1:**

```scala
// Scala program of filterNot()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(5, 12, 3, 13)

        // Applying filterNot method
        val result = m1.filterNot(_ < 10)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
List(12, 13)

```

**例 2:**

```scala
// Scala program of filterNot()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(5, 12, 3, 13)

        // Applying filterNot method
        val result = m1.filterNot(_ < 3)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
List(5, 12, 3, 13)

```