# 如何在 C# 中比较字符串？

> 原文:[https://www . geesforgeks . org/c-sharp 中字符串的比较方法/](https://www.geeksforgeeks.org/how-to-compare-strings-in-c-sharp/)

字符串是字符的集合，用于存储纯文本。与 C 或 C++不同，C# 中的字符串不以空字符结尾。字符串对象的最大大小取决于系统的内部架构。后面跟“string”的变量实际上是 string 类的对象。

### **如何实例化一个字符串对象？**

我们可以通过使用变量名称后跟“字符串”关键字来创建字符串类的对象。

**语法:**

> 串密音；

我们也可以在声明时初始化一个字符串对象。

**语法:**

> 字符串 mystring = " geeksforgeeks

本文主要讨论如何在 C# 中比较字符串。比如给我们三个字符串“极客 forGeeks”“极客”和“极客 forGeeks”。显然第一个和最后一个字符串是相同的。在 C# 中有许多比较字符串的方法，下面将详细解释其中的五种方法。

### 方法 1:使用字符串。Equals()方法

中指定了[字符串](https://www.geeksforgeeks.org/c-sharp-string-class/)类。NET 基类库。换句话说，字符串对象是系统的顺序集合。代表字符串的字符对象。系统。字符串类是不可变的，也就是说，一旦创建了它的状态，我们就不能对它进行更改。字符串。Equals()方法是 String 类的一种方法。此方法将两个字符串作为参数进行比较。它返回一个逻辑值，真或假，借助它我们可以确定给定的字符串是否相同。

**语法:**

> 字符串。等于(我的字符串 1，我的字符串 2)

**参数:**取两个参数 myString1:第一个字符串，myString2:第二个字符串

**返回类型:**该方法的返回类型为布尔型。如果两个字符串相等，则为真；如果两个字符串不同，则为假

**示例:**

## C#

```cs
// C# program to illustrate the working of
// String.Equals() method to compare two strings
using System;

class GFG{

static public void Main()
{

    // Initialize a string
    string myString1 = "GeeksforGeeks"; 

    // Initialize another string
    string myString2 = "Geeks";

    // Initialize a string
    string myString3 = "GeeksforGeeks";

    // If this method returns true
    // Print both string are same
    if (String.Equals(myString1, myString2)) 
        Console.WriteLine({content}quot;{myString1} and {myString2} are same."); 

    // If this method returns false
    // Print both string are different
    else 
        Console.WriteLine({content}quot;{myString1} and {myString2} are different."); 

    // If this method returns true
    // Print both string are same
    if (String.Equals(myString1, myString3)) 
        Console.WriteLine({content}quot;{myString1} and {myString3} are same."); 

    // If this method returns false
    // Print both string are different
    else 
        Console.WriteLine({content}quot;{myString1} and {myString3} are different."); 

    // If this method returns true
    // Print both string are same
    if (String.Equals(myString2, myString3)) 
        Console.WriteLine({content}quot;{myString2} and {myString3} are same."); 

    // If this method returns false
    // Print both string are different
    else 
        Console.WriteLine({content}quot;{myString2} and {myString3} are different.");          
}
}
```

**Output**

```cs
GeeksforGeeks and Geeks are different.
GeeksforGeeks and GeeksforGeeks are same.
Geeks and GeeksforGeeks are different.
```

### 方法 2:使用字符串。Compare()方法

该方法也在 String 类下定义。此方法还将两个要比较的字符串作为参数。它根据传递给方法的字符串返回一个数值。这个方法提供了字符串比较的详细信息，这就是为什么它比 **String.equals()** 方法更有优势。

**语法:**

> 字符串。比较(myString1、myString2)

**参数:**取两个参数 myString1:第一个字符串，myString2:第二个字符串

**返回类型:**该方法的返回类型为 Integer。它将是:

*   小于零:如果第一个字符串在字典序上小于第二个字符串。
*   零:如果两个字符串相等。
*   大于零:如果第一个字符串在字典序上大于第二个字符串。

**示例:**

## C#

```cs
// C# program to illustrate the working of
// String.Compare() method to compare two strings
using System;

class GFG{

static public void Main()
{

    // Initialize a string
    string myString1 = "GeeksforGeeks"; 

    // Initialize another string
    string myString2 = "Geeks";

    // Initialize another string
    string myString3 = "GeeksforGeeks";

    // If value returned by this method is equal to 0
    // Print both string are same
    if (String.Compare(myString1, myString2) == 0) 
        Console.WriteLine({content}quot;{myString1} and {myString2} are same."); 

    // If value returned by this method is less than 0
    // Then print first string is smaller than the second string
    else if(String.Compare(myString1, myString2) < 0)
        Console.WriteLine(
            {content}quot;{myString1} is lexicographically smaller than {myString2}."); 

    // If value returned bu the method is greater than 0
    // Then print first string is greater than the second string
    else
        Console.WriteLine(
            {content}quot;{myString1} is lexicographically greater than {myString2}."); 

    // If value returned by this method is equal to 0
    // Print both string are same     
    if (String.Compare(myString1, myString3) == 0) 
        Console.WriteLine({content}quot;{myString1} and {myString3} are same."); 

    // If value returned by this method is less than 0
    // Then print first string is smaller than the second string
    else if (String.Compare(myString1, myString3) < 0)
        Console.WriteLine(
            {content}quot;{myString1} is lexicographically smaller than {myString3}."); 

    // If value returned bu the method is greater than 0
    // Then print first string is greater than the second string
    else
        Console.WriteLine(
            {content}quot;{myString1} is lexicographically greater than {myString3}."); 

    // If value returned by this method is equal to 0
    // Print both string are same           
    if (String.Compare(myString2, myString3) == 0) 
        Console.WriteLine({content}quot;{myString2} and {myString3} are same."); 

    // If value returned by this method is less than 0
    // Then print first string is smaller than the second string
    else if (String.Compare(myString2, myString3) < 0)
        Console.WriteLine(
            {content}quot;{myString2} is lexicographically smaller than {myString3}."); 

    // If value returned bu the method is greater than 0
    // Then print first string is greater than the second string      
    else
        Console.WriteLine(
            {content}quot;{myString2} is lexicographically greater than {myString3}."); 
}
}
```

**Output**

```cs
GeeksforGeeks is lexicographically greater than Geeks.
GeeksforGeeks and GeeksforGeeks are same.
Geeks is lexicographically smaller than GeeksforGeeks.
```

### 方法 3:使用 CompareTo()方法

这是在字符串类下定义的实例方法，它直接应用于字符串或字符串对象。它根据要比较的字符串返回一个数值。这个方法提供了字符串比较的详细信息，这就是为什么它比 **String.equals()** 方法更有优势。

**语法:**

> 神秘 1 号。共享(myString2)

**参数:**取一个参数，就是 myString2:第二个字符串

**返回类型:**该方法的返回类型为 Integer。它将是:

*   小于零:如果第一个字符串在字典序上小于第二个字符串。
*   零:如果两个字符串相等。
*   大于零:如果第一个字符串在字典序上大于第二个字符串。

**示例:**

## C#

```cs
// C# program to illustrate the working of
// CompareTo() method to compare two strings
using System;

class GFG{

static public void Main()
{

    // Initialize a string
    string myString1 = "GeeksforGeeks"; 

    // Initialize another string
    string myString2 = "Geeks"; 

    // Initialize another string
    string myString3 = "GeeksforGeeks";

    // If value returned by this method is equal to 0
    // Then display both strings are equal
    if (myString1.CompareTo(myString2) == 0) 
        Console.WriteLine({content}quot;{myString1} and {myString2} are same."); 

    // If value returned by this method is less than 0
    // Then print the first string is smaller than the second string
    else if (myString1.CompareTo(myString2) < 0)
        Console.WriteLine(
            {content}quot;{myString1} is lexicographically smaller than {myString2}."); 

    // If value returned by this method is greater than 0
    // Then print the first string is greater than the second string      
    else
        Console.WriteLine(
            {content}quot;{myString1} is lexicographically greater than {myString2}."); 

    // If value returned by this method is equal to 0
    // Then print both strings are equal      
    if (myString1.CompareTo(myString2) == 0) 
        Console.WriteLine({content}quot;{myString1} and {myString3} are same."); 

    // If value returned by this method is less than 0
    // Then print the first string is smaller than the second string      
    else if(myString1.CompareTo(myString2) < 0)
        Console.WriteLine(
            {content}quot;{myString1} is lexicographically smaller than {myString3}."); 

    // If value returned by this method is greater than 0
    // Then print the first string is greater than the second string
    else
        Console.WriteLine(
            {content}quot;{myString1} is lexicographically greater than {myString3}."); 

    // If value returned by this method is equal to 0
    // Then display both strings are equal        
    if (myString1.CompareTo(myString2) == 0) 
        Console.WriteLine({content}quot;{myString1} and {myString2} are same."); 

    // If value returned by this method is less than 0
    // Then print the first string is smaller than the second string 
    else if (myString1.CompareTo(myString2) < 0)
        Console.WriteLine(
            {content}quot;{myString2} is lexicographically smaller than {myString3}."); 

    // If value returned by this method is greater than 0
    // Then print the first string is greater than the second string
    else
    Console.WriteLine(
        {content}quot;{myString2} is lexicographically greater than {myString3}."); 
}
}
```

**Output**

```cs
GeeksforGeeks is lexicographically greater than Geeks.
GeeksforGeeks is lexicographically greater than GeeksforGeeks.
Geeks is lexicographically greater than GeeksforGeeks.
```

### 方法 4:使用 StringComparer 类的 compare()方法

这个方法是在 StringComparer 类下定义的。我们可以创建这个类的一个对象，在这个对象的帮助下，我们可以使用 Compare()方法来比较两个字符串。这个方法提供了字符串比较的详细信息，这就是为什么它比 **String.equals()** 方法更有优势。

**语法:**

> string compare my company = string compare-字串比较。序数忽略；
> 
> 支原体感染。比较(myString1、mystring 2)；

**参数:**取两个参数 myString1:第一个字符串，myString2:第二个字符串

**返回类型:**该方法的返回类型为 Integer。它将是:

*   小于零:如果第一个字符串在字典序上小于第二个字符串。
*   零:如果两个字符串相等。
*   大于零:如果第一个字符串在字典序上大于第二个字符串。

**示例:**

## C#

```cs
// C# program to illustrate the working of Compare() method
// of StringComparer class to compare two strings
using System;

class GFG{

static public void Main()
{

    // Declare an object of class StringComparer
    StringComparer myComparer = StringComparer.OrdinalIgnoreCase;

    // Initialize a string
    string myString1 = "GeeksforGeeks";

    // Initialize another string
    string myString2 = "Geeks";

    // Initialize another string
    string myString3 = "GeeksforGeeks";

    // Compare strings using Compare method
    // on the instantiated object

    // If this method returns 0
    // Print both strings are same
    if (myComparer.Compare(myString1, myString2) == 0) 
        Console.WriteLine({content}quot;{myString1} and {myString2} are same."); 

    // If value returned by this method is smaller than 0
    // Then print the first string is smaller than the second string    
    else if (myComparer.Compare(myString1, myString2) < 0)
        Console.WriteLine(
            {content}quot;{myString1} is lexicographically smaller than {myString2}."); 

    // If value returned by this method is smaller than 0
    // Then print the first string is smaller than the second string  
    else
        Console.WriteLine(
            {content}quot;{myString1} is lexicographically greater than {myString2}."); 

    // If this method returns 0
    // Print both strings are same     
    if (myComparer.Compare(myString1, myString3) == 0) 
        Console.WriteLine({content}quot;{myString1} and {myString3} are same."); 

    // If value returned by this method is smaller than 0
    // Then print the first string is smaller than the second string 
    else if (myComparer.Compare(myString1, myString3) < 0)
        Console.WriteLine(
            {content}quot;{myString1} is lexicographically smaller than {myString3}."); 

    // If value returned by this method is smaller than 0
    // Then print the first string is smaller than the second string
    else
        Console.WriteLine(
            {content}quot;{myString1} is lexicographically greater than {myString3}."); 

    // If this method returns 0
    // Print both strings are same           
    if (myComparer.Compare(myString2, myString3) == 0) 
        Console.WriteLine({content}quot;{myString2} and {myString3} are same."); 

    // If value returned by this method is smaller than 0
    // Then print the first string is smaller than the second string       
    else if (myComparer.Compare(myString2, myString3) < 0)
        Console.WriteLine(
            {content}quot;{myString2} is lexicographically smaller than {myString3}."); 

    // If value returned by this method is greater than 0
    // Then print the first string is greater than the second string
    else
        Console.WriteLine(
            {content}quot;{myString2} is lexicographically greater than {myString3}."); 
}
}
```

**Output**

```cs
GeeksforGeeks is lexicographically greater than Geeks.
GeeksforGeeks and GeeksforGeeks are same.
Geeks is lexicographically smaller than GeeksforGeeks.
```

### 方法 5:逐个字符比较(使用自定义比较方法)

字符串可以逐个字符进行比较。按照以下步骤使用自定义比较方法比较两个字符串。

1.  声明一个静态方法**比较主方法之外的**。将此方法的返回类型设置为 int。
2.  将变量 **len** 初始化为两个字符串长度的最小值。
3.  使用 for 循环迭代**索引= 0** 到**索引= len–1**。每次迭代时，比较字符串的相应字符。
4.  如果第一个字符串在**索引**处的第一个不匹配字符小于第二个字符串在**索引**处的字符，那么我们将返回-1。
5.  如果第一个字符串在**索引**处的第一个不匹配字符小于第二个字符串在**索引**处的字符，那么我们将返回 1。
6.  在 for 循环结束后，如果两个字符串的长度相等，则返回 0。如果第一个字符串的长度小于第二个字符串，则返回-1，否则返回 1。
7.  通过传递要比较的字符串作为参数，从主函数调用 **Compare()** 函数。如果**比较()**函数返回 0，则打印第一个字符串与第二个字符串相同。如果**比较()**函数返回-1，则打印第一个字符串小于第二个字符串，否则打印第一个字符串大于第二个字符串。

**示例:**

## C#

```cs
// C# program to illustrate the working of
// custom Compare() method to compare two strings
using System;

class GFG{

// Compare method to compare two strings
static public int Compare(string myString1, string myString2)
{

    // len stores minimum of two string lengths
    int len = Math.Min(myString1.Length, myString2.Length);

    // Iterate over all characters
    for(int index = 0; index < len; index++)
    {

        // If the first not matched character of first
        // string is smaller than the second string then
        // return -1
        if (myString1[index] < myString2[index])
            return -1;

        // If the first not matched character of first
        // string is greater than the second string then
        // return 1         
        else if (myString1[index] > myString2[index])
            return 1;
    }

    // If lengths are equal
    // Return 0
    if (myString1.Length ==  myString2.Length)
        return 0;

    // If length of first string is smaller than the second string
    // then return -1
    // If length of first string is greater than the second string
    // then return 1
    return ((myString1.Length <  myString2.Length) ? -1 : 1);
}

// Driver code
static public void Main()
{

    // Initialize a string
    string myString1 = "GeeksforGeeks"; 

    // Initialize another string
    string myString2 = "Geeks"; 

    // Initialize another string
    string myString3 = "GeeksforGeeks";

    // If value returned by this method is equal to 0
    // Then print both strings are same          
    if (Compare(myString1, myString2) == 0) 
        Console.WriteLine({content}quot;{myString1} and {myString2} are same."); 

    // If value returned by this method is smaller than 0
    // Then print the first string is smaller than the second string
    else if (Compare(myString1, myString3) < 0)
        Console.WriteLine(
            {content}quot;{myString1} is lexicographically smaller than {myString2}."); 

    // If value returned by this method is greater than 0
    // Then print the first string is greater than the second string      
    else
        Console.WriteLine(
            {content}quot;{myString1} is lexicographically greater than {myString2}.");

    // If value returned by this method is equal to 0
    // Then print both strings are same         
    if (Compare(myString1, myString3) == 0) 
        Console.WriteLine({content}quot;{myString1} and {myString3} are same."); 

    // If value returned by this method is smaller than 0
    // Then print the first string is smaller than the second string      
    else if (Compare(myString1, myString3) < 0)
        Console.WriteLine(
            {content}quot;{myString1} is lexicographically smaller than {myString3}."); 

    // If value returned by this method is greater than 0
    // Then print the first string is greater than the second string 
    else
        Console.WriteLine(
            {content}quot;{myString1} is lexicographically greater than {myString3}.");

    // If value returned by this method is equal to 0
    // Then print both strings are same             
    if (Compare(myString2, myString3) == 0) 
        Console.WriteLine({content}quot;{myString2} and {myString3} are same."); 

    // If value returned by this method is smaller than 0
    // Then print the first string is smaller than the second string
    else if (Compare(myString2, myString3) < 0)
        Console.WriteLine(
            {content}quot;{myString2} is lexicographically smaller than {myString3}."); 

    // If value returned by this method is greater than 0
    // Then print the first string is greater than the second string 
    else
        Console.WriteLine(
            {content}quot;{myString2} is lexicographically greater than {myString3}.");
}
}
```

**Output**

```cs
GeeksforGeeks is lexicographically greater than Geeks.
GeeksforGeeks and GeeksforGeeks are same.
Geeks is lexicographically smaller than GeeksforGeeks.
```