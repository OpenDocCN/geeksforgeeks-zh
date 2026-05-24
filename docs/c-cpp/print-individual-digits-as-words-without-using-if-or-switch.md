# 不使用 if 或 switch 将单个数字打印为文字

> 原文:[https://www . geesforgeks . org/print-personal-digits-as-word-不使用 if-or-switch/](https://www.geeksforgeeks.org/print-individual-digits-as-words-without-using-if-or-switch/)

给定一个数字，打印单个数字的单词。不允许使用 if 或 switch。
示例:

```cpp
Input:  n = 123
Output: One Two Three

Input:  n = 350
Output: Three Five Zero
```

**我们强烈建议你尽量减少浏览器，先自己试试这个。**
这个想法是使用字符串数组来存储数字到单词的映射。以下是步骤。
输入数字为 n

1.  创建一个字符串数组来存储数字到单词的映射。
2.  创建另一个数组数字[]来存储 n 的单个数字。
3.  遍历 n 个数字，并将其存储在数字[]中。请注意，通过重复存储 n%10 并做 n = n/10，遍历的标准方式是以相反的顺序遍历数字。
4.  从头到尾遍历数字数组，并使用步骤 1 中创建的映射打印单词。

以下是上述想法的实现。

## C++

```cpp
// C++ program to print individual words without if and
// without switch
#include <bits/stdc++.h>
using namespace std;

// To store digit to word mapping
char word[][10] = {"zero", "one", "two", "three","four",
                   "five", "six", "seven", "eight", "nine"};

void printWordsWithoutIfSwitch(int n)
{
    // Store individual digits
    int digits[10]; // a 32 bit int has at-most 10 digits

    int dc = 0; // Initialize digit count for given number 'n'

    // The below loop stores individual digits of n in
    // reverse order. do-while is used to handle "0" input
    do
    {
        digits[dc] = n%10;
        n = n/10;
        dc++ ;
    } while (n != 0);

    // Traverse individual digits and print words using
    // word[][]
    for (int i=dc-1; i>=0; i--)
       cout << word[digits[i]] << " ";
}

// Driver program
int main()
{
    int n = 350;
    printWordsWithoutIfSwitch(n);
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to print individual words without
//  if and without switch
class GFG
{

// To store digit to word mapping
static String word[] = {"zero", "one", "two", "three","four",
                "five", "six", "seven", "eight", "nine"};

static void printWordsWithoutIfSwitch(int n)
{
    // Store individual digits
    int digits[] = new int[10]; // a 32 bit int has at-most 10 digits

    int dc = 0; // Initialize digit count for given number 'n'

    // The below loop stores individual digits of n in
    // reverse order. do-while is used to handle "0" input
    do
    {
        digits[dc] = n % 10;
        n = n/10;
        dc++ ;
    } while (n != 0);

    // Traverse individual digits and print words using
    // word[][]
    for (int i = dc - 1; i >= 0; i--)
        System.out.print(word[digits[i]] + " ");
}

// Driver program
public static void main(String[] args)
{
    int n = 350;
    printWordsWithoutIfSwitch(n);
}
}

// This code has been contributed by 29AjayKumar
```

## C#

```cpp
// C# program to print individual words without
// if and without switch
using System;

class GFG
{

// To store digit to word mapping
static String []word = {"zero", "one", "two", "three","four",
                "five", "six", "seven", "eight", "nine"};

static void printWordsWithoutIfSwitch(int n)
{
    // Store individual digits
    int []digits = new int[10]; // a 32 bit int has at-most 10 digits

    int dc = 0; // Initialize digit count for given number 'n'

    // The below loop stores individual digits of n in
    // reverse order. do-while is used to handle "0" input
    do
    {
        digits[dc] = n % 10;
        n = n/10;
        dc++ ;
    } while (n != 0);

    // Traverse individual digits and print words using
    // word[][]
    for (int i = dc - 1; i >= 0; i--)
        Console.Write(word[digits[i]] + " ");
}

// Driver program
public static void Main(String[] args)
{
    int n = 350;
    printWordsWithoutIfSwitch(n);
}
}

// This code contributed by Rajput-Ji
```

## 蟒蛇 3

```cpp
# Python program to prindividual words without if and
# without switch

# To store digit to word mapping
word= ["zero", "one", "two", "three","four","five",
                "six", "seven", "eight", "nine"]

def printWordsWithoutIfSwitch(n):

    # Store individual digits
    digits = [0 for i in range(10)] # a 32 bit has at-most 10 digits

    dc = 0 # Initialize digit count for given number 'n'

    # The below loop stores individual digits of n in
    # reverse order. do-while is used to handle "0" input
    while True:
        digits[dc] = n%10
        n = n//10
        dc += 1
        if(n==0):
            break

    # Traverse individual digits and prwords using
    # word[][]
    for i in range(dc-1,-1,-1):
        print(word[digits[i]],end=" ")

# Driver program
n = 350
printWordsWithoutIfSwitch(n)

# This code is contributed by mohit kumar 29
```

## java 描述语言

```cpp
<script>
// Javascript program to print individual words without
//  if and without switch

    // To store digit to word mapping
    let word=["zero", "one", "two", "three","four",
                "five", "six", "seven", "eight", "nine"];

    function printWordsWithoutIfSwitch(n)
    {

        // Store individual digits
    let digits = new Array(10); // a 32 bit int has at-most 10 digits

    let dc = 0; // Initialize digit count for given number 'n'

    // The below loop stores individual digits of n in
    // reverse order. do-while is used to handle "0" input
    do
    {
        digits[dc] = n % 10;
        n = Math.floor(n/10);
        dc++ ;
    } while (n != 0);

    // Traverse individual digits and print words using
    // word[][]
    for (let i = dc - 1; i >= 0; i--)
        document.write(word[digits[i]] + " ");
    }

    // Driver program  
    let n = 350;
    printWordsWithoutIfSwitch(n);  

    // This code is contributed by unknown2108
</script>
```

**输出:**

```cpp
Three Five Zero
```

感谢乌卡什·特里维迪提出上述解决方案。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。