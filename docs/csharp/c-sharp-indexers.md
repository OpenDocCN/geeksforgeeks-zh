# C# |索引器

> 原文:[https://www.geeksforgeeks.org/c-sharp-indexers/](https://www.geeksforgeeks.org/c-sharp-indexers/)

#### 先决条件:[c# 中的属性](https://www.geeksforgeeks.org/c-properties/)

索引器允许将类或结构的实例作为数组进行索引。如果用户将为一个类定义索引器，那么这个类将表现得像一个虚拟数组。数组访问运算符(即 **[ ]** )用于访问使用索引器的类的实例。用户可以在不指向实例或类型成员的情况下检索或设置索引值。索引器几乎类似于 [**属性**](https://www.geeksforgeeks.org/c-properties/) 。*索引器与* [*属性*](https://www.geeksforgeeks.org/c-properties/) 的主要区别在于索引器的[取值器](https://www.geeksforgeeks.org/c-properties/)会取参数。

**语法:**

```cs
[access_modifier] [return_type] this [argument_list]
{
  get 
  {
     // get block code
  }
  set 
  {
    // set block code
  }

}
```

在上面的语法中:

*   [T0】 access _ modifier: It can be public, private, protected or internal.
*   **return _ type:** can be any valid C# type.
*   **This:** is a keyword pointing to the object of the current class.
*   **Parameter _ list:** Specify the parameter list of indexer.
*   **Get {} and set {}:** These are [Visitors](https://www.geeksforgeeks.org/c-properties/) .

**例:**

## c#

```cs
// C# program to illustrate the Indexer
using System;

// class declaration
class IndexerCreation
{

    // class members
    private string[] val = new string[3];

    // Indexer declaration
    // public - access modifier
    // string - the return type of the Indexer
      // this - is the keyword having a parameters list
    public string this[int index]
    {

        // get Accessor
        // retrieving the values
        // stored in val[] array
        // of strings
        get
        {

            return val[index];
        }

        // set Accessor
        // setting the value at
        // passed index of val
        set
        {

            // value keyword is used
            // to define the value
            // being assigned by the
            // set indexer.
            val[index] = value;
        }
    }
}

// Driver Class
class main {

    // Main Method
    public static void Main() {

        // creating an object of parent class which
        // acts as primary address for using Indexer
        IndexerCreation ic = new IndexerCreation();

        // Inserting values in ic[]
        // Here we are using the object
        // of class as an array
        ic[0] = "C";
        ic[1] = "CPP";
        ic[2] = "CSHARP";

        Console.Write("Printing values stored in objects used as arrays\n");

        // printing values
        Console.WriteLine("First value = {0}", ic[0]);
        Console.WriteLine("Second value = {0}", ic[1]);
        Console.WriteLine("Third value = {0}", ic[2]);

    }
}
```

**输出:**

```cs
Printing values stored in objects used as arrays
First value = C
Second value = CPP
Third value = CSHARP
```

**关于索引器的要点:**

*   There are two types of indexers, namely **one-dimensional indexer** & [**multi-dimensional indexer**](https://www.geeksforgeeks.org/c-multidimensional-indexers/) . What is discussed above is a one-dimensional indexer.
*   The indexer may be overloaded.
*   These are different from [**attributes**](https://www.geeksforgeeks.org/c-properties/) .
*   This enables the object to be indexed in an array-like manner.
*   The collection accessor will always assign a value, while the acquisition accessor will return a value.
*   " *This* " keyword is always used to declare an indexer.
*   Define the value assigned by the set indexer, and use the keyword *value* .
*   The indexer is also called *intelligent array* or *parameterized property* in C#.
*   An indexer cannot be a static member because it is an instance member of a class.