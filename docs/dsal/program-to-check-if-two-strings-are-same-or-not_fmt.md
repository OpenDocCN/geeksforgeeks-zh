# 检查两个字符串是否相同的程序

> 原文: [https://www.geeksforgeeks.org/program-to-check-if-two-strings-are-same-or-not/](https://www.geeksforgeeks.org/program-to-check-if-two-strings-are-same-or-not/)

给定两个字符串，任务是检查这两个字符串是否相同。

**示例:**

> **输入:** `string1 = "geeksforgeks"`，`string2 = "geeksforgeks"`
> **输出:** 是
>
> **输入:** `string1 = "geeks for geeks"`，`string2 = "geeks for geeks"`
> **输出:** 是
>
> **输入:** `string1 = "GeeksforGeeks"`，`string2 = "Geeks"`
> **输出:** 否
>
> **输入:** `string1 = "geeks for geeks"`，`string2 = "Geeks for geeks"`
> **输出:** 否

**方法:** 这可以借助 C 中的 [`strcmp()`](https://www.geeksforgeeks.org/strcmp-in-c-cpp/) 方法来完成，请注意，该方法区分大小写。

**实施:**

## C++

```cpp
// C++ program to check if
// two strings are identical
#include <bits/stdc++.h>
using namespace std;

int main()
{

    char string1[100], string2[100];

    // Get the strings which
    // is to be checked
    cin >> string1;
    cout << "Enter the first string: " << string1;

    // Get the strings which
    // is to be checked
    cin >> string2;
    cout << "\nEnter the second string: " << string2;

    // Check if both strings are equal
    cout << "\nAre both strings same: ";

    if (strcmp(string1, string2) == 0)
    {
        cout << "Yes";
    }
    else {
        cout << "No";
    }

    return 0;
}

// This code is contributed by Akanksha Rai
```

## C

```c
// C program to check if
// two strings are identical

#include <stdio.h>
#include <string.h>

int main()
{

    char string1[100], string2[100];

    // Get the strings which
    // is to be checked
    scanf("%[^\n]\ns", string1);
    printf("Enter the first string: %s", string1);

    // Get the strings which
    // is to be checked
    scanf("%[^\n]\ns", string2);
    printf("\nEnter the second string: %s", string2);

    // Check if both strings are equal
    printf("\nAre both strings same: ");

    if (strcmp(string1, string2) == 0) {
        printf("Yes");
    }
    else {
        printf("No");
    }

    return 0;
}
```

## Java

```java
// Java program to check if
// two strings are identical
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        Scanner in = new Scanner(System.in);

        // Get the strings which is to be checked
        String string1 = in.nextLine();
        System.out.println("Enter the first string: "
                           + string1);

        // Get the strings which is to be checked
        String string2 = in.nextLine();
        System.out.println("Enter the second string :"
                           + string2);

        // Check if both strings are equal
        System.out.println("\nAre both strings same: ");

        if (string1.equals(string2) == true) {
            System.out.println("Yes");
        }
        else {
            System.out.println("No");
        }
    }
}

// This code is contributed by aishwarya.27
```

## Python 3

```python
# Python program to check if
# two strings are identical

if __name__ == "__main__" :

    # Get the strings which
    # is to be checked
    string1 = input("Enter the first string: ")
    print(string1, end = "\n")

    # Get the strings which
    # is to be checked
    string2 = input("Enter the second string: ")
    print(string2, end ="\n")

    # Check if both strings are equal
    print("Are both strings same: ", end = " ")

    if (string1 == string2) :
        print("Yes")

    else :
        print("No")

# This code is contributed by Ryuga
```

## C#

```csharp
// C# program to check if
// two strings are identical
using System;

class GFG {

    // Driver code
    public static void Main()
    {

        // Get the strings which is to be checked
        String string1 = Console.ReadLine();
        Console.WriteLine("Enter the first string: "
                          + string1);

        // Get the strings which is to be checked
        String string2 = Console.ReadLine();
        Console.WriteLine("Enter the second string :"
                          + string2);

        // Check if both strings are equal
        Console.WriteLine("\nAre both strings same: ");

        if (string1.Equals(string2) == true) {
            Console.WriteLine("Yes");
        }
        else {
            Console.WriteLine("No");
        }
    }
}

/* This code contributed by PrinciRaj1992 */
```

## PHP

```php
<?php
// PHP program to check if
// two strings are identical

// Get the strings which
// is to be checked
$string1 = readline();
echo "Enter the first string: $string1";

// Get the strings which
// is to be checked
$string2 = readline();
echo "\nEnter the second string: $string2";

// Check if both strings are equal
echo "\nAre both strings same: ";

if (strcmp($string1, $string2) == 0)
{
    echo "Yes";
}

else if (strcmp($string1, $string2) > 0) //Because string1 has some character greater than string2
{
    echo "No";
}

else if (strcmp($string1, $string2) < 0) //Because string2 has some character greater than string1
{
    echo "No";
}

// This code is contributed by Ashutosh Tiwari

?>
```

**输出:**

```
Enter the first string: GeeksForGeeks
Enter the second string: GeeksForGeeks
Are both strings same: Yes
```