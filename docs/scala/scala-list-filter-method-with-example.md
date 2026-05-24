# Scala 列表过滤器()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-list-filter-method-with-example/](https://www.geeksforgeeks.org/scala-list-filter-method-with-example/)

**过滤器()**方法用于选择满足所述谓词的列表的所有元素。

> **方法定义:**def filter(p:(A)=>Boolean:List[A]
> 
> **返回类型:**它返回一个新列表，该列表由满足给定谓词的列表的所有元素组成。

**示例#1:**

```scala
// Scala program of filter()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(5, 12, 3, 13)

        // Applying filter method
        val result = m1.filter(_ < 10)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
List(5, 3)

```