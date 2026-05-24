# 调用 Scala 中集合的方法

> 原文:[https://www . geesforgeks . org/methods-to-call-on-set-in-Scala/](https://www.geeksforgeeks.org/methods-to-call-on-a-set-in-scala/)

集合是只包含唯一项目的集合。在 Scala 中，可变集和不可变集都是可用的。可变集是那些对象的值被改变的集，但是，在不可变集中，对象的值本身不被改变。不可变集是在 Scala . collection . unvariable . package 下定义的，可变集是在 Scala . collection . mutable . package 下定义的。在这里，我们将讨论 Scala . collection . invoke . _ package 的一些重要方法。

**1。def+(elem:A):Set[A]–**此方法用于向集合中添加一个元素，然后将其返回。
T3】例:

```scala
// Scala program of +() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a set 
        val s = Set(8, 9, 1, 4, 2, 7) 

        // Applying +() method 
        val result = s.+(6) 

        // Display output 
        print(result)     
    } 
} 
```

**输出:**

```scala
Set(1, 6, 9, 2, 7, 8, 4)
```

**2。def-(elem:A):Set[A]–**此方法用于从集合中移除元素，然后将其返回。
T3】例:

```scala
// Scala program of -() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a set 
        val s = Set(8, 9, 1, 4, 2, 7) 

        // Applying -() method 
        val result = s.-(1) 

        // Display output 
        print(result)     
    } 
} 
```

**输出:**

```scala
Set(9, 2, 7, 8, 4)
```

**3。def 包含(elem:A):Boolean–**如果集合包含指定的元素，则此方法返回 true。否则，它将返回 false。
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

        // Creating a set 
        val s = Set(8, 9, 1, 4, 2, 7) 

        // Applying contains() method 
        val result = s.contains(1) 

        // Display output 
        print(result)     
    } 
} 
```

**输出:**

```scala
true
```

**4。def &(即:Set[A]):Set[A]–**此方法用于返回两个集合的交集。
T3】例:

```scala
// Scala program of &() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a set 
        val s1 = Set(8, 9, 1, 4, 2, 7)
        val s2 = Set(3, 4, 6, 8) 

        // Applying &() method 
        val result = s1.&(s2)

        // Display output 
        print(result)     
    } 
} 
```

**输出:**

```scala
Set(8, 4)
```

**5。def & ~(即:设置[A]):设置[A]–**此符号表示设置差异。
T3】例:

```scala
// Scala program of &~() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a set 
        val s1 = Set(8, 9, 1, 4, 2, 7)
        val s2 = Set(3, 4, 6, 8) 

        // Applying &~() method 
        val result = s1.&~(s2)

        // Display output 
        print(result)     
    } 
} 
```

**输出:**

```scala
Set(1, 9, 2, 7)
```

**6。def +(elem1: A，elem2: A，elems:A *):Set[A]–**这个方法是将多个元素加到一个 Scala 集合中，然后返回。
T3】例:

```scala
// Scala program of +() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a set 
        val s = Set(8, 9, 1, 4, 2, 7)

        // Applying +() method 
        val result = s.+(3, 4, 6) 

        // Display output 
        print(result)     
    } 
} 
```

**输出:**

```scala
Set(1, 6, 9, 2, 7, 3, 8, 4)
```

**7。def++(elems:A):Set[A]–**此方法用于一个集合与另一个集合的串联。
T3】例:

```scala
// Scala program of ++() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a set 
        val s1 = Set(8, 9, 1, 4, 2, 7)
        val s2 = Set(3, 4, 6) 

        // Applying ++() method 
        val result = s1 ++ s2 

        // Display output 
        print(result)     
    } 
} 
```

**输出:**

```scala
Set(1, 6, 9, 2, 7, 3, 8, 4)
```

**8。def -(elem1: A，elem2: A，elems:A *):Set[A]–**此方法用于从集合中移除提到的每个元素。
T3】例:

```scala
// Scala program of -() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a set 
        val s = Set(8, 9, 1, 4, 2, 7)

        // Applying -() method 
        val result = s.-(8, 1, 3) 

        // Display output 
        print(result)     
    } 
} 
```

**输出:**

```scala
Set(9, 2, 7, 4)
```

**9。def add String(b:StringBuilder):StringBuilder–**该方法用于将集合的所有元素添加到 StringBuilder 中。
T3】例:

```scala
// Scala program of addString() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a set 
        val s = Set(8, 9, 1, 4, 2, 7)

        // Applying addString() method 
        val result = s.addString(new StringBuilder()) 

        // Display output 
        print(result)     
    } 
} 
```

**输出:**

```scala
192784
```

**10。def addString(b: StringBuilder，sep:String):StringBuilder–**这个方法被用作上述功能的分隔符。
T3】例:

```scala
// Scala program of addString() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a set 
        val s = Set(8, 9, 1, 4, 2, 7)

        // Applying addString() method 
        val result = s.addString(new StringBuilder(), "*") 

        // Display output 
        print(result)     
    } 
} 
```

**输出:**

```scala
1*9*2*7*8*4
```

**11 时。def apply(elem:A)–**此方法用于检查元素是否是集合的一部分。它返回布尔值“真”或“假”。
T3】例:

```scala
// Scala program of apply() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a set 
        val s = Set(8, 9, 1, 4, 2, 7)

        // Applying apply() method 
        val result = s.apply(2)

        // Display output 
        print(result)     
    } 
} 
```

**输出:**

```scala
true
```

**12 时。def drop(n:Int):Set[A]]–**此方法用于返回除第一个 n.
之外的所有元素**示例:**

```scala
// Scala program of drop() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a set 
        val s = Set(2, 3, 5, 7, 8)

        // Applying drop() method 
        val result = s.drop(2)

        // Display output 
        print(result)     
    } 
} 
```

**输出:**

```scala
Set(7, 3, 8)
```

**13。def drop right(n:Int):Set[A]–**此方法用于返回除最后 n 个元素之外的所有元素，这与上述方法()正好相反。
T3】例:

```scala
// Scala program of dropRight() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a set 
        val s = Set(1, 2, 3, 5, 7, 9)

        // Applying dropRight() method 
        val result = s.dropRight(2)

        // Display output 
        print(result)     
    } 
} 
```

**输出:**

```scala
Set(5, 1, 9, 2)
```

**14。def 等于(即:任意):布尔值–**该方法用于将集合与另一个序列进行比较。
T3】例:

```scala
// Scala program of equals() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a set 
        val s = Set(2, 3, 5, 7, 8)

        // Applying equals() method 
        val result = s.equals(Set(2, 3, 5, 7, 8))

        // Display output 
        print(result)     
    } 
} 
```

**输出:**

```scala
true
```

**15。def head:A–**此方法用于返回集合中的第一个元素。
T3】例:

```scala
// Scala program of head() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a set 
        val s = Set(1, 2, 3, 5, 7, 9)

        // Applying head() method 
        val result = s.head

        // Display output 
        print(result)     
    } 
} 
```

**输出:**

```scala
5
```

**16。def init:Set[A]–**此方法用于返回集合中除最后一个元素之外的所有元素。
T3】例:

```scala
// Scala program of init() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a set 
        val s = Set(1, 2, 3, 5, 7, 9)

        // Applying init() method 
        val result = s.init

        // Display output 
        print(result)     
    } 
} 
```

**输出:**

```scala
Set(5, 1, 9, 2, 7)
```

**17。def intersect(即:Set[A]):Set[A]–**这个方法用来返回两个集合的交集，也就是说它返回两个集合的公共元素。
T3】例:

```scala
// Scala program of intersect() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a set 
        val s1 = Set(1, 2, 3, 5, 7, 9)
        val s2 = Set(1, 2, 3, 4, 9, 9)

        // Applying intersect() method 
        val result = s1.intersect(s2) 

        // Display output 
        print(result)     
    } 
} 
```

**输出:**

```scala
Set(1, 9, 2, 3)
```

**18。def isEmpty:Boolean–**如果给定的集合为空，则该方法返回 true。否则，它将返回 False。
T3】例:

```scala
// Scala program of isEmpty() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a set 
        val s = Set(2, 3, 5, 7, 8)

        // Applying isEmpty() method 
        val result = s.isEmpty 

        // Display output 
        print(result)     
    } 
} 
```

**输出:**

```scala
false
```

**19。def 迭代器:迭代器[A]–**这个方法有助于在集合上创建一个新的迭代器。
T3】例:

```scala
// Scala program of iterator() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a set 
        val s = Set(2, 3, 5, 7, 8)

        // Applying iterator() method 
        val result = s.iterator

        // Display output 
        print(result)     
    } 
} 
```

**输出:**

```scala
non-empty iterator
```

**20。def last:A–**这个方法有助于从集合中返回最后一个元素。
T3】例:

```scala
// Scala program of last() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a set 
        val s = Set(1, 2, 3, 5, 7, 9)

        // Applying last() method 
        val result = s.last

        // Display output 
        print(result)     
    } 
} 
```

**输出:**

```scala
3
```

**21。def max:A–**此方法用于返回集合中的最高值。
T3】例:

```scala
// Scala program of max() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a set 
        val s = Set(2, 3, 5, 7, 8)

        // Applying max() method 
        val result = s.max 

        // Display output 
        print(result)     
    } 
} 
```

**输出:**

```scala
8
```

**22。def min:A–**此方法用于返回集合中最低的元素。
T3】例:

```scala
// Scala program of min() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a set 
        val s = Set(1, 2, 3, 5, 7, 9)

        // Applying min() method 
        val result = s.min 

        // Display output 
        print(result)     
    } 
} 
```

**输出:**

```scala
1
```

**23。def mkString:String–**此方法有助于将集合中的所有元素表示为字符串。
T3】例:

```scala
// Scala program of mkString() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a set 
        val s = Set(2, 3, 5, 7, 8)

        // Applying mkString() method 
        val result = s.mkString

        // Display output 
        print(result)     
    } 
} 
```

**输出:**

```scala
52738
```

**24。def product:A–**此方法用于返回集合中所有元素的乘积。
T3】例:

```scala
// Scala program of product() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a set 
        val s = Set(1, 2, 3, 5, 7, 9)

        // Applying product() method 
        val result = s.product

        // Display output 
        print(result)     
    } 
} 
```

**输出:**

```scala
1890
```

**25。def size:Int–**此方法用于返回集合的大小。
T3】例:

```scala
// Scala program of size() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a set 
        val s = Set(2, 3, 5, 7, 8)

        // Applying size() method 
        val result = s.size 

        // Display output 
        print(result)     
    } 
} 
```

**输出:**

```scala
5
```

**26。def sum:A–**此方法用于返回集合所有元素的和。
T3】例:

```scala
// Scala program of sum() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a set 
        val s = Set(1, 2, 3, 5, 7, 9)

        // Applying sum() method 
        val result = s.sum

        // Display output 
        print(result)     
    } 
} 
```

**输出:**

```scala
27
```

**27。def tail:Set[A]–**此方法用于返回集合中除第一个元素之外的所有元素。
T3】例:

```scala
// Scala program of tail() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a set 
        val s = Set(2, 3, 5, 7, 8)

        // Applying tail() method 
        val result = s.tail

        // Display output 
        print(result)     
    } 
} 
```

**输出:**

```scala
Set(2, 7, 3, 8)
```

**28。def take(n:Int):Set[A]–**此方法用于返回集合中的前 n 个元素。
T3】例:

```scala
// Scala program of take() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a set 
        val s = Set(1, 2, 3, 5, 7, 9)

        // Applying take() method 
        val result = s.take(3)

        // Display output 
        print(result)     
    } 
} 
```

**输出:**

```scala
Set(5, 1, 9)
```

这里还有一些在集合上调用的方法。

| 方法 | 描述 |
| **[def &(即:集【甲】):集【甲】](https://www.geeksforgeeks.org/scala-set-method-with-example-3/)** | 此方法有助于返回两个集合的交集。 |
| **t1【def count(p:(a)=>boolean:int** | 此方法用于返回满足谓词的元素计数。 |
| **[def diff(即:集合【A】):集合【A】](https://www.geeksforgeeks.org/scala-set-diff-method-with-example/)** | 此方法用于返回集合差(元素存在于一个集合中，但不存在于另一个集合中)。 |
| **[def drop while(p:(A)=>Boolean:Set【A】](https://www.geeksforgeeks.org/scala-set-dropwhile-method-with-example/)** | 此方法用于删除元素，直到第一个元素不满足谓词。 |
| **T1】def 存在(p: (A) = >布尔:布尔 T3】** | 如果谓词为真，则此方法用于返回真，否则返回假。 |
| **[def 滤镜(p: (A) = >布尔:设置【A】](https://www.geeksforgeeks.org/scala-set-filter-method-with-example/)** | 此方法用于过滤元素。 |
| **[def find(p:(A)=>Boolean:选项【A】](https://www.geeksforgeeks.org/scala-set-find-method-with-example/)** | 此方法用于返回满足谓词的第一个元素。 |
| [def forall(p:(a)=>boolean:boolean](https://www.geeksforgeeks.org/scala-set-forall-method-with-example/) | 如果集合的所有元素都满足谓词，则使用此方法返回 true。否则，假的。 |
| **[def 贴图【B】(f:(A)=>B):不可变。](https://www.geeksforgeeks.org/scala-set-map-method-with-example/)设置【B】** | 此方法用于将函数应用于集合的所有元素并返回它。 |
| **[def splitAt(n: Int):(集合[A]，集合[A])](https://www.geeksforgeeks.org/scala-set-splitat-method-with-example/)** | 此方法用于在给定索引处拆分集合，并返回两个结果子集。 |
| **[def subtof(即:集合[A]):布尔](https://www.geeksforgeeks.org/scala-set-subsetof-method-with-example/)** | 如果作为参数传递的集合是该集合的子集，则使用此方法返回 true，否则返回 false。 |
| **[def taker ight(n:Int):Set[A]](https://www.geeksforgeeks.org/scala-set-takeright-method-with-example/)** | 此方法用于返回最后 n 个元素。 |
| **[延迟到数组:数组【A】](https://www.geeksforgeeks.org/scala-set-toarray-method-with-example/)** | 此方法用于从集合中返回包含元素的数组。 |
| **[定义为列表:列表【A】](https://www.geeksforgeeks.org/scala-set-tolist-method-with-example/)** | 此方法用于从集合的元素中返回列表。 |
| **[def toSeq: Seq[A]](https://www.geeksforgeeks.org/scala-set-toseq-method-with-example/)** | 此方法用于从集合中返回序列。 |
| **[def ToString():String](https://www.geeksforgeeks.org/scala-set-tostring-method-with-example/)** | 此方法将集合的元素表示为字符串。 |