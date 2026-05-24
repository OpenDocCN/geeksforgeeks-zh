# c#–使用字符串作为索引的索引器

> 原文:[https://www . geesforgeks . org/c-sharp-indexers-使用字符串作为索引/](https://www.geeksforgeeks.org/c-sharp-indexers-using-string-as-an-index/)

**先决条件**:c# 中[属性](https://www.geeksforgeeks.org/c-sharp-properties/)

[索引器](https://www.geeksforgeeks.org/c-sharp-indexers/)允许类或结构的实例像数组一样被索引。通过使用索引器，类将表现得像一个虚拟数组。可以在不显式指定类型或实例成员的情况下设置或检索索引值。索引器类似于属性，只是它们的访问器接受参数。索引器几乎类似于 [*属性*](https://www.geeksforgeeks.org/c-sharp-properties/) 。索引器和属性的主要区别在于索引器的访问器将接受参数。

### 使用字符串作为索引的索引器:

这个方法会给你更多的信息，可读性。如果我们想使用字符串作为索引来检索信息。

*示例:*

```cs
ic["username"] = "user12";  
ic["password"] = "12345";  

```

这将比下面给出的代码更具可读性。

```cs
ic[0] = "user12";  
ic[1] = "12345";  

```

**语法:**

```cs
[access_modifier] [return_type] this [argument_list]
{
 get  
 {
    // retrieval code or code to get the value 
 }
 set  
 {
   // code for setting value to member
 }

```

**在上面的语法中:**

*   **access_modifier** :可以是公共的、私有的、受保护的，也可以是内部的。
*   **return_type** :可以是任何有效的 C# 类型。在这种情况下，它将是字符串类型。
*   **这个**:是指向当前类的对象的关键字。
*   **参数 _ 列表**:指定索引器的参数列表。
*   **获取{ }并设置{** **}** :这些是访问器。

**示例:**

## C#

```cs
// C# program to illustrate the Indexers 
// Using String as an Index 
using System; 

// class declaration 
class IndexerPOC 
{ 

    // class members 
    private string[] val = new string[4]; 

    // indexer array 
    private string[] indices={"username","password","email","Book"};

    // Indexer declaration 
    // Here pubic is the modifier 
    // string is the return type of 
    // Indexer and "this" is the keyword 
      // which refer to the calling object.
    // having parameters list 
    public string this[string index] 
    { 

        // get Accessor 
        // retrieving the values 
        // stored in val[] array 
        // of strings using string indexer.
        get
        { 

            return val[Array.IndexOf(indices,index)]; 
        } 

        // set Accessor 
        // setting the value at 
        // passed i of val 
        set
        { 

            // value keyword is used 
            // to define the value 
            // being assigned by the 
            // set indexer. 
            val[ Array.IndexOf(indices,index)] = value; 
        } 
    } 
} 

// Driver Class 
class Program { 

    // Main Method 
    public static void Main() { 

        // creating an object of parent class which 
        // acts as primary address for using Indexer 
        IndexerPOC ic = new IndexerPOC(); 

        // Inserting values in ic[] 
        // Here we are using the object 
        // of class as an array 
        ic["username"] = "user12"; 
        ic["password"] = "12345"; 
        ic["email"] = "user123@gmail.com"; 
        ic["Book"]="CSHARP";
        Console.Write("Printing values stored in objects used as arrays\n"); 

        // printing values 
        Console.WriteLine("UserName = {0}", ic["username"]); 
        Console.WriteLine("Password = {0}", ic["password"]); 
        Console.WriteLine("Email = {0}", ic["email"]); 
        Console.WriteLine("Book = {0}", ic["Book"]); 

    } 
}
```

**输出:**

```cs
Printing values stored in objects used as arrays
UserName = user12
Password = 12345
Email = user123@gmail.com
Book = CSHARP
```