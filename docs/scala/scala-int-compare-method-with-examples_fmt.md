# 带示例的标量积分比较方法

> 原文：`https://www.geeksforgeeks.org/scala-int-compare-method-with-examples/`

`compare`是Scala中一个`Int`类方法，用于将其与操作数进行比较。

## 语法

> **语法：**`（给定_值1）.compare（给定_值2）`
>
> **返回：**当`给定_值1`小于`给定_值2`时，返回`-1`。当两个值相等时，返回`0`。当`给定_值1`大于`给定_值2`时，返回`1`。

## 例 1

```scala
// Scala Program to demonstrate the
// compare method of Int class

object GfG
{

    // Main Method
    def main(args:Array[String])
    {

        // Applying the method
        val v1 = (451).compare(145)

        // Displaying the output
        println(v1)

    }
}
```

**Output:**

```scala

```

## 例 2

```scala
// Scala Program to demonstrate the
// compare method of Int class

object GfG
{

    // Main Method
    def main(args:Array[String])
    {

        // Applying the method
        val v1 = (121).compare(1478)

        // Displaying the output
        println(v1)

    }
}
```

**Output:**

```scala

```