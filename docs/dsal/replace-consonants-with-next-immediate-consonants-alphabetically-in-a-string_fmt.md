# 用字符串中的下一个直接辅音字母替换辅音

> 原文: [https://www.geeksforgeeks.org/replace-consonants-with-next-immediate-consonants-alphabetically-in-a-string/](https://www.geeksforgeeks.org/replace-consonants-with-next-immediate-consonants-alphabetically-in-a-string/)

给定一个包含小写英文字母的字符串。任务是用英文字母中的下一个辅音替换每个辅音。
假设我们要替换字符 `a`，它将被 `b` 替换。再举个例子，假设我们要替换字符 `d`，下一个直接辅音是 `f`，因此 `d` 将被 `f` 替换。
**注**: 如果字符是 `z`，那么在英文字母中循环查找下一个辅音，即替换为 `b`。

**示例**:

```
Input : str = "geeksforgeeks"
Output : heeltgosheelt

Input : str = "gfg"
Output : hgh
```

## 进场

*   从左到右迭代字符串元素。
*   如果字符串元素是辅音，那么检查这个元素的下一个字母。
*   如果下一个字母是辅音字母，则用这个字母替换它。如果是元音，则用第二个直接字母替换字符串元素，因为英语字母中没有连续的元音。

以下是上述程序的实现:

## C++

```cpp
// C++ program of above approach
#include <bits/stdc++.h>
using namespace std;

// Function to check if a character is
// vowel or not
bool isVowel(char ch)
{
    if (ch != 'a' && ch != 'e' && ch != 'i'
                     && ch != 'o' && ch != 'u')
        return false;

    return true;
}

// Function that replaces consonant with
// next immediate consonant alphabetically
string replaceConsonants(string s)
{
    // Start traversing the string
    for (int i = 0; i < s.length(); i++) {

        if (!isVowel(s[i])) {

            // if character is z,
            // than replace it with character b
            if (s[i] == 'z')
                s[i] = 'b';

            // if the alphabet is not z
            else {

                // replace the element with
                // next immediate alphabet
                s[i] = (char)(s[i] + 1);

                // if next immediate alphabet is vowel,
                // than take next 2nd immediate alphabet
                // (since no two vowels occurs consecutively
                // in alphabets) hence no further
                // checking is required
                if (isVowel(s[i]))
                    s[i] = (char)(s[i] + 1);
            }
        }
    }

    return s;
}

// Driver code
int main()
{
    string s = "geeksforgeeks";

    cout << replaceConsonants(s);

    return 0;
}
```

## Java

```java
// Java program of above approach
class GFG
{

    // Function to check if a character is
    // vowel or not
    static boolean isVowel(char ch)
    {
        if (ch != 'a' && ch != 'e' && ch != 'i'
                && ch != 'o' && ch != 'u')
        {
            return false;
        }
        return true;
    }

    // Function that replaces consonant with
    // next immediate consonant alphabetically
    static String replaceConsonants(char[] s)
    {
        // Start traversing the string
        for (int i = 0; i < s.length; i++)
        {
            if (!isVowel(s[i]))
            {

                // if character is z,
                // than replace it with character b
                if (s[i] == 'z')
                {
                    s[i] = 'b';
                }

                // if the alphabet is not z
                else
                {

                    // replace the element with
                    // next immediate alphabet
                    s[i] = (char) (s[i] + 1);

                    // if next immediate alphabet is vowel,
                    // than take next 2nd immediate alphabet
                    // (since no two vowels occurs consecutively
                    // in alphabets) hence no further
                    // checking is required
                    if (isVowel(s[i]))
                    {
                        s[i] = (char) (s[i] + 1);
                    }
                }
            }
        }
        return String.valueOf(s);
    }

    // Driver code
    public static void main(String[] args)
    {
        String s = "geeksforgeeks";
        System.out.println(replaceConsonants(s.toCharArray()));
    }
}

// This code is contributed by Rajput-Ji
```

## Python 3

```python
# Python3 program of above approach

# Function to check if a character is
# vowel or not
def isVowel(ch):

    if (ch != 'a' and ch != 'e' and
        ch != 'i' and ch != 'o' and
        ch != 'u'):
        return False;

    return True;

# Function that replaces consonant with
# next immediate consonant alphabetically
def replaceConsonants(s):

    # Start traversing the string
    for i in range(len(s)):
        if (isVowel(s[i])==False):

            # if character is z,
            # than replace it with character b
            if (s[i] == 'z'):
                s[i] = 'b';

            # if the alphabet is not z
            else:

                # replace the element with
                # next immediate alphabet
                s[i] = chr(ord(s[i]) + 1);

                # if next immediate alphabet is vowel,
                # than take next 2nd immediate alphabet
                # (since no two vowels occurs consecutively
                # in alphabets) hence no further
                # checking is required
                if (isVowel(s[i])==True):
                    s[i] = chr(ord(s[i]) + 1);

    return ''.join(s);

# Driver code
s = "geeksforgeeks";

print(replaceConsonants(list(s)));

# This code is contributed by mits
```

## C#

```csharp
// C# program of above approach
using System;

class GFG
{

    // Function to check if a character is
    // vowel or not
    static bool isVowel(char ch)
    {
        if (ch != 'a' && ch != 'e' && ch != 'i'
                && ch != 'o' && ch != 'u')
        {
            return false;
        }
        return true;
    }

    // Function that replaces consonant with
    // next immediate consonant alphabetically
    static String replaceConsonants(char[] s)
    {

        // Start traversing the string
        for (int i = 0; i < s.Length; i++)
        {
            if (!isVowel(s[i]))
            {

                // if character is z,
                // than replace it with character b
                if (s[i] == 'z')
                {
                    s[i] = 'b';
                }

                // if the alphabet is not z
                else
                {

                    // replace the element with
                    // next immediate alphabet
                    s[i] = (char) (s[i] + 1);

                    // if next immediate alphabet is vowel,
                    // than take next 2nd immediate alphabet
                    // (since no two vowels occurs consecutively
                    // in alphabets) hence no further
                    // checking is required
                    if (isVowel(s[i]))
                    {
                        s[i] = (char) (s[i] + 1);
                    }
                }
            }
        }
        return String.Join("",s);
    }

    // Driver code
    public static void Main(String[] args)
    {
        String s = "geeksforgeeks";
        Console.WriteLine(replaceConsonants
                            (s.ToCharArray()));
    }
}

// This code is contributed by
// 29AjayKumar
```

# 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

## PHP 实现

```php
<?php
// PHP program of above approach

// Function to check if a character is
// vowel or not
function isVowel($ch)
{
    if ($ch != 'a' && $ch != 'e' &&
        $ch != 'i' && $ch != 'o' &&
        $ch != 'u')
        return false;

    return true;
}

// Function that replaces consonant with
// next immediate consonant alphabetically
function replaceConsonants($s)
{
    // Start traversing the string
    for ($i = 0; $i < strlen($s); $i++)
    {
        if (!isVowel($s[$i]))
        {

            // if character is z,
            // than replace it with character b
            if ($s[$i] == 'z')
                $s[$i] = 'b';

            // if the alphabet is not z
            else
            {

                // replace the element with
                // next immediate alphabet
                $s[$i] = chr(ord($s[$i]) + 1);

                // if next immediate alphabet is vowel,
                // than take next 2nd immediate alphabet
                // (since no two vowels occurs consecutively
                // in alphabets) hence no further
                // checking is required
                if (isVowel($s[$i]))
                    $s[$i] = chr(ord($s[$i]) + 1);
            }
        }
    }
    return $s;
}

// Driver code
$s = "geeksforgeeks";

echo replaceConsonants($s);

// This code is contributed by mits
?>
```

## JavaScript 实现

```javascript
<script>

// Javascript program of above approach

// Function to check if a character is
// vowel or not
function isVowel(ch)
{
    if (ch != 'a' && ch != 'e' && ch != 'i'
                     && ch != 'o' && ch != 'u')
        return false;

    return true;
}

// Function that replaces consonant with
// next immediate consonant alphabetically
function replaceConsonants(s)
{
    // Start traversing the string
    for (var i = 0; i < s.length; i++) {

        if (!isVowel(s[i])) {

            // if character is z,
            // than replace it with character b
            if (s[i] == 'z')
                s[i] = 'b';

            // if the alphabet is not z
            else {

                // replace the element with
                // next immediate alphabet
                s[i] = String.fromCharCode(s[i].charCodeAt(0) + 1);

                // if next immediate alphabet is vowel,
                // than take next 2nd immediate alphabet
                // (since no two vowels occurs consecutively
                // in alphabets) hence no further
                // checking is required
                if (isVowel(s[i]))
                    s[i] = String.fromCharCode(s[i].charCodeAt(0) + 1);
            }
        }
    }

    return s.join('');
}

// Driver code
var s = "geeksforgeeks".split('');
document.write( replaceConsonants(s));

</script>
```

**输出：**

```
heeltgosheelt
```