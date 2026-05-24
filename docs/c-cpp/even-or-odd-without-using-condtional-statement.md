# 不使用条件语句打印“偶数”或“奇数”

> 原文:[https://www . geesforgeks . org/偶数或奇数不使用条件语句/](https://www.geeksforgeeks.org/even-or-odd-without-using-condtional-statement/)

编写一个程序，接受用户输入的数字，如果输入的数字是偶数，则打印“偶数”，如果输入的数字是奇数，则打印“奇数”。不允许使用任何比较(==，，…等)或条件语句(if，else，switch，三元运算符，。等等)。

**方法 1**
下面是一个棘手的代码，可以用来相应打印“偶数”或“奇数”。

## C++

```cpp
#include <iostream>

using namespace std;

int main()
{
    char arr[2][5] = { "Even", "Odd" };
    int no;
    cout << "Enter a number: ";
    cin >> no;
    cout << arr[no % 2];
    getchar();
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
import java.util.Scanner;
class GFG
{
    public static void main(String[] args)
    {

        String[] arr = {"Even", "Odd"};

        Scanner s = new Scanner(System.in);

        System.out.print("Enter the number: ");
        int no = s.nextInt();

        System.out.println(arr[no%2]);
    }
}

// This code is contributed by divyeshrabadiya07.
```

## 蟒蛇 3

```cpp
arr = ["Even", "Odd"]
print ("Enter the number")
no = int(input())
print (arr[no % 2])
```

## C#

```cpp
using System;
class GFG {
  static void Main() {
    string[] arr = {"Even", "Odd"};

    Console.Write("Enter the number: ");

    string val;
    val = Console.ReadLine();
    int no = Convert.ToInt32(val);

    Console.WriteLine(arr[no%2]);
  }
}

// This code is contributed by divyesh072019.
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```cpp
<?php
$arr = ["Even", "Odd"];
$input = 5;
echo ($arr[$input % 2]);

// This code is contributed
// by Aman ojha
?>
```

## java 描述语言

```cpp
<script>

    let arr = ["Even", "Odd"];
    let no = prompt("Enter a number: ");

    document.write(arr[no % 2]);

   // This code is contributed by suresh07

</script>
```

**方法 2**
下面是另一个棘手的代码，可以用来相应地打印“偶数”或“奇数”。感谢[学生](https://www.geeksforgeeks.org/archives/8337/comment-page-1#comment-4987)提出这个方法。

## C++

```cpp
#include<stdio.h>
int main()
{
    int no;
    printf("Enter a no: ");
    scanf("%d", &no);
    (no & 1 && printf("odd"))|| printf("even");
    return 0;
}
```

**Output**

```cpp
Enter a no: even
```