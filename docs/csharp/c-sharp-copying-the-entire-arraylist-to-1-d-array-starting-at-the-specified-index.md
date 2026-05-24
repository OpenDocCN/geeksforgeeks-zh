# C# |从指定索引处开始将整个数组列表复制到一维数组中

> 原文:[https://www . geesforgeks . org/c-sharp-将整个数组列表复制到 1-d-array-从指定索引处开始/](https://www.geeksforgeeks.org/c-sharp-copying-the-entire-arraylist-to-1-d-array-starting-at-the-specified-index/)

**数组列表。CopyTo(Array，Int32)方法**用于将整个[数组列表](https://www.geeksforgeeks.org/c-arraylist-class/)复制到兼容的一维数组中，从目标数组的指定索引处开始。

**语法:**

```cs
public virtual void CopyTo (Array array, int arrayIndex);
```

**参数:**

> **数组:**一维数组是从数组列表中复制的元素的目的地。数组必须具有从零开始的索引。
> 
> **数组索引:**是*数组*中开始复制的从零开始的索引。

**异常:**

*   **参数空异常:**如果*数组*为空。
*   **argumentout of range exception:**如果*数组索引*小于零。
*   **ArgumentException:** 如果数组是多维的 ***或*** 源数组列表中的元素数量大于目标数组可以包含的元素数量。
*   **InvalidCastException:** 如果源数组列表的类型不能自动转换为目标*数组的类型*。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to illustrate the
// ArrayList.CopyTo(Array, Int32)
// Method
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an ArrayList
        ArrayList myList = new ArrayList();

        // Adding elements to ArrayList
        myList.Add("A");
        myList.Add("B");
        myList.Add("C");
        myList.Add("D");

        // Creates and initializes the
        // one-dimensional target Array.
        String[] arr = new String[6];

        // adding elements to Array
        arr[0] = "HTML";
        arr[1] = "PHP";
        arr[2] = "Java";
        arr[3] = "Python";
        arr[4] = "C#";
        arr[5] = "OS";

        Console.WriteLine("Before Method: ");

        Console.WriteLine("\nArrayList Contains: ");

        // Displaying the elements in myList
        for (int i = 0; i < myList.Count; i++) {
            Console.WriteLine("myList[{0}] : {1}", i, myList[i]);
        }

        Console.WriteLine("\nArray Contains: ");

        // Displaying the elements in arr
        for (int i = 0; i < arr.Length; i++) {
            Console.WriteLine("arr[{0}] : {1}", i, arr[i]);
        }

        Console.WriteLine("After Method: ");

        // Copying the entire source ArrayList
        // to the target Array starting at
        // index 2.
        myList.CopyTo(arr, 2);

        Console.WriteLine("\nArrayList Contains: ");

        // Displaying the elements in myList
        for (int i = 0; i < myList.Count; i++) {
            Console.WriteLine("myList[{0}] : {1}", i, myList[i]);
        }

        Console.WriteLine("\nArray Contains: ");

        // Displaying the elements in arr
        for (int i = 0; i < arr.Length; i++) {
            Console.WriteLine("arr[{0}] : {1}", i, arr[i]);
        }
    }
}
```

**输出:**

```cs
Before Method: 

ArrayList Contains: 
myList[0] : A
myList[1] : B
myList[2] : C
myList[3] : D

Array Contains: 
arr[0] : HTML
arr[1] : PHP
arr[2] : Java
arr[3] : Python
arr[4] : C#
arr[5] : OS
After Method: 

ArrayList Contains: 
myList[0] : A
myList[1] : B
myList[2] : C
myList[3] : D

Array Contains: 
arr[0] : HTML
arr[1] : PHP
arr[2] : A
arr[3] : B
arr[4] : C
arr[5] : D

```

**例 2:**

```cs
// C# code to illustrate the
// ArrayList.CopyTo(Array, Int32)
// Method
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating an ArrayList
        ArrayList myList = new ArrayList();

        // Adding elements to ArrayList
        myList.Add("A");
        myList.Add("B");
        myList.Add("C");
        myList.Add("D");

        // Creates and initializes the
        // one-dimensional target Array.
        // Here array size is only 2 i.e
        // it can hold only 3 elements.
        String[] arr = new String[2];

        Console.WriteLine("Before Method: ");

        Console.WriteLine("\nArrayList Contains: ");

        // Displaying the elements in myList
        for (int i = 0; i < myList.Count; i++) {
            Console.WriteLine("myList[{0}] : {1}", i, myList[i]);
        }

        Console.WriteLine("\nArray Contains: ");

        // Displaying the elements in arr
        for (int i = 0; i < arr.Length; i++) {
            Console.WriteLine("arr[{0}] : {1}", i, arr[i]);
        }

        Console.WriteLine("After Method: ");

        // using Method but It will give
        // Runtime Error as number of elements
        // in the source ArrayList is greater
        // than the number of elements that
        // the destination array can contain
        myList.CopyTo(arr, 2);

        Console.WriteLine("\nArrayList Contains: ");

        // Displaying the elements in myList
        for (int i = 0; i < myList.Count; i++) {
            Console.WriteLine("myList[{0}] : {1}", i, myList[i]);
        }

        Console.WriteLine("\nArray Contains: ");

        // Displaying the elements in arr
        for (int i = 0; i < arr.Length; i++) {
            Console.WriteLine("arr[{0}] : {1}", i, arr[i]);
        }
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。参数异常:目标数组不够长。检查目标索引和长度，以及数组的下限
> 参数名称:目标数组

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . ArrayList . copy to？view = net framework-4 . 7 . 2 # System _ Collections _ ArrayList _ copy to _ System _ Array _ System _ int 32 _](https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist.copyto?view=netframework-4.7.2# System_Collections_ArrayList_CopyTo_System_Array_System_Int32_)