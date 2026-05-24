# c#–随机生成字符串

> 原文:[https://www . geesforgeks . org/c-sharp-随机生成字符串/](https://www.geeksforgeeks.org/c-sharp-randomly-generating-strings/)

在 C# 中，[字符串](https://www.geeksforgeeks.org/c-sharp-string/)是 Unicode 字符序列或字符数组。Unicode 字符的范围是从 U+0000 到 U+FFFF。字符串是文本的表示形式。在本文中，我们将学习如何随机生成字符串和字母数字字符串。因此，为了完成这项任务，我们使用了 Random 类，尽管它生成整数，但我们可以使用它们来创建随机字符串。Random 类提供了不同类型的方法来生成随机字符串。随机字符串通常用于验证码验证等。

**示例:**

```cs
Random String: ZDTXZFPYQEOUPGMEIYCEUSK

Random String: PSSR34YB
```

### 方法 1:使用 Next()方法

我们可以使用 [Next()](https://www.geeksforgeeks.org/c-sharp-random-next-method/) 方法生成一个随机字符串。此方法接受两个参数最小和最大范围，并在指定的最小和最大范围内返回一个正的随机整数。

**语法:**

> 公共虚拟 int Next(int mvvalue，int nvvalue)；

这里，mValue 是生成的随机数的上界，nValue 是返回的随机数的下界。

**进场:**

> 1.创建随机类的对象
> 
> 2.使用 Next()方法随机选择字符串的大小，并存储在 stringlength 变量中。
> 
> 3.使用 for 循环重复以下字符串长度的步骤:
> 
> *   随机选择一个介于 0 和 25 之间的数字
> *   随机数加 65，用[转换成 char。](https://www.geeksforgeeks.org/c-sharp-convert-tocharstring-iformatprovider-method/)方法
> 
> 4.显示输出。

**示例:**

## C#

```cs
// C# program to generate random strings
using System;

class GFG{

static void Main()
{

    // Creating object of random class
    Random rand = new Random();

    // Choosing the size of string
    // Using Next() string
    int stringlen = rand.Next(4, 10);
    int randValue;
    string str = "";
    char letter;
    for (int i = 0; i < stringlen; i++)
    {

        // Generating a random number.
        randValue = rand.Next(0, 26);

        // Generating random character by converting
        // the random number into character.
        letter = Convert.ToChar(randValue + 65);

        // Appending the letter to string.
        str = str + letter;
    }
    Console.Write("Random String:" + str);
}
}
```

**输出:**

```cs
Random String:UUYXBGA
```

**说明:**在上面的例子中，我们将生成一个 0 到 25 之间的随机数，并将其加到 65，然后它将成为字母表的 ASCII 值。ASCII 值使用 ToChar()方法转换为字符。整个步骤将使用 for 循环重复多次，并通过附加所有随机生成的字符形成一个字符串。

### 方法 2:

我们也可以使用这个方法生成随机字符串。在这个方法中，我们传递一个包含 26 个字母的字符串。然后从 26 个字母中，我们将随机选择一个字母，并将其附加到字符串中，通过重复这个过程，形成一个随机字符串。

**进场:**

> 1.  Initialize the string with letters, namely str = **"ABC ……". xyz"**
> 2.  Initialize an empty string and name it "ran".
> 3.  Select the size of the string to be generated.
> 4.  Now use the [next ()](https://www.geeksforgeeks.org/c-sharp-random-next-method/) method to generate a random number, and select the character at the index in the alphabet string.
> 5.  Append the character to the random string.
> 6.  Repeat steps 4 and 5n, where n is the length of the string.

**示例:**

## C#

```cs
// C# program to generate random strings
using System;

class GFG{

public static void Main(string[] args)
{
    Random res = new Random();

    // String of alphabets 
    String str = "abcdefghijklmnopqrstuvwxyz";
    int size = 10;

    // Initializing the empty string
    String ran = "";

    for (int i = 0; i < size; i++)
    {

        // Selecting a index randomly
        int x = res.Next(26);

        // Appending the character at the 
        // index to the random string.
        ran = ran + str[x];
    }

    Console.WriteLine("Random String:" + ran);
}
}
```

**输出:**

```cs
Random String:mphhzgvpjr
```

**解释:**在这个例子中，我们创建了一个 Random 类的对象。然后我们将 26 个字母存储在一个名为“str”的字符串中。现在我们创建一个名为“size”的整数类型的变量，它表示随机生成的字符串中存在的字符总数。现在我们创建一个名为“ran”的空字符串。然后，我们创建一个 for 循环，迭代到“i <大小”，在这个 for 循环中，我们使用 Next()方法。这个方法会生成小于 26 的随机数，所以我们使用这些数字作为位置指示器来获取该位置的字符。所以每次循环迭代时，我们都会得到一个随机字符。最后，我们将追加这些字符，得到一个随机字符串。

### 方法 3:生成字母数字字符串

字母数字字符串是那些既包含字母又包含数字的字符串。我们可以使用上述方法生成随机的字母数字字符串。

**进场:**

> 1.  Initialize a string with letters and numbers, namely str = **"ABC ... XYZ 012 ... 789"**
> 2.  Initialize an empty string and name it "Random String".
> 3.  Select the size of the string to be generated.
> 4.  Now use the [next ()](https://www.geeksforgeeks.org/c-sharp-random-next-method/) method to generate a random number, and select the character at the index in the alphanumeric string.
> 5.  Append the character to the random string.
> 6.  Repeat steps 4 and 5n, where n is the length of the string.

**示例:**

## C#

```cs
// C# program to generate random alphanumeric strings
using System;

class GFG{

public static void Main(string[] args)
{
    Random res = new Random();

    // String that contain both alphabets and numbers
    String str = "abcdefghijklmnopqrstuvwxyz0123456789";
    int size = 8;

    // Initializing the empty string
    String randomstring = "";

    for (int i = 0; i < size; i++)
    {

        // Selecting a index randomly
        int x = res.Next(str.Length);

        // Appending the character at the 
        // index to the random alphanumeric string.
        randomstring = randomstring + str[x];
    }

    Console.WriteLine("Random alphanumeric String:" + randomstring);
}
}
```

**输出:**

```cs
Random alphanumeric String:v91d2p48
```

**解释:**在这个例子中，我们创建了一个 Random 类的对象。然后我们将字母和数字存储在一个名为“str”的字符串中。现在我们创建一个名为“size”的整型变量，它代表随机生成的字母数字字符串中的字符总数。现在我们创建一个名为“randomstring”的空字符串。然后，我们创建一个 for 循环，迭代到“i <大小”，在这个 for 循环中，我们使用 Next()方法。此方法生成小于字符串的随机数。长度，所以我们使用这些数字作为位置指示器，从那个位置获取字符。所以每次循环迭代时，我们都会得到一个随机字符。最后，我们将附加这些字符，得到一个随机的字母数字字符串。