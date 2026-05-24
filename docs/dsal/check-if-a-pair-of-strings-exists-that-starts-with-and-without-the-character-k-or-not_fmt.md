# 检查是否存在一对以字符 K 开头和不包含字符 K 的字符串

> 原文: [https://www.geeksforgeeks.org/check-if-a-pair-of-strings-exists-that-starts-with-and-without-the-character-k-or-not/](https://www.geeksforgeeks.org/check-if-a-pair-of-strings-exists-that-starts-with-and-without-the-character-k-or-not/)

给定一个由小写字符的字符串 `N` 和字符 `K` 组成的数组 `arr[]`，使得任何字符串都可以以字符 `K` 开始，任务是检查是否存在任何一对开始和不开始的字符串（`!`）带有字符 `K`。如果发现为真，则打印“是”。否则，打印“否”。

**示例:**

> **输入:** `arr[] = {"a", "!a", "b", "!c", "d", "!d"}`，`K = '!'`
> **输出:** 是
> **解释:**
> 存在有效的字符串对是 `{("a", "!a"), ("!d", "d")}`。
>
> **输入:** `arr[] = {"red", "red", "red", "!orange", "yellow", "!yellow", "blue", "cyan", "!green", "brown", "!gray"}`，`K = '!'`
> **输出:** 否

## 天真方法

解决给定问题最简单的方法是从数组中找到所有可能的对，并检查字符串对是否满足给定条件。

- **时间复杂度:** `O(N^2 * M)`，其中 `M` 是给定数组 `arr[]` 中字符串的最大长度。
- **辅助空间:** `O(1)`

## 高效途径

以上途径也可以使用词典解决。按照以下步骤解决问题:

1.  初始化一个字典，比如说 `visited` 来存储之前访问过的字符串。
2.  遍历列表 `arr[]`，在每次迭代中，如果当前字符串的起始字符是字符 `K`，则在 `visited` 中检查不带字符 `K` 的字符串，否则在 `visited` 中检查带字符 `K` 的字符串。如果找到字符串，则返回“是”。
3.  在每次迭代中，将字符串 `S` 添加到地图 `visited` 中。
4.  完成上述步骤后，如果不满足上述条件，则打印“否”。

下面是上述方法的实现:

### C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to check whether a pair of
// strings exists satisfying the conditions
string checkhappy(vector<string> arr, char K, int N)
{

    // Stores the visited strings
    set<string> visited;

    // Iterate over the array arr[]
    for (string s : arr) {

        // If first character of current
        // string is K
        if(s[0] == K)
            if (visited.find(s.substr(1)) != visited.end())
                return "Yes";

        // Otherwise
        else
            if (visited.find((K + s)) != visited.end())
                return "Yes";

        // Adding to the visited
        visited.insert(s);
    }

    return "No";
}

// Driver Code
int main() {

    // Given Input
    vector<string> arr = {"a", "! a", "b", "! c", "d", "! d"};
    char K = '!';
    int N = arr.size();

    cout << checkhappy(arr, K, N) << endl;

    return 0;
}

// This code is contributed Dharanendra L V.
```

### Python 3

```python
# Python program for the above approach

# Function to check whether a pair of
# strings exists satisfying the conditions
def checkhappy(arr, K, N):

    # Stores the visited strings
    visited = set()

    # Iterate over the array arr[]
    for s in arr:

        # If first character of current
        # string is K
        if(s[0] == K):
            if s[1:] in visited:
                return 'Yes'

        # Otherwise
        else:
            if (K + s) in visited:
                return 'Yes'

        # Adding to the visited
        visited.add(s)

    return "No"

# Driver Code
if __name__ == '__main__':

    # Given Input
    arr = ['a', '! a', 'b', '! c', 'd', '! d']
    K = '!'
    N = len(arr)

    print(checkhappy(arr, K, N))
```

### JavaScript

```javascript
<script>

// Javascript program for the above approach

// Function to check whether a pair of
// strings exists satisfying the conditions
function checkhappy(arr, K, N)
{

    // Stores the visited strings
    let visited = new Set();

    // Iterate over the array arr[]
    for(let s of arr)
    {

        // If first character of current
        // string is K
        if (s[0] == K)
        {
            if (visited.has(s.slice(1)))
                return "Yes";
        }

        // Otherwise
        else
        {
            if (visited.has(K + s))
                return "Yes";
        }

        // Adding to the visited
        visited.add(s);
    }
    return "No";
}

// Driver Code

// Given Input
let arr = [ "a", "! a", "b", "! c",
            "d", "! d" ];
let K = "!";
let N = arr.length;

document.write(checkhappy(arr, K, N));

// This code is contributed by gfgking

</script>
```

**输出:**

```
No
```

- **时间复杂度:** `O(N)`
- **辅助空间:** `O(1)`