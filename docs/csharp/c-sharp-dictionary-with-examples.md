# C# 带示例词典

> 原文:[https://www . geesforgeks . org/c-sharp-dictionary-with-examples/](https://www.geeksforgeeks.org/c-sharp-dictionary-with-examples/)

在 C# 中，字典是一个通用集合，通常用于存储键/值对。字典的工作方式与[非通用散列表](https://www.geeksforgeeks.org/c-sharp-hashtable-with-examples/)非常相似。字典的优点是，它是泛型。字典在`System.Collection.Generic`命名空间下定义。它本质上是动态的，意味着字典的大小是根据需要而增长的。

**要点:**

*   字典类实现了
    *   附属< TKey，tvalue>t1】接口
    *   *ireadolicollection<key value pair<tkey，tvalue>t5*界面
    *   爱尔兰语词典<【tkey，tvalue】>t1】界面
    *   *接口字典*接口
*   在字典中，关键字不能为空，但值可以为空。
*   在字典中，关键字必须是唯一的。重复键是不允许的。如果你试图使用重复键，编译器会抛出一个异常。
*   在字典中，您只能存储相同类型的元素。
*   字典的容量是字典可以容纳的元素数量。

#### 如何创建字典？

字典类有 *7 个构造函数*用来创建字典，这里我们只使用字典< TKey，tvvalue>()构造函数，如果想了解更多关于构造函数的知识，那就参考**T3】c# |字典类 T5】。**

**字典< TKey，tvvalue>():**此构造函数用于创建字典< TKey，tvvalue>类的实例，该类为空，具有默认的初始容量，并使用默认的相等比较器作为键类型，如下所示:

**步骤 1:** 包含系统。集合。在使用关键字的帮助下，程序中的泛型命名空间。

**语法:**

```cs
using System.Collection.Generics; 
```

**步骤 2:** 使用字典<创建字典，如下所示的 TKey，TValue >类:

```cs
Dictionary dictionary_name = new Dictionary();
```

**第三步:**如果你想在你的字典中添加元素，那么使用 [Add()](https://www.geeksforgeeks.org/c-sharp-dictionary-add-method/) 方法在你的字典中添加键/值对。您也可以不使用 add 方法在字典中添加键/值对。如下例所示。

**步骤 4:** 使用**三种不同的方式访问字典的键/值对:**

*   **for loop:** You can use for loop to access the key/value pairs of the Dictionary.

    **示例:**

    ```cs
    for(int x=0; i< My_dict1.Count; x++)
    {
        Console.WriteLine("{0} and {1}", My_dict1.Keys.ElementAt(x), 
                             My_dict1[ My_dict1.Keys.ElementAt(x)]);
    }
    ```

*   **Using Index:** You can access individual key/value pair of the Dictionary by using its index value. Here, you just specify the key in the index to get the value from the given dictionary, no need to specify the index. Indexer always takes the key as a parameter, if the given key is not available in the dictionary, then it gives *KeyNotFoundException*.

    **示例:**

    ```cs
    Console.WriteLine("Value is:{0}", My_dicti[1123]);
    Console.WriteLine("Value is:{0}", My_dicti[1125]);
    ```

*   **foreach 循环:**可以使用 foreach 循环访问字典的键/值对。如下例所示，我们使用 foreach 循环访问字典。

**示例:**

```cs
// C# program to illustrate how 
// to create a dictionary
using System;
using System.Collections.Generic;  

class GFG {

        // Main Method 
    static public void Main () {

        // Creating a dictionary
        // using Dictionary<TKey,TValue> class
        Dictionary<int, string> My_dict1 =  
                       new Dictionary<int, string>(); 

          // Adding key/value pairs 
          // in the Dictionary
          // Using Add() method
          My_dict1.Add(1123, "Welcome");
          My_dict1.Add(1124, "to");
          My_dict1.Add(1125, "GeeksforGeeks");

          foreach(KeyValuePair<int, string> ele1 in My_dict1)
          {
              Console.WriteLine("{0} and {1}",
                        ele1.Key, ele1.Value);
          }
          Console.WriteLine();

          // Creating another dictionary
          // using Dictionary<TKey,TValue> class
      // adding key/value pairs without
          // using Add method
      Dictionary<string, string> My_dict2 =  
              new Dictionary<string, string>(){
                                  {"a.1", "Dog"},
                                  {"a.2", "Cat"},
                                {"a.3", "Pig"} }; 

          foreach(KeyValuePair<string, string> ele2 in My_dict2)
          {
              Console.WriteLine("{0} and {1}", ele2.Key, ele2.Value);
          }
    }
}
```

**Output:**

```cs
1123 and Welcome
1124 and to
1125 and GeeksforGeeks

a.1 and Dog
a.2 and Cat
a.3 and Pig

```

#### 如何从字典中删除元素？

在字典中，您可以从字典中移除元素。字典<tkey tvalue="">类提供了两种不同的方法来移除元素，这两种方法是:</tkey>

*   **[清除](https://www.geeksforgeeks.org/c-sharp-dictionary-clear-method/) :** 此方法从字典< TKey、TValue >中移除所有键和值。
*   **[移除](https://www.geeksforgeeks.org/c-sharp-dictionary-remove-method/) :** 此方法从字典< TKey、TValue >中移除具有指定键的值。

**示例:**

```cs
// C# program to illustrate how 
// remove key/value pairs from 
// the dictionary
using System;
using System.Collections.Generic;  

class GFG {

        // Main Method
    static public void Main() {

        // Creating a dictionary
        // using Dictionary<TKey,TValue> class
        Dictionary<int, string> My_dict =  
                     new Dictionary<int, string>(); 

          // Adding key/value pairs in the 
          // Dictionary Using Add() method
          My_dict.Add(1123, "Welcome");
          My_dict.Add(1124, "to");
          My_dict.Add(1125, "GeeksforGeeks");

          // Before Remove() method
          foreach(KeyValuePair<int, string> ele in My_dict)
          {
              Console.WriteLine("{0} and {1}", 
                          ele.Key, ele.Value);
          }
          Console.WriteLine();

          // Using Remove() method 
          My_dict.Remove(1123);

          // After Remove() method
          foreach(KeyValuePair<int, string> ele in My_dict)
          {
              Console.WriteLine("{0} and {1}",
                          ele.Key, ele.Value);
          }
          Console.WriteLine();

          // Using Clear() method
          My_dict.Clear();

          Console.WriteLine("Total number of key/value "+
           "pairs present in My_dict:{0}", My_dict.Count);

    }
}
```

**Output:**

```cs
1123 and Welcome
1124 and to
1125 and GeeksforGeeks

1124 and to
1125 and GeeksforGeeks

Total number of key/value pairs present in My_dict:0

```

#### 如何检查字典中元素的可用性？

在字典中，您可以检查给定的键或值是否存在于指定的字典中。字典<tkey tvalue="">类提供了两种不同的检查方法，这两种方法是:</tkey>

*   **[ContainsKey](https://www.geeksforgeeks.org/c-sharp-dictionary-containskey-method/) :** 此方法用于检查字典< TKey，TValue >是否包含指定的 Key。
*   **[ContainsValue](https://www.geeksforgeeks.org/c-sharp-dictionary-containsvalue-method/) :** 此方法用于检查字典< TKey、tvvalue>是否包含特定值。

**示例:**

```cs
// C# program to illustrate how
// to  check the given key or 
// value present in the dictionary
// or not
using System;
using System.Collections.Generic;  

class GFG {

        // Main Method
    static public void Main () {

                 // Creating a dictionary
        // using Dictionary<TKey,TValue> class
        Dictionary<int, string> My_dict =  
                      new Dictionary<int, string>(); 

          // Adding key/value pairs in the 
          // Dictionary Using Add() method
          My_dict.Add(1123, "Welcome");
          My_dict.Add(1124, "to");
          My_dict.Add(1125, "GeeksforGeeks");

          // Using ContainsKey() method to check
          // the specified key is present or not
          if (My_dict.ContainsKey(1122)==true)
          {
              Console.WriteLine("Key is found...!!");
          }

          else
          {
               Console.WriteLine("Key is not found...!!");
          }

          // Using ContainsValue() method to check
          // the specified value is present or not
          if (My_dict.ContainsValue("GeeksforGeeks")==true)
          {
              Console.WriteLine("Value is found...!!");
          }

          else
          {
               Console.WriteLine("Value is not found...!!");
          }
    }
}
```

**Output:**

```cs
Key is not found...!!
Value is found...!!

```