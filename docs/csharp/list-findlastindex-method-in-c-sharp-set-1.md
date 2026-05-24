# 在 C# 中列出 FindLastIndex()方法| Set -1

> 原文:[https://www . geesforgeks . org/list-findlastindex-method-in-c-sharp-set-1/](https://www.geeksforgeeks.org/list-findlastindex-method-in-c-sharp-set-1/)

此方法用于搜索与指定谓词定义的条件相匹配的元素，并返回列表中最后一次出现的从零开始的索引<t>或其一部分。该方法的重载列表中有 3 种方法:</t>

*   **查找最后索引(谓词<t>)方法</t>***   **FindLastIndex(Int32，谓词<t>)方法</t>***   **FindLastIndex(Int32, Int32, Predicate<T>) Method

    这里我们只讨论第一种方法，即 *FindLastIndex(谓词< T > )*

    **列表< T >。FindLastIndex(谓词< T >)方法**搜索与指定谓词定义的条件匹配的元素，并返回整个[列表< T >](https://www.geeksforgeeks.org/c-list-class/) 中最后一次出现的从零开始的索引。

    **语法:**

    ```cs
    public int FindLastIndex (Predicate <T> match);
    ```

    这里，*匹配*是谓词< T >委托，它定义了要搜索的元素的条件。

    **返回值:**如果找到该元素，则返回与参数“match”指定的条件匹配的最后一个元素的 int 或 Int32 类型的从零开始的索引。如果没有找到，则返回“-1”。

    **异常:**如果`match`为空，该方法将抛出 *ArgumentNullException* 。

    **示例 1:** 在本例中，创建一个名为“PC”的列表，其中包含一些元素。我们的任务是找到一个名为“Computer”的元素并打印它的索引。

    ```cs
    // C# Program to illustrate the 
    // FindLastIndex(Predicate<T>)
    // Method
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
            PC.Add("mouse");
            PC.Add("keyboard");
            PC.Add("laptop");
            PC.Add("Computer");

            // using the method
            int indx = PC.FindLastIndex(predi);

            Console.WriteLine(indx);
        }

        // Conditional method
        private static bool predi(string g)
        {

            if (g == "Computer") {
                return true;
            }
            else {
                return false;
            }
        }
    }
    ```

    **Output:**

    ```cs
    3

    ```

    **例 2:** 本例是上例的扩展形式。在本例中，我们使用一个 XML 文件搜索一个项目，并打印该项目的索引。如果没有找到该项目，则打印“-1”，如果找到，则打印索引。物品是“极客巧克力”。

    ```cs
    // C# Program to illustrate the 
    // FindLastIndex(Predicate<T>)
    // Method
    using System;
    using System.Collections.Generic;
    using System.Linq;

    class GFG {

        // here List<T> contains the
        // object "gfg" using
        // data from a sample XML file
        // "geeks" is the List name
        private static List<gfg> geeks = new List<gfg>();

        // Main Method
        public static void Main()
        {

            // if the item is found 
            // then it prints the index
            // if not found prints "-1"
            int x = geeks.FindLastIndex(FindGFG);
            Console.WriteLine(x); 
        }

        // conditional method
        private static bool FindGFG(gfg g)
        {

            if (g.G == "GeeksForGeeks")
            {
                return true;
            }
            else {
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

    **Output:**

    ```cs
    -1

    ```

    **注:**

    *   列表<t>从最后一个元素开始向后搜索，到第一个元素结束。</t>
    *   谓词<t>是一个方法的委托，如果传递给它的对象与委托中定义的条件相匹配，则该委托返回真。当前列表<t>的元素被单独传递给谓词<t>委托。</t></t></t>
    *   此方法执行线性搜索；因此，这个方法是一个 O(n)运算，其中 n 是 Count。

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . list-1 . findlastindex？view = net framework-4 . 7 . 2 # System _ Collections _ Generic _ List _ 1 _ FindLastIndex _ System _ Predicate _ 0 _ _](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.findlastindex?view=netframework-4.7.2# System_Collections_Generic_List_1_FindLastIndex_System_Predicate__0__)**