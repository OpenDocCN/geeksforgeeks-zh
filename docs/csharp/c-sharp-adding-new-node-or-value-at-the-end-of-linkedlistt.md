# C# |在链表末尾添加新节点或值

> 原文:[https://www . geeksforgeeks . org/c-sharp-添加新节点-或-链接末端值-istt/](https://www.geeksforgeeks.org/c-sharp-adding-new-node-or-value-at-the-end-of-linkedlistt/)

**链接列表< T >。AddLast** 方法用于在链表的末尾添加一个新的节点或值< T >。此方法的重载列表中有 2 种方法，如下所示:

*   **AddLast(链接列表***   **AddLast(T)

    #### add last(linked listnode<**t**>

    该方法用于在链表的末尾添加指定的新节点< **T** >。

    **语法:**

    ```cs
    public void AddLast (System.Collections.Generic.LinkedListNode<T> node);

    ```

    在这里， ***节点*** 是新的 LinkedListNode < **T** >添加到 LinkedList 的末尾< **T** >。

    **异常:**

    *   **ArgumentNullException :** 如果节点为空。
    *   **无效操作异常:**如果节点属于另一个链接列表< **T** >。

    **示例:**

    ```cs
    // C# code to add new node
    // at the end of LinkedList
    using System;
    using System.Collections;
    using System.Collections.Generic;

    class GFG {

        // Driver code
        public static void Main()
        {
            // Creating a LinkedList of Integers
            LinkedList<int> myList = new LinkedList<int>();

            // Adding nodes in LinkedList
            myList.AddLast(2);
            myList.AddLast(4);
            myList.AddLast(6);
            myList.AddLast(6);
            myList.AddLast(6);
            myList.AddLast(8);

            // To get the count of nodes in LinkedList
            // before removing all the nodes
            Console.WriteLine("Total nodes in myList are : " + myList.Count);

            // Displaying the nodes in LinkedList
            foreach(int i in myList)
            {
                Console.WriteLine(i);
            }

            // Adding new node at the end of LinkedList
            // This will give error as node is null
            myList.AddLast(null);

            // To get the count of nodes in LinkedList
            // after removing all the nodes
            Console.WriteLine("Total nodes in myList are : " + myList.Count);

            // Displaying the nodes in LinkedList
            foreach(int i in myList)
            {
                Console.WriteLine(i);
            }
        }
    }
    ```

    **运行时错误:**

    > 未处理异常:
    > 系统。ArgumentNullException:值不能为空。
    > 参数名称:节点

    **注:**

    *   链接列表< **T** >接受 *null* 作为引用类型的有效值，并允许重复值。
    *   如果链接列表< **T** >为空，新节点将成为*第一个*和*最后一个*。
    *   这个方法是一个 O(1)运算。

    #### 添加最后一个方法

    该方法用于在链表<**T**T2 末尾添加一个包含指定值的新节点。

    **语法:**

    ```cs
    public System.Collections.Generic.LinkedListNode<T> AddLast (T value);

    ```

    这里， ***值*** 是链接列表< **T** >末尾要添加的值。

    **返回值:**包含值的新链接列表节点< **T** >。

    **示例:**

    ```cs
    // C# code to add new node containing
    // the specified value at the end
    // of LinkedList
    using System;
    using System.Collections;
    using System.Collections.Generic;

    class GFG {

        // Driver code
        public static void Main()
        {
            // Creating a LinkedList of Integers
            LinkedList<int> myList = new LinkedList<int>();

            // Adding nodes in LinkedList
            myList.AddLast(2);
            myList.AddLast(4);
            myList.AddLast(6);
            myList.AddLast(6);
            myList.AddLast(6);
            myList.AddLast(8);

            // To get the count of nodes in LinkedList
            // before removing all the nodes
            Console.WriteLine("Total nodes in myList are : " + myList.Count);

            // Displaying the nodes in LinkedList
            foreach(int i in myList)
            {
                Console.WriteLine(i);
            }

            // Adding new node containing the
            // specified value at the end of LinkedList
            myList.AddLast(20);

            // To get the count of nodes in LinkedList
            // after removing all the nodes
            Console.WriteLine("Total nodes in myList are : " + myList.Count);

            // Displaying the nodes in LinkedList
            foreach(int i in myList)
            {
                Console.WriteLine(i);
            }
        }
    }
    ```

    **输出:**

    ```cs
    Total nodes in myList are : 6
    2
    4
    6
    6
    6
    8
    Total nodes in myList are : 7
    2
    4
    6
    6
    6
    8
    20

    ```

    **注:**

    *   链接列表< **T** >接受 *null* 作为引用类型的有效值，并允许重复值。
    *   如果链接列表< **T** >为空，新节点将成为*第一个*和*最后一个*。
    *   这个方法是一个 O(1)运算。

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . linked list-1 . add last？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.linkedlist-1.addlast?view=netframework-4.7.2)**