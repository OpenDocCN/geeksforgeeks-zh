# Scala 中的 StringBuilder

> 原文:[https://www.geeksforgeeks.org/stringbuilder-in-scala/](https://www.geeksforgeeks.org/stringbuilder-in-scala/)

字符串对象是不可变的，即字符串一旦创建就不能更改。在需要对字符串进行重复修改的情况下，我们需要 StringBuilder 类。 **StringBuilder** 用于将输入数据附加到内部缓冲区。在 StringBuilder 方法的支持下，我们可以执行许多操作。该操作包括*追加数据*、*插入数据*、*删除数据*。
**要点:**

*   StringBuilder 类有利于可变字符串的有效扩展。
*   StringBuilder 的实例像字符串一样使用。
*   Scala 的字符串是不可变的，所以当你需要一个可变的字符串时，你可以使用 StringBuilder。

**Operations performed by the StringBuilder class**

*   **Appending character:** This operation is helpful in appending character.
    **Example:**

    ```scala
    // Scala program to append
    // a character

    // Creating object 
    object GFG
    {

        // Main method
        def main(args: Array[String])
        {

            // Creating StringBuilder 
            val x = new StringBuilder("Author");

            // Appending character 
            val y = (x += 's')

            // Displays the string after 
            // appending the character 
            println(y)
        }
    }
    ```

    **Output:**

    ```scala
    Authors

    ```

    这里，利用 **(x += ' ')** 追加一个字符。

*   **追加字符串:**该操作有助于追加字符串。
    **示例:**

    ```scala
    // Scala program to append
    // a String

    // Creating object 
    object GFG
    {

        // Main method
        def main(args: Array[String])
        {

            // Creating StringBuilder 
            val x = new StringBuilder("Authors");

            // Appending String 
            val y = (x ++= " of GeeksforGeeks")

            // Displays the string after 
            // appending the string 
            println(y)

        }
    }
    ```

    **输出:**

```scala
Authors of GeeksforGeeks

```