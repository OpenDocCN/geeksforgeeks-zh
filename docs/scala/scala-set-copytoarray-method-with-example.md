# Scala Set copyToArray()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-set-copy to array-method-with-example/](https://www.geeksforgeeks.org/scala-set-copytoarray-method-with-example/)

**copyToArray()** 方法用于将集合的元素复制到数组中。

> **方法定义:** def copyToArray(xs: Array[A]，start: Int，len: Int): Unit
> **参数:**
> **xs:** 表示复制元素的数组。
> **start:** 表示复制发生的起始索引。其默认值为 0。
> **len:** 表示要复制的元素数量。它的默认值是集合的长度。
> **返回类型:**它将集合的元素返回到一个数组中。

**示例#1:**

## 斯卡拉

```scala
// Scala program of copyToArray()
// method

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {

        // Creating sets
        val s1 = Set(1, 2, 3)

        val arr: Array[Int] = Array(0, 0, 0, 0, 0)

        // Applying copyToArray method
        s1.copyToArray(arr)

        // Displays output
        for(elem <- arr) 
        println(elem)

    }
}
```

**Output:** 

```scala
1
2
3
0
0
```

**例 2:**

## 斯卡拉

```scala
// Scala program of copyToArray()
// method

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {

        // Creating sets
        val s1 = Set(1, 2, 3)

        val arr: Array[Int] = Array(0, 0, 0, 0, 0)

        // Applying copyToArray method
        s1.copyToArray(arr, 1, 2)

        // Displays output
        for(elem <- arr) 
        println(elem)

    }
}
```

**Output:** 

```scala
0
1
2
0
0
```