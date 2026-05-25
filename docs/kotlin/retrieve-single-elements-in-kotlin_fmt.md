# 检索柯特林中的单个元素

> 原文: [https://www.geeksforgeeks.org/retrieve-single-elements-in-kotlin/](https://www.geeksforgeeks.org/retrieve-single-elements-in-kotlin/)

[科特林](https://www.geeksforgeeks.org/introduction-to-kotlin/)集合允许针对不同条件检索单个元素。这完全取决于使用哪种集合来存储数据。集合的元素可以通过位置、条件、随机化以及列表中该元素的存在来检索。

## 按位置检索

`elementAt(index)`：`elementAt()`获取元素的索引，并从列表中检索它。列表的索引从 0 开始，一直到 n-1，其中 n 是列表中的元素数。这是检索元素的最简单和最容易的方法，并且只有在预先知道所需元素的位置时才是首选的。

### 使用 `elementAt()` 方法的 Kotlin 程序

```kt
fun main(args: Array<String>) {
    val list = listOf("GeeksforGeeks", "A", "Computer", "Science", "Portal")
    // we know the place of GeeksforGeeks thus we use
    // elementAt() method
    println(list.elementAt(0))
}
```

**输出：**

```kt
GeeksforGeeks
```

从列表中检索一个元素有很多方法，但是为了避免在检索不存在的元素时出现异常，我们应该使用安全的方法。其中两个方法是：

- `elementAtOrDefault(index) { lambda expression }`：它是对 `elementAt()` 的加法，在找不到索引时执行 lambda expression。
- `elementAtOrNull(index)`：它是对 `elementAt()` 的加法，当找不到索引时返回 Null。

### 使用安全转换检索元素的 Kotlin 程序

```kt
fun main(args: Array<String>) {
    val list = listOf("GeeksforGeeks", "A", "Computer", "Science", "Portal")
    // we are trying to access the elements out of bounds
    // one will give out null output and other will execute
    // print statement
    println(list.elementAtOrNull(5))
    println(list.elementAtOrElse(5) { "Element index not found" })
}
```

**输出：**

```kt
null
Element index not found
```

我们也可以通过以下两种方法从列表中检索第一个和最后一个元素：

- `first()`：用于从列表中检索第一个元素，即索引为 0。
- `last()`：用于检索列表的最后一个元素，即索引 n-1，其中 n 是列表的大小。

### 使用 `first()` 和 `last()` 方法的 Kotlin 程序

```kt
fun main(args: Array<String>) {
    val list = listOf("GeeksforGeeks", "A", "Computer", "Science", "Portal")
    // accessing the first element
    println(list.first())
    // accessing the last element
    println(list.last())
}
```

**输出：**

```kt
GeeksforGeeks
Portal
```

## 按条件检索

使用 `first()` 和 `last()` 方法，我们可以检索匹配给定谓词的元素。

```kt
fun main(args: Array<String>) {
    val numbers = listOf("Geeks", "for", "Geek", "A", "Computer", "Science", "Portal")
    // retrieve the first element having string length > 5
    println(numbers.first { it.length > 5 })
    // retrieve the last element start with "G"
    println(numbers.last { it.startsWith("G") })
}
```

**输出：**

```kt
Computer
Geek
```

如果没有找到与谓词匹配的元素，这两个函数都会抛出异常。为了避免异常，我们使用 `firstOrNull()` 和 `lastOrNull()`，如果没有找到匹配的元素，它们将返回 **null**。

```kt
fun main(args: Array<String>) {
    val numbers = listOf("Geeks", "for", "Geek", "A", "Computer", "Science", "Portal")
    // retrieve the first element having string length > 9
    println(numbers.firstOrNull { it.length > 9 })
    // retrieve the last element start with "B"
    println(numbers.lastOrNull { it.startsWith("B") })
}
```

**输出：**

```kt
null
null
```

## 随机检索

如果我们想从列表中检索任意元素，我们可以使用 `random()` 函数。

- `random()`：它从集合中返回一个随机元素。

### 示例

```kt
fun main(args: Array<String>) {
    val strings = listOf("Geeks", "for", "Geek", "A", "Computer", "Science", "Portal")
    // Example of random outputs of letters in list new each time
    println(strings.random())
}
```

**输出：**

```kt
Computer (output can be same or different)
```

## 检查存在

- `contains(element)`：用于检查列表中是否有元素。如果元素存在，则返回 true，否则返回 false。
- `containsAll(elements[])`：用于检查所有元素是否在列表中。如果所有元素都在那里，则返回 true，否则返回 false。
- `in` 关键字：用于检查所有元素是否在列表中。如果元素存在，则返回真，否则返回假。
- `isEmpty()`：用于检查列表是否为空。如果元素不在列表中，则返回 true，否则返回 false。
- `isNotEmpty()`：用于检查列表是否为空。如果元素在列表中，则返回 true，否则返回 false。

### 检查列表中字符串存在的 Kotlin 程序

```kt
fun main(args: Array<String>) {
    val list = listOf("Geeks", "for", "Geek", "A", "Computer", "Science", "Portal")
    // checking the string is in list or not
    println(list.contains("For"))
    println(list.containsAll(listOf("A", "Computer")))
    println(list.isEmpty())
    println(list.isNotEmpty())
}
```

**输出：**

```kt
false
true
false
true
```