# 将时间从 12 小时转换为 24 小时格式的程序

> 原文:[https://www . geesforgeks . org/program-convert-time-12 小时-24 小时-format/](https://www.geeksforgeeks.org/program-convert-time-12-hour-24-hour-format/)

给定 12 小时上午/下午格式的时间，将其转换为军用(24 小时)时间。
注:12 小时制的午夜为上午 12:00:00，24 小时制的午夜为 00:00:00。中午是 12 小时制的中午 12:00:00，24 小时制的中午 12:00:00

**示例:**

```cpp
Input : A single string containing a time in 12-hour 
clock format(hh:mm:ss AM or hh:mm:ss PM
        where 01 <= hh <= 12 or 01 <= mm,ss <= 59 
Output :Convert and print the given time in 24-hour format,
where 00 <= hh <= 23

Input : 07:05:45PM
Output : 19:05:45
```

## C++

```cpp
// C++ program to convert 12 hour to 24 hour
// format
#include<iostream>
using namespace std;

void print24(string str)
{
    // Get hours
    int h1 = (int)str[1] - '0';
    int h2 = (int)str[0] - '0';
    int hh = (h2 * 10 + h1 % 10);

    // If time is in "AM"
    if (str[8] == 'A')
    {
        if (hh == 12)
        {
            cout << "00";
            for (int i=2; i <= 7; i++)
                cout << str[i];
        }
        else
        {
            for (int i=0; i <= 7; i++)
                cout << str[i];
        }
    }

    // If time is in "PM"
    else
    {
        if (hh == 12)
        {
            cout << "12";
            for (int i=2; i <= 7; i++)
                cout << str[i];
        }
        else
        {
            hh = hh + 12;
            cout << hh;
            for (int i=2; i <= 7; i++)
                cout << str[i];
        }
    }
}

// Driver code
int main()
{
   string str = "07:05:45PM";
   print24(str);
   return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to convert 12 hour
// format to  24 hour format
class GFG
{
static void print24(String str)
{
    // Get hours
    int h1 = (int)str.charAt(1) - '0';
    int h2 = (int)str.charAt(0) - '0';
    int hh = (h2 * 10 + h1 % 10);

    // If time is in "AM"
    if (str.charAt(8) == 'A')
    {
        if (hh == 12)
        {
            System.out.print("00");
            for (int i = 2; i <= 7; i++)
                System.out.print(str.charAt(i));
        }
        else
        {
            for (int i = 0; i <= 7; i++)
                System.out.print(str.charAt(i));
        }
    }

    // If time is in "PM"
    else
    {
        if (hh == 12)
        {
            System.out.print("12");
            for (int i = 2; i <= 7; i++)
                System.out.print(str.charAt(i));
        }
        else
        {
            hh = hh + 12;
            System.out.print(hh);
            for (int i = 2; i <= 7; i++)
                System.out.print(str.charAt(i));
        }
    }
}

// Driver code
public static void main (String[] args)
{
    String str = "07:05:45PM";
    print24(str);
}
}

// This code is contributed by Anant Agarwal.
```

## 蟒蛇 3

```cpp
# Python3 program to convert 12
# hour to 24 hour format
def print24(s):

    # Get hours
    h1 = ord(s[1]) - ord('0')
    h2 = ord(s[0]) - ord('0')
    hh = (h2 * 10 + h1 % 10)

    # If time is in "AM"
    if (s[8] == 'A'):
        if (hh == 12):
            print('00', end = '')

            for i in range(2, 8):
                print(s[i], end = '')

        else:
            for i in range(0, 8):
                print(s[i], end = '')

    # If time is in "PM"
    else:
        if (hh == 12):
            print("12", end = '')

            for i in range(2, 8):
                print(s[i], end = '')

        else:
            hh = hh + 12;
            print(hh, end = '')

            for i in range(2, 8):
                print(s[i], end = '')

# Driver code          
if __name__=="__main__":

   s = "07:05:45PM"

   print24(s)

# This code is contributed by rutvik_56
```

## C#

```cpp
// C# program to convert 12 hour
// format to 24 hour format
using System;

class GFG
{

static void print24(String str)
{
    // Get hours
    int h1 = (int)str[1] - '0';
    int h2 = (int)str[0] - '0';
    int hh = (h2 * 10 + h1 % 10);

    // If time is in "AM"
    if (str[8] == 'A')
    {
        if (hh == 12)
        {
            Console.Write("00");
            for (int i = 2; i <= 7; i++)
                Console.Write(str[i]);
        }
        else
        {
            for (int i = 0; i <= 7; i++)
                Console.Write(str[i]);
        }
    }

    // If time is in "PM"
    else
    {
        if (hh == 12)
        {
            Console.Write("12");
            for (int i = 2; i <= 7; i++)
                Console.Write(str[i]);
        }
        else
        {
            hh = hh + 12;
            Console.Write(hh);
            for (int i = 2; i <= 7; i++)
                Console.Write(str[i]);
        }
    }
}

// Driver code
public static void Main(String[] args)
{
    String str = "07:05:45PM";
    print24(str);
}
}

// This code is contributed by Rajput-Ji
```

## java 描述语言

```cpp
<script>
// javascript program to convert 12 hour
// format to 24 hour format

  function print24(str)
{
    // Get hours
    var h1 = Number(str[1] - '0');
    var h2 = Number(str[0] - '0');
    var hh = (h2 * 10 + h1 % 10);

    // If time is in "AM"
    if (str[8] == 'A')
    {
        if (hh == 12)
        {
            document.write("00");
            for (var i = 2; i <= 7; i++)
                document.write(str[i]);
        }
        else
        {
            for (var i = 0; i <= 7; i++)
                document.write(str[i]);
        }
    }

    // If time is in "PM"
    else
    {
        if (hh == 12)
        {
            document.write("12");
            for (var i = 2; i <= 7; i++)
                document.write(str[i]);
        }
        else
        {
            hh = hh + 12;
            document.write(hh);
            for (var i = 2; i <= 7; i++)
                document.write(str[i]);
        }
    }
}

// Driver code

    var str = "07:05:45PM";
    print24(str);

// This code is contributed by bunnyram19.
</script>
```

**输出:**

```cpp
19:05:45
```

**方法二:使用 java 日期**

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program for the above approach
import java.text.DateFormat;
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;

class GFG {
    public static String englishTime(String input)
        throws ParseException
    {

        // Format of the date defined in the input String
        DateFormat dateFormat
            = new SimpleDateFormat("hh:mm:ss aa");

        // Change the pattern into 24 hour format
        DateFormat format
            = new SimpleDateFormat("HH:mm:ss");
        Date time = null;
        String output = "";

        // Converting the input String to Date
        time = dateFormat.parse(input);

        // Changing the format of date
        // and storing it in
        // String
        output = format.format(time);
        return output;
    }

    // Driver Code
    public static void main(String[] arg)
        throws ParseException
    {
        System.out.println(englishTime("07:05:45 PM"));
    }
}
```

**输出:**

```cpp
19:05:45
```

本文由**拉胡尔·辛格(Nit kkr)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。