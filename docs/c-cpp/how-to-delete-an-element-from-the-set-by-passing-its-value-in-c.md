# 如何通过在 C++ 中传递元素的值来从集合中删除元素

> 原文:[https://www . geeksforgeeks . org/如何通过在 c 中传递元素的值来从集合中删除元素/](https://www.geeksforgeeks.org/how-to-delete-an-element-from-the-set-by-passing-its-value-in-c/)

给定一个[集合](https://www.geeksforgeeks.org/set-in-cpp-stl/)，任务是在 C++ 中移除这个[集合](https://www.geeksforgeeks.org/set-in-cpp-stl/)中的最后一个元素。
**例:**

```cpp
Input: set = [10 20 30 70 80 90 100 40 50 60],
              valueOfElementToBeDeleted = 100
Output: 10 20 30 40 50 60 70 80 90

Input: set = [1 2 3 4 5],
              valueOfElementToBeDeleted = 3
Output: 1 2 4 5
```

[集合](https://www.geeksforgeeks.org/set-in-cpp-stl/)是一种关联容器，其中每个元素必须是唯一的，因为元素的值标识了它。元素的值一旦添加到集合中就不能修改，尽管可以移除和添加该元素的修改值。
**方法:**在该方法中，通过使用 erase 函数并以最后一个元素的值作为参数调用它来删除最后一个元素。如果最后一个元素的值未知，则使用前面的方法。
**语法:**

```cpp
size_type erase (const value_type& valueOfElementToBeDeleted);
```

以下是上述方法的实现:

## C++

```cpp
// C++ program to delete an element
// of a Set by passing its value

#include <iostream>
#include <set>
using namespace std;

// Function to print the set
void printSet(set<int> myset)
{

    // Get the iterator
    set<int>::iterator it;

    // printing all the elements of the set
    for (it = myset.begin(); it != myset.end(); ++ it)
        cout << ' ' << *it;
    cout << '\n';
}

// Function to delete the element of set
void deleteByValue(set<int> myset,
           int valueOfElementToBeDeleted)
{

    // printing all the elements of the set
    cout << "\nSet originally: ";
    printSet(myset);

    // Erase the element that is equal to
    // the value passed as the parameter
    myset.erase(valueOfElementToBeDeleted);

    // printing all the elements of the set
    cout << "Set after deleting "
         << valueOfElementToBeDeleted
         << ": ";
    printSet(myset);
}

// Driver code
int main()
{
    set<int> myset;

    // Get the set
    for (int i = 1; i < 10; i++)
        myset.insert(i * 10);

    // Get the valueOfElementToBeDeleted
    int valueOfElementToBeDeleted = 50;

    // Delete an element from the Set
    deleteByValue(myset, valueOfElementToBeDeleted);

    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to delete an element
// of a Set by passing its value
import java.io.*;
import java.util.*;
class GFG
{

  // Function to print the set
  static void printSet(TreeSet<Integer> myset)
  {

    // printing all the elements of the set
    for(int it : myset)
    {
      System.out.print(it + " ");
    }
    System.out.println();
  }

  // Function to delete the element of set
  static void deleteByValue(TreeSet<Integer> myset, 
                            int valueOfElementToBeDeleted)
  {

    // printing all the elements of the set
    System.out.print("\nSet originally: ");
    printSet(myset);

    // Erase the element that is equal to
    // the value passed as the parameter
    myset.remove(valueOfElementToBeDeleted);

    // printing all the elements of the set
    System.out.print("Set after deleting " +
                     valueOfElementToBeDeleted +  ": ");
    printSet(myset);
  }

  // Driver code
  public static void main (String[] args)
  {

    //Set<Integer> myset = new HashSet<Integer>();
    TreeSet<Integer> myset = new TreeSet<Integer>();

    // Get the set
    for (int i = 1; i < 10; i++)
    {
      myset.add(i * 10);
    }

    // Get the valueOfElementToBeDeleted
    int valueOfElementToBeDeleted = 50;

    // Delete an element from the Set
    deleteByValue(myset, valueOfElementToBeDeleted);
  }
}

// This code is contributed by avanitrachhadiya2155
```

## 蟒蛇 3

```cpp
# Python3 program to delete an element of a
# set by passing of a set by passing its value

# function to print the set
def printset(myset):

    for i in myset:
        print(i, end = " ")
    print()

# function to delete the element of a set
def deleteByValue(myset, value):

    myset = sorted(myset)

    # printint original value
    print("Set originally:", end = " ")
    printset(myset)

    # Erase the element that is equal to
    # the value passed as the parameter
    myset.remove(value)

    # printing all the elements of the set
    print("Set after deleting", value,
                        ":", end = " ")
    printset(myset)

# Driver code
myset = set()

for i in range(1, 10):
    myset.add(i * 10)

# Get the valueOfElementToBeDeleted
value = 50

# Delete an element from the Set
deleteByValue(myset, value);

# This code is contributed
# by Mohit kumar 29
```

## C#

```cpp
// C# program to delete an element
// of a Set by passing its value
using System;
using System.Collections.Generic;
public class GFG
{

  // Function to print the set
  static void printSet(HashSet<int> myset)
  {

    // printing all the elements of the set
    foreach(int it in myset)
    {
      Console.Write(it + " ");
    }
    Console.WriteLine();
  }

  // Function to delete the element of set
  static void deleteByValue(HashSet<int> myset, int valueOfElementToBeDeleted)
  {

    // printing all the elements of the set
    Console.Write("\nSet originally: ");
    printSet(myset);

    // Erase the element that is equal to
    // the value passed as the parameter
    myset.Remove(valueOfElementToBeDeleted);

    // printing all the elements of the set
    Console.Write("Set after deleting " + valueOfElementToBeDeleted +  ": ");
    printSet(myset);
  }

  // Driver code
  static public void Main ()
  {
    //Set<Integer> myset = new HashSet<Integer>();
    HashSet<int> myset = new HashSet<int>();

    // Get the set
    for (int i = 1; i < 10; i++)
    {
      myset.Add(i * 10);
    }

    // Get the valueOfElementToBeDeleted
    int valueOfElementToBeDeleted = 50;

    // Delete an element from the Set
    deleteByValue(myset, valueOfElementToBeDeleted);
  }
}

// This code is contributed by rag2127
```

## java 描述语言

```cpp
<script>

// JavaScript program to delete an element
// of a Set by passing its value

 // Function to print the set
function printSet(myset)
{
    // printing all the elements of the set
    for(let it of myset.values())
    {
      document.write(it + " ");
    }
    document.write("<br>");
}

 // Function to delete the element of set
function deleteByValue(myset, valueOfElementToBeDeleted)
{
    // printing all the elements of the set
    document.write("<br>Set originally: ");
    printSet(myset);

    // Erase the element that is equal to
    // the value passed as the parameter
    myset.delete(valueOfElementToBeDeleted);

    // printing all the elements of the set
    document.write("Set after deleting " +
                     valueOfElementToBeDeleted +  ": ");
    printSet(myset);
}

// Driver code

//Set<Integer> myset = new HashSet<Integer>();
    let myset = new Set();

    // Get the set
    for (let i = 1; i < 10; i++)
    {
      myset.add(i * 10);
    }

    // Get the valueOfElementToBeDeleted
    let valueOfElementToBeDeleted = 50;

    // Delete an element from the Set
    deleteByValue(myset, valueOfElementToBeDeleted);

// This code is contributed by patel2127

</script>
```

**Output:** 

```cpp
Set originally:  10 20 30 40 50 60 70 80 90
Set after deleting 50:  10 20 30 40 60 70 80 90
```