# Scala 字符串拆分(字符串正则表达式，int limit)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-string-split string-regex-int-limit-method-with-example/](https://www.geeksforgeeks.org/scala-string-splitstring-regex-int-limit-method-with-example/)

**split(String regex，int limit)** 方法与 split(String，regex)方法相同，但这里唯一的区别是您可以限制结果数组中的元素数量。

> **方法定义:**字符串[]拆分(字符串正则表达式，int 限制)
> 
> **返回类型:**它返回一个字符串数组，其中指定了数组中的元素数量，数组的最后一个元素是所述字符串中剩余的部分。

**例:1#**

```scala
// Scala program of split()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying split method
        val result = "PfsoQmsoRcsoGfGkso".split(".so", 3)

        for ( m1 <-result ) 
        {
            // Displays output
            println(m1)
        }

    }
} 
```

**Output:**

```scala
P
Q
RcsoGfGkso

```

因此，这里我们在结果数组中有三个元素，最后一个元素包含字符串的剩余部分，这是拆分数组的第二个元素后剩下的部分。
**例:2#**

```scala
// Scala program of split()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying split method
        val result = "NidhifsoSinghmsoAcso".split(".so", 2)

        for ( m1 <-result ) 
        {
            // Displays output
            println(m1)
        }

    }
} 
```

**Output:**

```scala
Nidhi
SinghmsoAcso

```