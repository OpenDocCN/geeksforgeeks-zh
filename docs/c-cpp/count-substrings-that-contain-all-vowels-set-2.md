# 统计包含所有元音的子串| SET 2

> 原文:[https://www . geesforgeks . org/count-substrings-包含所有元音的-set-2/](https://www.geeksforgeeks.org/count-substrings-that-contain-all-vowels-set-2/)

给定一个包含小写字母的字符串 **str** ，任务是统计包含所有元音的子字符串至少一次，并且子字符串中没有辅音(非元音字符)。
**例:**

> **输入:**str = " aeoisddaaeioudb "
> **输出:**4
> 【aaeiouu】【aeiou】【aeiou】和【aaeiou】
> **输入:**str = " aeoisddaaeouedf "
> **输出:** 1
> **输入:**str = " aeoisddaaeouua "
> **输出:**

**方法:**思路是提取所有只包含元音的最大长度子串。现在对于所有这些单独的子串，我们需要找到包含所有元音至少一次的子串的计数。这可以使用[双指针技术](https://www.geeksforgeeks.org/two-pointers-technique/)来完成。
说明在这种情况下如何使用双指针技术:

> if string = " aeoibsdaaeioudb "
> 第一步是提取所有最大长度的子串，这些子串只包含以下元音:
> 
> 1.  你好
> 2.  aaeiouu
> 
> 现在，以第一个字符串“aeoi”为例，它不会被计算在内，因为元音“u”丢失了。
> 然后，取第二个子串，即字符串的“aaeiouu”
> Length，n = 7
> start = 0
> index = 0
> count = 0
> 我们将运行一个循环，直到所有的元音至少出现一次，所以我们在 index 5 处停止，start = 0。
> 现在我们的字符串是“aaeiou”，有 n–I 个子字符串，至少包含一次元音，并且以字符串“aaeiou”作为前缀。
> 这些子串是:“aaeiou”、“aaeiou”
> count = count+(n–I)= 7–5 = 2
> 现在，count = 2
> 然后，增量从 1 开始。如果[start，index]之间的子串，即(1，5)仍然至少包含一次元音，则添加(n–I)。
> 这些子串是:“aeiou”、“aeiou”
> count = count+(n–I)= 7–5 = 2
> 现在，count = 2
> 然后 start = 2，现在子串变成“eiouu”。那么就不能再增加计数了，因为缺少元音‘a’。

以下是上述方法的实现:

## C++

```cpp
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

// Function that returns true if c is a vowel
bool isVowel(char c)
{
    return (c == 'a' || c == 'e' || c == 'i'
            || c == 'o' || c == 'u');
}

// Function to return the count of sub-strings
// that contain every vowel at least
// once and no consonant
int countSubstringsUtil(string s)
{
    int count = 0;

    // Map is used to store count of each vowel
    map<char, int> mp;

    int n = s.length();

    // Start index is set to 0 initially
    int start = 0;

    for (int i = 0; i < n; i++) {
        mp[s[i]]++ ;

        // If substring till now have all vowels
        // atleast once increment start index until
        // there are all vowels present between
        // (start, i) and add n - i each time
        while (mp['a'] > 0 && mp['e'] > 0
               && mp['i'] > 0 && mp['o'] > 0
               && mp['u'] > 0) {
            count += n - i;
            mp[s[start]]--;
            start++ ;
        }
    }

    return count;
}

// Function to extract all maximum length
// sub-strings in s that contain only vowels
// and then calls the countSubstringsUtil() to find
// the count of valid sub-strings in that string
int countSubstrings(string s)
{
    int count = 0;
    string temp = "";

    for (int i = 0; i < s.length(); i++) {

        // If current character is a vowel then
        // append it to the temp string
        if (isVowel(s[i])) {
            temp += s[i];
        }

        // The sub-string containing all vowels ends here
        else {

            // If there was a valid sub-string
            if (temp.length() > 0)
                count += countSubstringsUtil(temp);

            // Reset temp string
            temp = "";
        }
    }

    // For the last valid sub-string
    if (temp.length() > 0)
        count += countSubstringsUtil(temp);

    return count;
}

// Driver code
int main()
{
    string s = "aeouisddaaeeiouua";

    cout << countSubstrings(s) << endl;

    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java implementation of the approach
import java.util.*;

class GFG
{

// Function that returns true if c is a vowel
static boolean isVowel(char c)
{
    return (c == 'a' || c == 'e' ||
            c == 'i' || c == 'o' || c == 'u');
}

// Function to return the count of sub-strings
// that contain every vowel at least
// once and no consonant
static int countSubstringsUtil(char []s)
{
    int count = 0;

    // Map is used to store count of each vowel
    Map<Character, Integer> mp = new HashMap<>();

    int n = s.length;

    // Start index is set to 0 initially
    int start = 0;

    for (int i = 0; i < n; i++)
    {
        if(mp.containsKey(s[i]))
        {
            mp.put(s[i], mp.get(s[i]) + 1);
        }
        else
        {
            mp.put(s[i], 1);
        }

        // If substring till now have all vowels
        // atleast once increment start index until
        // there are all vowels present between
        // (start, i) and add n - i each time
        while (mp.containsKey('a') && mp.containsKey('e') &&
               mp.containsKey('i') && mp.containsKey('o') &&
               mp.containsKey('u') && mp.get('a') > 0 &&
               mp.get('e') > 0 && mp.get('i') > 0 &&
               mp.get('o') > 0 && mp.get('u') > 0)
        {
            count += n - i;
            mp.put(s[start], mp.get(s[start]) - 1);

            start++ ;
        }
    }
    return count;
}

// Function to extract all maximum length
// sub-strings in s that contain only vowels
// and then calls the countSubstringsUtil() to find
// the count of valid sub-strings in that string
static int countSubstrings(String s)
{
    int count = 0;
    String temp = "";

    for (int i = 0; i < s.length(); i++)
    {

        // If current character is a vowel then
        // append it to the temp string
        if (isVowel(s.charAt(i)))
        {
            temp += s.charAt(i);
        }

        // The sub-string containing all vowels ends here
        else
        {

            // If there was a valid sub-string
            if (temp.length() > 0)
                count += countSubstringsUtil(temp.toCharArray());

            // Reset temp string
            temp = "";
        }
    }

    // For the last valid sub-string
    if (temp.length() > 0)
        count += countSubstringsUtil(temp.toCharArray());

    return count;
}

// Driver code
public static void main(String[] args)
{
    String s = "aeouisddaaeeiouua";

    System.out.println(countSubstrings(s));
}
}

// This code is contributed by Princi Singh
```

## 蟒蛇 3

```cpp
# Python3 implementation of the approach

# Function that returns true if c is a vowel
def isVowel(c) :

    return (c == 'a' or c == 'e' or c == 'i'
            or c == 'o' or c == 'u');

# Function to return the count of sub-strings
# that contain every vowel at least
# once and no consonant
def countSubstringsUtil(s) :

    count = 0;

    # Map is used to store count of each vowel
    mp = dict.fromkeys(s,0);

    n = len(s);

    # Start index is set to 0 initially
    start = 0;

    for i in range(n) :
        mp[s[i]] += 1;

        # If substring till now have all vowels
        # atleast once increment start index until
        # there are all vowels present between
        # (start, i) and add n - i each time
        while (mp['a'] > 0 and mp['e'] > 0
            and mp['i'] > 0 and mp['o'] > 0
            and mp['u'] > 0) :
            count += n - i;
            mp[s[start]] -= 1;
            start += 1;

    return count;

# Function to extract all maximum length
# sub-strings in s that contain only vowels
# and then calls the countSubstringsUtil() to find
# the count of valid sub-strings in that string
def countSubstrings(s) :

    count = 0;
    temp = "";

    for i in range(len(s)) :

        # If current character is a vowel then
        # append it to the temp string
        if (isVowel(s[i])) :
            temp += s[i];

        # The sub-string containing all vowels ends here
        else :

            # If there was a valid sub-string
            if (len(temp) > 0) :
                count += countSubstringsUtil(temp);

            # Reset temp string
            temp = "";

    # For the last valid sub-string
    if (len(temp) > 0) :
        count += countSubstringsUtil(temp);

    return count;

# Driver code
if __name__ == "__main__" :

    s = "aeouisddaaeeiouua";

    print(countSubstrings(s));

# This code is contributed by AnkitRai01
```

## C#

```cpp
// C# implementation of the approach
using System;
using System.Collections.Generic;

class GFG
{

// Function that returns true if c is a vowel
static bool isVowel(char c)
{
    return (c == 'a' || c == 'e' ||
            c == 'i' || c == 'o' || c == 'u');
}

// Function to return the count of sub-strings
// that contain every vowel at least
// once and no consonant
static int countSubstringsUtil(char []s)
{
    int count = 0;

    // Map is used to store count of each vowel
    Dictionary<char,
               int> mp = new Dictionary<char,
                                        int>();

    int n = s.Length;

    // Start index is set to 0 initially
    int start = 0;

    for (int i = 0; i < n; i++)
    {
        if(mp.ContainsKey(s[i]))
        {
            mp[s[i]] = mp[s[i]] + 1;
        }
        else
        {
            mp.Add(s[i], 1);
        }

        // If substring till now have all vowels
        // atleast once increment start index until
        // there are all vowels present between
        // (start, i) and add n - i each time
        while (mp.ContainsKey('a') && mp.ContainsKey('e') &&
               mp.ContainsKey('i') && mp.ContainsKey('o') &&
               mp.ContainsKey('u') && mp['a'] > 0 &&
               mp['e'] > 0 && mp['i'] > 0 &&
               mp['o'] > 0 && mp['u'] > 0)
        {
            count += n - i;
            if(mp.ContainsKey(s[start]))
                mp[s[start]] = mp[s[start]] - 1;

            start++ ;
        }
    }
    return count;
}

// Function to extract all maximum length
// sub-strings in s that contain only vowels
// and then calls the countSubstringsUtil() to find
// the count of valid sub-strings in that string
static int countSubstrings(String s)
{
    int count = 0;
    String temp = "";

    for (int i = 0; i < s.Length; i++)
    {

        // If current character is a vowel then
        // append it to the temp string
        if (isVowel(s[i]))
        {
            temp += s[i];
        }

        // The sub-string containing
        // all vowels ends here
        else
        {

            // If there was a valid sub-string
            if (temp.Length > 0)
                count += countSubstringsUtil(temp.ToCharArray());

            // Reset temp string
            temp = "";
        }
    }

    // For the last valid sub-string
    if (temp.Length > 0)
        count += countSubstringsUtil(temp.ToCharArray());

    return count;
}

// Driver code
public static void Main(String[] args)
{
    String s = "aeouisddaaeeiouua";

    Console.WriteLine(countSubstrings(s));
}
}

// This code is contributed by Princi Singh
```

## java 描述语言

```cpp
<script>
// JavaScript implementation of the approach

// Function that returns true if c is a vowel
function isVowel( c)
{
    return (c == 'a' || c == 'e' || c == 'i'
            || c == 'o' || c == 'u');
}

// Function to return the count of sub-strings
// that contain every vowel at least
// once and no consonant
function countSubstringsUtil( s)
{
    var count = 0;

    // Map is used to store count of each vowel
    var mp = {};

    var n = s.length;

    // Start index is set to 0 initially
    var start = 0;

    for (let i = 0; i < n; i++) {
        if(mp[s[i]]){
           mp[s[i]]++ ;
        }
        else
            mp[s[i]] = 1;

        // If substring till now have all vowels
        // atleast once increment start index until
        // there are all vowels present between
        // (start, i) and add n - i each time

        while (mp['a'] > 0 && mp['e'] > 0
               && mp['i'] > 0 && mp['o'] > 0
               && mp['u'] > 0) {
            count += n - i;
            mp[s[start]]--;
            start++ ;
        }
    }

    return count;
}

// Function to extract all maximum length
// sub-strings in s that contain only vowels
// and then calls the countSubstringsUtil() to find
// the count of valid sub-strings in that string
function countSubstrings( s)
{
    var count = 0;
    var temp = "";

    for (let i = 0; i < s.length; i++) {

        // If current character is a vowel then
        // append it to the temp string
        if (isVowel(s[i])) {
            temp += s[i];
        }

        // The sub-string containing all vowels ends here
        else {

            // If there was a valid sub-string
            if (temp.length > 0)
                count += countSubstringsUtil(temp);

            // Reset temp string
            temp = "";
        }
    }

    // For the last valid sub-string
    if (temp.length > 0)
        count += countSubstringsUtil(temp);

    return count;
}

// Driver code

var s = "aeouisddaaeeiouua";
console.log( countSubstrings(s));

// This code is contributed by ukasp.   

</script>
```

**Output:** 

```cpp
9
```

**时间复杂度:** O(N)