# 在 C# 中列出 FindLastIndex()方法| Set -2

> 原文:[https://www . geesforgeks . org/list-findlastindex-method-in-c-sharp-set-2/](https://www.geeksforgeeks.org/list-findlastindex-method-in-c-sharp-set-2/)

此方法用于搜索与指定谓词定义的条件相匹配的元素，并返回列表中最后一次出现的从零开始的索引<t>或其一部分。该方法的重载列表中有 3 种方法:</t>

*   **[查找最后索引(谓词< T >)方法](https://www.geeksforgeeks.org/list-findlastindex-method-in-c-sharp-set-1/)***   **[查找最后索引(Int32，谓词< T >)方法](# 2nd)***   **[FindLastIndex(Int32, Int32, Predicate<T>) Method](# 3rd)

    在这里，我们将只讨论最后两种方法。

    #### 查找最后索引(Int32，谓词< T >)方法

    此方法搜索与指定谓词定义的条件匹配的元素，并返回从第一个元素延伸到指定索引的[列表< T >](https://www.geeksforgeeks.org/c-list-class/) 中元素范围内最后一次出现的从零开始的索引。

    > **语法:**public int FindLastIndex(int start，谓语< T >匹配)；
    > 
    > **参数:**
    > **开始**:是搜索开始的起始索引。
    > **匹配**:是谓词委托定义了被搜索元素的条件。

    **返回值:**如果找到该元素，则返回与参数“*匹配*指定条件匹配的元素最后一次出现的类型为 *Int32* 的从零开始的索引。如果没有找到，则返回“ *-1* ”。

    **异常:**

    *   **参数空异常:**如果*匹配*则*为空*。
    *   **argumentout of range exception:**如果*开始*在列表< T >的有效索引范围之外。

    以下程序说明了上述方法的使用:

    **例 1:**

    ```cs
    // C# program to illustrate the 
    // List<T>.FindLastIndex(Int32,
    // Predicate <T>) Method
    using System;
    using System.Collections.Generic;

    class GFG {

        // Main Method
        public static void Main()
        {
            // List creation
            // List name is "PC"
            List<string> PC = new List<string>();

            // elements in the List
            PC.Add("Computer");
            PC.Add("keyboard");
            PC.Add("laptop");
            PC.Add("mouse");

            // the search will starts from index 2
            int indx = PC.FindLastIndex(2, FindIndex);

            Console.WriteLine(indx);
        }

        // Conditional method
        private static bool FindIndex(string g)
        {

            if (g == "Computer") 
            {
                return true;
            }

            else 
            {
                return false;
            }
        }
    }
    ```

    **输出:**

    ```cs
    0

    ```

    **例 2:**

    ```cs
    // C# program to illustrate the 
    // List<T>.FindLastIndex(Int32,
    // Predicate <T>) Method
    using System;
    using System.Collections.Generic;

    class GFG {

        // Main Method
        public static void Main()
        {

            // List creation
            // List name is "PC"
            List<int> PC = new List<int>();

            // elements in the List
            PC.Add(3);
            PC.Add(4);
            PC.Add(5);
            PC.Add(6);

            // condition is "FindIndex"
            int indx = PC.FindLastIndex(2, FindIndex);

            Console.WriteLine(indx);
        }

        // Conditional method
        private static bool FindIndex(int g)
        {

            // search for "5"
            if (g == 5)

            {
                return true;
            }

            else 
            {
                return false;
            }
        }
    }
    ```

    **输出:**

    ```cs
    2

    ```

    **示例 3:** 在本例中，我们使用一个 XML 文件，从起始索引中搜索一个项目，并打印该项目的索引，如果找不到该项目，则打印“-1”，如果找到，则打印索引。物品是“*极客 forgesks*”。但是这里我们没有 XML 文件，这里编译器给出了一个异常。

    ```cs
    // C# program to illustrate the 
    // List<T>.FindLastIndex(Int32,
    // Predicate <T>) Method
    using System;
    using System.Collections.Generic;
    using System.Linq;

    class GFG {

        // here List<T> contains the object "gfg" using
        // data from a sample XML file
        // List initialize
        private static List<gfg> geeks = new List<gfg>();

        public static void Main()
        {

            // if the item is found then
            // it prints the index
            // if not found prints "-1"
            int x = geeks.FindLastIndex(3, FindGFG);
            Console.WriteLine(x);

        }

        // conditional method
        private static bool FindGFG(gfg g)
        {

             // item is "GeeksForGeeks"
            if (g.G == "GeeksForGeeks")
            {
                return true;
            }

            else
            {
                return false;
            }
        }
    }

    public class gfg {

        public string G
        {
            get;
            set;
        }
    }
    ```

    **运行时错误:**

    > 未处理异常:
    > 系统。ArgumentOutOfRange 异常:ArgumentOutOfRange_Index
    > 参数名:startIndex

    #### 查找最后索引(Int32，Int32，谓词< T >)方法

    此方法搜索与指定谓词定义的条件匹配的元素，并返回整个列表中最后一个匹配项的从零开始的索引，该列表包含指定数量的元素，并在指定索引处结束。

    > **语法:**public int FindLastIndex(int startIndex，int count，谓词< T >匹配)；
    > 
    > **参数:**
    > **startIndex** :是后向搜索的从零开始的起始索引。
    > **计数**:是要搜索的区间内的元素个数。
    > **匹配**:谓词< T >委托定义了要搜索的元素的条件。

    **返回值:**如果找到该元素，则返回与参数“match”指定的条件匹配的最后一个元素的 Int32 类型的从零开始的索引。如果没有找到，则返回“-1”。

    **异常:**

    *   **ArgumentNullException:** 如果“*匹配*为空。
    *   **ArgumentOutOfRangeException:**如果“开始索引”在范围之外，或者“计数”小于 0(零)，或者“开始索引”和“计数”不在列表中指定有效的部分

    **示例:**

    ```cs
    // C# Program to illustrate the 
    // FindLastIndex(Int32, Int32, 
    // Predicate<T>) Method
    using System;
    using System.Collections.Generic;

    class GFG
    {
        public static void Main()
        {
            // List name is "mylist"
            List<string> mylist = new List<string>();

            // Elements in the List
            mylist.Add("C");
            mylist.Add("C++");
            mylist.Add("Java");
            mylist.Add("Python");
            mylist.Add("C#");
            mylist.Add("HTML");
            mylist.Add("Java");
            mylist.Add("PHP");

            // the search will starts from index 2
            // the number of element is 3
            int indx = mylist.FindLastIndex(2, 3, FindIndex);

            Console.WriteLine("The index of Java is: "+indx);
        }

        // Conditional method
        private static bool FindIndex(string g)
        {

            if (g == "Java")
            {
                return true;
            }
            else
            {
                return false;
            }
        }
    }
    ```

    **输出:**

    ```cs
    The index of Java is: 2

    ```

    **注:**

    *   列表<t>从*开始搜索*并在第一个元素结束。</t>
    *   谓词<t>是一个方法的委托，如果传递给它的对象与委托中定义的条件相匹配，则该委托返回真。当前列表<t>的元素被单独传递给谓词<t>委托。</t></t></t>
    *   此方法执行线性搜索；因此，这个方法是一个 O(n)运算，其中 n 是从 List <t>开始到开始的元素个数。</t>**