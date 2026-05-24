# Scala–字符串方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-string-methods-with-examples/](https://www.geeksforgeeks.org/scala-string-methods-with-examples/)

在 Scala 中，就像在 Java 中一样，字符串是一个字符序列。在 Scala 中，String 的对象是不可变的，这意味着一个常量，一旦创建就不能更改。在本节的剩余部分，我们将讨论 java.lang.String 类的重要方法。

1.  **char charAt(int index):** This method is used to returns the character at the given index.

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

2.  **int compareTo(Object o):** This method is used for the comparison of one string to another object.
    **Example:**

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

3.  **int compareTo(String anotherString):** This method is used to compares two strings lexicographically. If two strings match then it returns 0, else it returns the difference between the two.
    **Example:**

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

4.  **int compareToIgnoreCase(String str):** This method is used for comparing two strings lexicographically. It ignoring the case differences.
    **Example:**

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

5.  **String concat(String str):** This method is used for concatenation of the two strings. It join two strings together and made a single string.**Example:**

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

6.  **Boolean contentEquals(StringBuffer sb):** This method is used to compares a string to a StringBuffer’s contents. If they are equal then it returns true otherwise it will return false.
    **Example:**

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

7.  **Boolean endsWith(字符串后缀):**如果字符串以指定的后缀结尾，则此方法用于返回 true。否则，它返回 false。
    T3】例:

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

13.  **Boolean equals(Object anObject):** This method is used to returns true if the string and the object are equal. Otherwise, it returns false.
    **Example:**

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

    **输出:**

    ```scala
    Result : true
    ```

14.  **Boolean equalsIgnoreCase(String anotherString):** This methods works like equals() but it ignores the case differences.
    **Example:**

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

    **输出:**

    ```scala
    Result : true

    ```

15.  **byte getBytes():** This method helps in encoding a string into a sequence of bytes and it also helps in storing it into a new byte array.
    **Example:**

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

    **输出:**

    ```scala
    Result : [B@506e1b77
    ```

16.  **int indexOf(int ch):** This method helps in returning the index of the first occurrence of the character in the string.
    **Example:**

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

    **输出:**

    ```scala
    Result : 1
    ```

17.  **int indexOf(int ch, int fromIndex):** This method works similar to that indexOf. The only difference is that it begins searching at the specified index.**Example:**

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

    **输出:**

    ```scala
    Result : 8
    ```

18.  **int indexOf(String str):** This method is used to return the index of the first occurrence of the substring we specify, in the string.
    **Example:**

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

    **输出:**

    ```scala
    Result : 3
    ```

19.  **String intern():** This method is used to return the canonical representation for the string object.
    **Example:**

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

    **输出:**

    ```scala
    Result : Geeks,
        ForGeeks

    ```

20.  **int lastIndexOf(int ch):** This method is used to return the index of the last occurrence of the character we specify.
    **Example:**

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

    **输出:**

    ```scala
    Result : 2
    ```

21.  **int lastIndexOf(String str):** This method is used to return the index of the last occurrence of the substring we specify, in the string.
    **Example:**

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

    **输出:**

    ```scala
    Result : 10
    ```

22.  **int length():** This method is used to return the length of a string.
    **Example:**

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

    **输出:**

    ```scala
    Result : 5
    ```

23.  **String replaceAll(String regex, String replacement):** This method is used to replace the substring with the replacement string provided by user.
    **Example:**

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

    **输出:**

    ```scala
    Result : ********okays**
    ```

24.  **String replaceFirst(String regex, String replacement):** If in the above example, we want to replace only the first such occurrence.
    **Example:**

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

    **输出:**

    ```scala
    Result : **dotnothotokayslot
    ```

25.  **String[] split(String regex):** This method is used to split the string around matches of the regular expression we specify. It returns a String array.
    **Example:**

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

    **输出:**

    ```scala
    P
    Q
    R
    GfG

    ```

26.  **Boolean startsWith(String prefix, int toffset):** This method is used to return true if the string starts with the given index. Otherwise, it will return false.
    **Example:**

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

    **输出:**

    ```scala
    Result : true
    ```

27.  **CharSequence subSequence(int beginIndex, int endIndex):** This method is used to return the sub string from the given string. Here starting index and ending index of a sub string is given.
    **Example:**

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

    **输出:**

    ```scala
    Result : eek
    ```

28.  **String substring(int beginIndex):** This method is used to return the characters of the string beginning from the given index till the end of the string.
    **Example:**

    ```scala
    // Scala program of substring() method 

    // Creating Object 
    object GFG
    {

        // Main method 
        def main(args: Array[String])
        {

            // Using substring() methods
            val result = "Geeks".substring(3)
            println("Result : " + result)
        }
    }
    ```

    **输出:**

    ```scala
    Result : ks
    ```

29.  **char[] toCharArray():** This method is used to convert the string into a CharArray.
    **Example:**

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

    **输出:**

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

30.  **String toLowerCase():** This method is used to convert all the characters into lower case.
    **Example:**

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

    **输出:**

    ```scala
    Result : geeks
    ```

31.  **String toString():** This method is used to return a String object itself.
    **Example:**

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

    **输出:**

    ```scala
    Result : 9
    ```

32.  **String toUpperCase():** This method is used to convert the string into upper case.
    **Example:**

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

    **输出:**

    ```scala
    Result : GEEKS
    ```

33.  **String trim():** This method is used to remove the leading and trailing whitespaces from the string.
    **Example:**

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

    **输出:**

    ```scala
    Result : Geeks
    ```

34.  **String substring(int beginIndex, int endIndex):** This method is used to return the part of the string beginning at beginIndex and ending at endIndex.
    **Example:**

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

    **输出:**

    ```scala
    Result : iyu
    ```

35.  **Boolean startsWith(String prefix):** This method is used to return true if the string starts with the given prefix. Otherwise, returns false.
    **Example:**

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

    **输出:**

36.  **String[] split(String regex, int limit):** This method is like split, the only change is that we can limit the number of members for the array.
    **Example:**

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

    **输出:**

    ```scala
    Nidhi
    SinghmsoAcso
    ```

37.  **Boolean matches(String regex):** This method is used to return true, if string matches the regular expression specified.
    **Example:**

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

    **输出:**

    ```scala
    Result : false
    ```

38.  **Boolean regionMatches(boolean ignoreCase, int toffset, String other, int offset, int len)**: This method is used to return true if two strings regions are equal.
    **Example:**

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

    **输出:**

    ```scala
    Result : true
    ```

39.  **String replace(char oldChar, char newChar):** This method is used to replace the oldChar occurences with the newChar ones.
    **Example:**

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

    **输出:**

    ```scala
    Result : $anjay $harma
    ```

40.  **int hashCode():** This method is used to return hash code of a string.
    **Example:**

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

    **输出:**

    ```scala
    Result : 1976240247
    ```

41.  **Boolean regionMatches(int toffset, String other, int offset, int len):** This method does not have any ignore case, else it is same as above method.
    **Example:**

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

    **输出:**

    ```scala
    Result : true
    ```