# 使用自定义哈希函数对数组中的字符串进行分类

> 原文：[https://www.geeksforgeeks.org/classify-strings-from-an-array-using-custom-hash-function/](https://www.geeksforgeeks.org/classify-strings-from-an-array-using-custom-hash-function/)

给定由 **N** 个字符串组成的字符串数组 `arr[]`，任务是根据字符串中字符的 ASCII 值之和对 26 取模得到的哈希值对字符串进行分类。

**示例：**

> **输入：** `arr[] = {"geeks", "for", "geeks"}`
> **输出：**
> geeks geeks
> for
> **解释：**
> 字符串 "for" 的哈希值为 `(102 + 111 + 114) % 26 = 14`
>
> **输入：** `arr[] = {"ADF", "aahe", "bce", "bgdb"}`
> **输出：**
> aahe bgdb
> bce
> adf
> **解释：**
> 字符串 "ADF" 的哈希值为 `(65+68+70) % 26 = 13`
> 字符串 "aahe" 的哈希值为 `(97+97+104+101) % 26 = 9`
> 字符串 "bgdb" 的哈希值为 `(98+103+100+98) % 26 = 9`
> 因此，字符串 "aahe" 和 "bgdb" 具有相同的散列值，因此它们被分组在一起。

**方法：** 想法是使用 `map` 数据结构将具有相同哈希值的字符串组合在一起。按照以下步骤解决问题：

*   初始化一个 `map`，比如说 `mp`，将哈希值映射到一个 `vector` 中的相应字符串。
*   遍历给定的字符串数组，并执行以下步骤：
    *   根据给定的函数计算当前字符串的哈希值。
    *   将字符串推入向量中，将字符串的计算哈希值作为映射 `mp` 中的关键。
*   最后，遍历地图 `mp` 并打印各个键的所有字符串。

下面是上述方法的实现：

## C++

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to find the hash
// value of the string s
int stringPower(string s)
{
    // Stores hash value of string
    int power = 0;
    int n = s.length();

    // Iterate over characters of the string
    for (int i = 0; i < n; i++) {

        // Calculate hash value
        power = (power + (s[i])) % 26;
    }

    // Return the hash value
    return power;
}

// Function to classify the strings
// according to the given condition
void categorisation_Of_strings(
    vector<string> s, int N)
{
    // Maps strings with their strings
    // respective hash values
    map<int, vector<string> > mp;

    // Traverse the array of strings
    for (int i = 0; i < N; i++) {

        // Find the hash value of the
        // of the current string
        int temp = stringPower(s[i]);

        // Push the current string in
        // value vector of temp key
        mp[temp].push_back(s[i]);
    }

    // Traverse over the map mp
    for (auto power : mp) {

        // Print the result
        for (auto str : power.second) {
            cout << str << " ";
        }
        cout << endl;
    }
}

// Driver Code
int main()
{
    vector<string> arr{ "adf", "aahe",
                        "bce", "bgdb" };
    int N = arr.size();

    categorisation_Of_strings(arr, N);

    return 0;
}
```

## Java

```java
// Java program for the above approach
import java.util.Arrays;
import java.util.HashMap;
import java.util.Map;
import java.util.Vector;

class GFG{

// Function to find the hash
// value of the string s
static int stringPower(String s)
{

    // Stores hash value of string
    int power = 0;
    int n = s.length();
    char C[] = s.toCharArray();

    // Iterate over characters of the string
    for(int i = 0; i < n; i++)
    {

        // Calculate hash value
        power = (power + (C[i])) % 26;
    }

    // Return the hash value
    return power;
}

// Function to classify the strings
// according to the given condition
static void categorisation_Of_strings(Vector<String> s,
                                      int N)
{

    // Maps strings with their strings
    // respective hash values
    Map<Integer, Vector<String> > mp = new HashMap<>();

    // Traverse the array of strings
    for(int i = 0; i < N; i++)
    {

        // Find the hash value of the
        // of the current string
        int temp = stringPower(s.get(i));

        // Push the current string in
        // value vector of temp key
        if (mp.containsKey(temp))
        {
            mp.get(temp).add(s.get(i));
        }
        else
        {
            mp.put(temp, new Vector<String>());
            mp.get(temp).add(s.get(i));
        }
    }

    // Traverse over the map mp
    for(Map.Entry<Integer,
           Vector<String>> entry : mp.entrySet())
    {

        // Print the result
        for(String str : entry.getValue())
        {
            System.out.print(str + " ");
        }
        System.out.println();
    }
}

// Driver code
public static void main(String[] args)
{
    String[] Sarr = { "adf", "aahe", "bce", "bgdb" };
    Vector<String> arr = new Vector<String>(
        Arrays.asList(Sarr));
    int N = arr.size();

    categorisation_Of_strings(arr, N);
}
}

// This code is contributed by abhinavjain194
```

## Python 3

```python
# Python3 program for the above approach

# Function to find the hash
# value of the string s
def stringPower(s):

    # Stores hash value of string
    power = 0
    n = len(s)

    # Iterate over characters of the string
    for i in range(n):

        # Calculate hash value
        power = (power + ord(s[i])) % 26

    # Return the hash value
    return power

# Function to classify the strings
# according to the given condition
def categorisation_Of_strings(s, N):

    # Maps strings with their strings
    # respective hash values
    mp = {}

    # Traverse the array of strings
    for i in range(N):

        # Find the hash value of the
        # of the current string
        temp = stringPower(s[i])

        # Push the current string in
        # value vector of temp key
        if temp in mp:
            mp[temp].append(s[i])
        else:
            mp[temp] = []
            mp[temp].append(s[i])

    # Traverse over the map mp
    for i in sorted (mp) :

        # Print the result
        for str in mp[i]:
            print(str,end = " ")
        print("\n",end = "")

# Driver Code
if __name__ == '__main__':
    arr =  ["adf", "aahe", "bce", "bgdb"]
    N = len(arr)
    categorisation_Of_strings(arr, N)

    # This code is contributed by ipg2016107.
```

## JavaScript

```javascript
<script>

// Javascript program for the above approach

// Function to find the hash
// value of the string s
function stringPower(s)
{

    // Stores hash value of string
    var power = 0;
    var n = s.length;

    // Iterate over characters of the string
    for(var i = 0; i < n; i++)
    {

        // Calculate hash value
        power = (power + (s[i].charCodeAt(0))) % 26;
    }

    // Return the hash value
    return power;
}

// Function to classify the strings
// according to the given condition
function categorisation_Of_strings(s, N)
{

    // Maps strings with their strings
    // respective hash values
    var mp = new Map();

    // Traverse the array of strings
    for(var i = 0; i < N; i++)
    {

        // Find the hash value of the
        // of the current string
        var temp = stringPower(s[i]);

        // Push the current string in
        // value vector of temp key
        if (!mp.has(temp))
        {
            mp.set(temp, new Array());
        }
        var tmp = mp.get(temp);
        tmp.push(s[i]);
        mp.set(temp, tmp);
    }

    var tmp = Array();

    // Traverse over the map mp
    mp.forEach((value, key) => {
        tmp.push(key);
    });

    tmp.sort((a, b) => a - b);

     // Traverse over the map mp
    tmp.forEach((value) => {

        // Print the result
        mp.get(value).forEach(element => {
            document.write(element + " ");
        });
        document.write("<br>");
    });
}

// Driver Code
var arr = [ "adf", "aahe", "bce", "bgdb" ];
var N = arr.length;

categorisation_Of_strings(arr, N);

// This code is contributed by rutvik_56

</script>
```

**输出：**

```
aahe bgdb 
bce 
adf
```

**时间复杂度：** `O(N*M)`，其中 `M` 是最长字符串的长度。
**辅助空间：** `O(N*M)`