# Scala–字符串方法示例

> 原文: [https://www.geeksforgeeks.org/scala-string-methods-with-examples/](https://www.geeksforgeeks.org/scala-string-methods-with-examples/)

在 Scala 中，就像在 Java 中一样，字符串是一个字符序列。在 Scala 中，`String` 的对象是不可变的，这意味着一个常量，一旦创建就不能更改。在本节的剩余部分，我们将讨论 `java.lang.String` 类的重要方法。

## `char charAt(int index)`
此方法用于返回给定索引处的字符。

**示例:**
```scala
// Scala program of charAt() method

// Creating Object 
object GFG
{
    // Main method 
    def main(args: Array[String]){
        // Getting a character at the given index
        // Using charAt() methods
        val result = "GeeksforGeeks".charAt(3)
        println("Result : " + result)
    }
}
```

**输出:**
```scala
Result : k
```

## `int compareTo(Object o)`
此方法用于将一个字符串与另一个对象进行比较。

**示例:**
```scala
// Scala program of compareTo() method

// Creating Object 
object GFG
{
    // Main method 
    def main(args: Array[String]){
        // Compare two strings
        // Using compateTo() methods
        val val1 = "Hello"
        val val2 = "GeeksforGeeks"
        val result = val1.compareTo(val2)
        println("Result : " + result)
    }
}
```

**输出:**
```scala
Result : 1
```

## `int compareTo(String anotherString)`
此方法用于按字典顺序比较两个字符串。如果两个字符串匹配则返回 0，否则返回两者之间的差值。

**示例:**
```scala
// Scala program of compareTo() method

// Creating Object 
object GFG
{
    // Main method 
    def main(args: Array[String]){
        // Compare two strings
        // Using compateTo() methods
        val result = "Geeks".compareTo("Geeks")
        println("Result : " + result)
    }
}
```

**输出:**
```scala
Result : 0
```

## `int compareToIgnoreCase(String str)`
此方法用于按字典顺序比较两个字符串，忽略大小写差异。

**示例:**
```scala
// Scala program of compareToIgnoreCase() method

// Creating Object 
object GFG
{
    // Main method 
    def main(args: Array[String])
    {
        // Using compareToIgnoreCase() methods
        val result = "Geeks".compareToIgnoreCase("geeks")
        println("Result : " + result)
    }
}
```

**输出:**
```scala
Result : 0
```

## `String concat(String str)`
此方法用于连接两个字符串。它将两个字符串连接在一起，形成一个单独的字符串。

**示例:**
```scala
// Scala program of concat() method

// Creating Object 
object GFG
{
    // Main method 
    def main(args: Array[String]){
        // Concatenate two strings
        // Using concat() methods
        val result = "Geeks".concat("forGeeks")
        println("Result : " + result)
    }
}
```

**输出:**
```scala
Result : GeeksforGeeks
```

## `Boolean contentEquals(StringBuffer sb)`
此方法用于将字符串与 `StringBuffer` 的内容进行比较。如果它们相等则返回 `true`，否则返回 `false`。

**示例:**
```scala
// Scala program of contentEquals() method

// Creating Object 
object GFG
{
    // Main method 
    def main(args: Array[String])
    {
        // Using contentEquals() methods
        val a = new StringBuffer("Geeks")
        val result = "Geeks".contentEquals(a)
        println("Result : " + result)
    }
}
```

**输出:**
```scala
Result : true
```

## `Boolean endsWith(字符串后缀)`
如果字符串以指定的后缀结尾，则此方法用于返回 `true`。否则，它返回 `false`。

**示例:**
```scala
// Scala program of endsWith() method

// Creating Object 
object GFG
{
    // Main method 
    def main(args: Array[String])
    {
        // Using endsWith() methods
        val result = "Geeks".endsWith("s")
        println("Result : " + result)
    }
}
```

**输出:**
```scala
Result : true
```

### 13. `Boolean equals(Object anObject)`
This method is used to returns true if the string and the object are equal. Otherwise, it returns false.

`Example:`

```scala
// Scala program of equals() method

// Creating Object
object GFG
{

// Main method
    def main(args: Array[String])
    {

// Using equals() methods
        val result = "Geeks".equals("Geeks")
        println("Result : " + result)
    }
}
```

`输出:`

```scala
Result : true
```

### 14. `Boolean equalsIgnoreCase(String anotherString)`
This methods works like `equals()` but it ignores the case differences.

`Example:`

```scala
// Scala program of equalsIgnoreCase() method

// Creating Object
object GFG
{

// Main method
    def main(args: Array[String])
    {

// Using equalsIgnoreCase() methods
        val result = "Geeks".equalsIgnoreCase("gEeks")
        println("Result : " + result)
    }
}
```

`输出:`

```scala
Result : true
```

### 15. `byte[] getBytes()`
This method helps in encoding a string into a sequence of bytes and it also helps in storing it into a new byte array.

`Example:`

```scala
// Scala program of getBytes() method

// Creating Object
object GFG
{

// Main method
    def main(args: Array[String])
    {

// Using getBytes() methods
        val result = "ABCcba".getBytes()
        println("Result : " + result)
    }
}
```

`输出:`

```scala
Result : [B@506e1b77
```

### 16. `int indexOf(int ch)`
This method helps in returning the index of the first occurrence of the character in the string.

`Example:`

```scala
// Scala program of indexOf() method

// Creating Object
object GFG
{

// Main method
    def main(args: Array[String])
    {

// Using indexOf() methods
        val result = "Geeks".indexOf('e')
        println("Result : " + result)
    }
}
```

`输出:`

```scala
Result : 1
```

### 17. `int indexOf(int ch, int fromIndex)`
This method works similar to that `indexOf`. The only difference is that it begins searching at the specified index.

`Example:`

```scala
// Scala program of indexOf() method

// Creating Object
object GFG
{

// Main method
    def main(args: Array[String])
    {

// Using indexOf() methods
        val result = "Geeksforgeeks".indexOf('g',5)
        println("Result : " + result)
    }
}
```

`输出:`

```scala
Result : 8
```

### 18. `int indexOf(String str)`
This method is used to return the index of the first occurrence of the substring we specify, in the string.

`Example:`

```scala
// Scala program of indexOf() method

// Creating Object
object GFG
{

// Main method
    def main(args: Array[String])
    {

// Using indexOf() methods
        val result = "Geeksforgeeeks".indexOf("ks")
        println("Result : " + result)
    }
}
```

`输出:`

```scala
Result : 3
```

### 19. `String intern()`
This method is used to return the canonical representation for the string object.

`Example:`

```scala
// Scala program of intern() method

// Creating Object
object GFG
{

// Main method
    def main(args: Array[String])
    {

// Using intern() methods
        val result = "Geeks,\n\tForGeeks".intern()
        println("Result : " + result)
    }
}
```

`输出:`

```scala
Result : Geeks,
    ForGeeks
```

### 20. `int lastIndexOf(int ch)`
This method is used to return the index of the last occurrence of the character we specify.

`Example:`

```scala
// Scala program of lastIndexOf() method

// Creating Object
object GFG
{

// Main method
    def main(args: Array[String])
    {

// Using lastIndexOf() methods
        val result = "Geeks".lastIndexOf('e')
        println("Result : " + result)
    }
}
```

`输出:`

```scala
Result : 2
```

## 21. `int lastIndexOf(String str)`
此方法用于返回我们指定的子字符串在字符串中最后出现的位置索引。
**示例：**

```scala
// Scala program of lastIndexOf() method

// Creating Object 
object GFG
{

// Main method 
    def main(args: Array[String])
    {

// Using lastIndexOf() methods
        val result = "Geeksforgeeks".lastIndexOf("ek")
        println("Result : " + result)
    }
}
```

**输出：**

```scala
Result : 10
```

## 22. `int length()`
此方法用于返回字符串的长度。
**示例：**

```scala
// Scala program of length() method

// Creating Object 
object GFG
{

// Main method 
    def main(args: Array[String])
    {

// Using length() methods
        val result = "Geeks".length()
        println("Result : " + result)
    }
}
```

**输出：**

```scala
Result : 5
```

## 23. `String replaceAll(String regex, String replacement)`
此方法用于用用户提供的替换字符串替换匹配正则表达式的子字符串。
**示例：**

```scala
// Scala program of replaceAll() method

// Creating Object 
object GFG
{

// Main method 
    def main(args: Array[String])
    {

// Using replaceAll() methods
        val result = "potdotnothotokayslot".replaceAll(".ot","**")
        println("Result : " + result)
    }
}
```

**输出：**

```scala
Result : ********okays**
```

## 24. `String replaceFirst(String regex, String replacement)`
如果在上面的例子中，我们只想替换第一个匹配的子字符串。
**示例：**

```scala
// Scala program of replaceFirst() method

// Creating Object 
object GFG
{

// Main method 
    def main(args: Array[String])
    {

// Using replaceFirst() methods
        val result = "potdotnothotokayslot".replaceFirst(".ot","**")
        println("Result : " + result)
    }
}
```

**输出：**

```scala
Result : **dotnothotokayslot
```

## 25. `String[] split(String regex)`
此方法用于根据我们指定的正则表达式的匹配项来分割字符串。它返回一个字符串数组。
**示例：**

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
        val result = "PfsoQmsoRcsoGfGkso".split(".so")

for ( a <-result ) 
        { 
            // Displays output 
            println(a) 
        }

} 
} 
```

**输出：**

```scala
P
Q
R
GfG
```

## 26. `Boolean startsWith(String prefix, int toffset)`
此方法用于检查字符串是否从给定的索引处开始匹配指定的前缀。如果是，则返回 `true`；否则返回 `false`。
**示例：**

```scala
// Scala program of startsWith() method

// Creating Object 
object GFG
{

// Main method 
    def main(args: Array[String])
    {

// Using startsWith() methods
        val result = "Geeks".startsWith("ee", 1)
        println("Result : " + result)
    }
}
```

**输出：**

```scala
Result : true
```

## 27. `CharSequence subSequence(int beginIndex, int endIndex)`
此方法用于返回给定字符串的子字符串。这里需要指定子字符串的起始索引和结束索引。
**示例：**

```scala
// Scala program of subSequence() method

// Creating Object 
object GFG
{

// Main method 
    def main(args: Array[String])
    {

// Using subSequence() methods
        val result = "Geeks".subSequence(1,4)
        println("Result : " + result)
    }
}
```

**输出：**

```scala
Result : eek
```

## 28. `String substring(int beginIndex)`
此方法用于返回从给定索引开始直到字符串末尾的字符。
**示例：**

```scala
// Scala program of substring() method

// Creating Object 
object GFG
{
```

# Scala字符串方法

## 29. `char[] toCharArray()`
此方法用于将字符串转换为字符数组。

### 示例
```scala
// Scala program of toCharArray() 
// method

// Creating object 
object GfG 
{

// Main method 
    def main(args:Array[String]) 
    {

// Applying toCharArray method 
        val result = "GeeksforGeeks".toCharArray()

for(m1<-result) 
        {

// Displays output 
            println(m1) 
        } 
    } 
} 
```

### 输出
```scala
G
e
e
k
s
f
o
r
G
e
e
k
s
```

## 30. `String toLowerCase()`
此方法用于将所有字符转换为小写。

### 示例
```scala
// Scala program of toLowerCase() method

// Creating Object 
object GFG
{

// Main method 
    def main(args: Array[String])
    {

// Using toLowerCase() methods
        val result = "GEekS".toLowerCase()
        println("Result : " + result)
    }
}
```

### 输出
```scala
Result : geeks
```

## 31. `String toString()`
此方法用于返回字符串对象本身。

### 示例
```scala
// Scala program of toString() method

// Creating Object 
object GFG
{

// Main method 
    def main(args: Array[String])
    {

// Using toString() methods
        val result = "9".toString()
        println("Result : " + result)
    }
}
```

### 输出
```scala
Result : 9
```

## 32. `String toUpperCase()`
此方法用于将字符串转换为大写。

### 示例
```scala
// Scala program of toUpperCase() method

// Creating Object 
object GFG
{

// Main method 
    def main(args: Array[String])
    {

// Using toUpperCase() methods
        val result = "Geeks".toUpperCase()
        println("Result : " + result)
    }
}
```

### 输出
```scala
Result : GEEKS
```

## 33. `String trim()`
此方法用于移除字符串的前导和尾随空格。

### 示例
```scala
// Scala program of trim() method

// Creating Object 
object GFG
{

// Main method 
    def main(args: Array[String])
    {

// Using trim() methods
        val result = " Geeks ".trim()
        println("Result : " + result)
    }
}
```

### 输出
```scala
Result : Geeks
```

## 34. `String substring(int beginIndex, int endIndex)`
此方法用于返回字符串从`beginIndex`开始到`endIndex`结束的部分。

### 示例
```scala
// Scala program of substring() 
// method

// Creating Object 
object GFG
{

// Main method 
    def main(args: Array[String])
    {

// Using substring() methods
        val result = "Piyush".substring(1, 4)
        println("Result : " + result)
    }
}
```

### 输出
```scala
Result : iyu
```

## 35. `Boolean startsWith(String prefix)`
此方法用于检查字符串是否以给定前缀开头。如果是，返回`true`；否则返回`false`。

### 示例
```scala
// Scala program of startsWith() 
// method

// Creating Object 
object GFG
{

// Main method 
    def main(args: Array[String])
    {

// Using startsWith() methods
        val result = "Ayush".startsWith(" Ay")
        println("Result : " + result)
    }
}
```

### 输出
```scala
Result : false
```

## 36. `String[] split(String regex, int limit)`
此方法类似于`split`，唯一的区别是我们可以限制数组的成员数量。

### 示例
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

### 输出
```scala
Nidhi
SinghmsoAcso
```

## 37. `Boolean matches(String regex)`
此方法用于检查字符串是否匹配指定的正则表达式。如果匹配，返回`true`。

### 示例
```scala
// Scala program of matches() method

// Creating Object 
object GFG
{

// Main method 
    def main(args: Array[String])
    {

// Using matches() methods
        val result = "Ayushi".matches(".i.*")
        println("Result : " + result)
    }
}
```

### 输出
```scala
Result : false
```

## 38. `Boolean regionMatches(boolean ignoreCase, int toffset, String other, int offset, int len)`
此方法用于检查两个字符串区域是否相等。

### 示例
```scala
// Scala program of regionMatches() method

// Creating Object 
object GFG
{

// Main method 
    def main(args: Array[String])
    {

// Using regionMatches() methods
        val result = "Ayushi".regionMatches(true, 0, "Ayush", 0, 3)
        println("Result : " + result)
    }
}
```

### 输出
```scala
Result : true
```

## 39. `String replace(char oldChar, char newChar)`
此方法用于将`oldChar`的出现替换为`newChar`。

### 示例
```scala
// Scala program of replace() method

// Creating Object 
object GFG
{

// Main method 
    def main(args: Array[String])
    {

// Using replace() methods
        val result = "sanjay sharma".replace('s','{content}apos;)
        println("Result : " + result)
    }
}
```

### 输出
```scala
Result : $anjay $harma
```

## 40. `int hashCode()`
此方法用于返回字符串的哈希码。

### 示例
```scala
// Scala program of hashCode() method

// Creating Object 
object GFG
{

// Main method 
    def main(args: Array[String])
    {

// Using hashCode() methods
        val result = "Ayushi".hashCode()
        println("Result : " + result)
    }
}
```

### 输出
```scala
Result : 1976240247
```

## 41. `Boolean regionMatches(int toffset, String other, int offset, int len)`
此方法与上一个方法相同，但不忽略大小写。

### 示例
```scala
// Scala program of regionMatches() method

// Creating Object 
object GFG
{

// Main method 
    def main(args: Array[String])
    {

// Using regionMatches() methods
        val result = "Ayushi".regionMatches(true, 0, "Ayushi",
                                            0, 4)
        println("Result : " + result)
    }
}
```

### 输出
```scala
Result : true
```