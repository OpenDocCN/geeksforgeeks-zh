# HTML 实体解析器

> 原文:[https://www.geeksforgeeks.org/html-entity-parser/](https://www.geeksforgeeks.org/html-entity-parser/)

给定一个字符串 **str** ，其中有各种 [HTML 实体](https://www.geeksforgeeks.org/html-entities/)，任务是用它们对应的特殊字符替换这些实体。

> **HTML 实体解析器**是以 HTML 代码为输入，用字符本身代替特殊字符的所有实体的解析器。HTML 的特殊字符及其实体为引号:实体为“，符号字符为”。

下面是 HTML 实体，它们对应的特殊字符如下表所示:

| 名称/描述 | HTML 实体 | 特殊字符 |
| --- | --- | --- |
| 空间 | `&nbsp;` |  |
| &的记号名称 | `&amp;` | `&` |
| 大于 | `&gt;` | `>` |
| 不到 | `&lt;` | `<` |
| 单引号 | `&apos;` | `'` |
| 双引号 | `&quot;` | `"` |
| 商标 | `&reg;` | `®` | 版权标志 | `&copy;` | `©` | 斜杠 | `&frasl;` | `⁄` |

**示例:**

> **输入:**str = " 17&gt；25 和 25&lt；17"
> **输出:** 17 > 25 和 25 < 17
> **说明:**在上例中&gt；是否将
> 替换为相应的特殊字符
> >和&lt；被<代替
> 
> **输入:**str =&复制；是版权的象征”
> T3】输出:是版权的象征
> **说明:**在上例中&复制；
> 是否被相应的特殊字符
> 代替

**方法 1–使用[无序 _ 地图](https://www.geeksforgeeks.org/unordered_map-in-stl-and-its-applications/) :** 步骤如下:

1.  将带有字符的 HTML 实体存储在[地图](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)中。
2.  遍历给定的字符串，如果遇到任何字符 **' & '** ，那么找出在这个&符号之后存在哪个 HTML 实体。
3.  在输出字符串中添加与实体对应的字符。
4.  打印输出字符串作为结果。

下面是上述方法的实现:

## C++

```html
// C++ program for the above approach
#include <iostream>
#include <unordered_map>
using namespace std;

class GfG {
public:
    unordered_map<string, string> m;

public:
    // Associating html entity with
    // special character
    void initializeMap()
    {
        m["""] = "\"";
        m["'"] = "'";
        m["&"] = "&";
        m[">"] = ">";
        m["<"] = "<";
        m["⁄"] = "/";
        m[" "] = " ";
        m["®"] = "®";
        m["©"] = "©";
    }

public:
    // Function that convert the given
    // HTML Entity to its parsed String
    string parseInputString(string input)
    {
        // Output string
        string output = "";

        // Traverse the string
        for (int i = 0;
             i < input.size(); i++) {

            // If any ampersand is occurred
            if (input[i] == '&') {

                string buffer;

                while (i < input.size()) {

                    buffer = buffer + input[i];

                    // If any Entity is found
                    if (input[i] == ';'
                        && m.find(buffer)
                               != m.end()) {

                        // Append the parsed
                        // character
                        output = output
                                 + m[buffer];

                        // Clear the buffer
                        buffer = "";
                        i++;
                        break;
                    }
                    else {
                        i++;
                    }
                }

                if (i >= input.size()) {
                    output = output
                             + buffer;
                    break;
                }
                i--;
            }
            else {
                output = output
                         + input[i];
            }
        }

        // Return the parsed string
        return output;
    }
};

// Driver Code
int main()
{
    // Given String
    string input = "17 > 25 and 25 < 17";
    GfG g;

    // Initialised parsed string
    g.initializeMap();

    // Function Call
    cout << g.parseInputString(input);
    return 0;
}
```

**Output:**

```html
17 > 25 and 25 < 17

```

***时间复杂度:** *O(N)*
**辅助空间:** *O(N)**

**方法 2–使用模式匹配:**
以下是步骤:

1.  遍历给定的字符串**字符串**。
2.  遍历时，如果遇到任何字符 **' & '** ，那么找出在这个&符号之后出现的是哪个 HTML 实体。
3.  在上表匹配字符的上表中，将实体对应的字符添加到输出字符串中。
4.  遍历上述字符串后，打印输出字符串作为结果。

下面是上述方法的实现:

## C++

```html
// C++ program to Parse the HTML Entities
#include <iostream>
using namespace std;

class GfG {

public:
    string parseInputString(string input)
    {

        // To store parsed string
        string output = "";

        for (int i = 0;
             i < input.size(); i++) {

            // Matching pattern of html
            // entity
            if (input[i] == '&') {
                string buffer;

                while (i < input.size()) {
                    buffer = buffer + input[i];

                    // Check match for (\)
                    if (input[i] == ';'
                        && buffer == """) {
                        output = output + "\"";
                        buffer = "";
                        i++;
                        break;
                    }

                    // Check match for (')
                    else if (input[i] == ';'
                             && buffer == "'") {
                        output = output + "'";
                        buffer = "";
                        i++;
                        break;
                    }

                    // Check match for (&)
                    else if (input[i] == ';'
                             && buffer == "&") {
                        output = output + "&";
                        buffer = "";
                        i++;
                        break;
                    }

                    // Check match for (>)
                    else if (input[i] == ';'
                             && buffer == ">") {
                        output = output + ">";
                        buffer = "";
                        i++;
                        break;
                    }

                    // Check match for (<)
                    else if (input[i] == ';'
                             && buffer == "<") {
                        output = output + "<";
                        buffer = "";
                        i++;
                        break;
                    }

                    // Check match for (/)
                    else if (input[i] == ';'
                             && buffer == "⁄") {
                        output = output + "/";
                        buffer = "";
                        i++;
                        break;
                    }

                    // Check match for (" ")
                    else if (input[i] == ';'
                             && buffer == " ") {
                        output = output + " ";
                        buffer = "";
                        i++;
                        break;
                    }

                    // Check match for (®)
                    else if (input[i] == ';'
                             && buffer == "®") {
                        output = output + "®";
                        buffer = "";
                        i++;
                        break;
                    }

                    // Check match for (©)
                    else if (input[i] == ';'
                             && buffer == "©") {
                        output = output + "©";
                        buffer = "";
                        i++;
                        break;
                    }
                    else {
                        i++;
                    }
                }

                if (i >= input.size()) {
                    output = output + buffer;
                    break;
                }
                i--;
            }
            else {
                output = output + input[i];
            }
        }

        // Return the parsed string
        return output;
    }
};

// Driver Code
int main()
{
    // Given String
    string input = "17 > 25 and 25 < 17";
    GfG g;

    // Initialised parsed string
    g.initializeMap();

    // Function Call
    cout << g.parseInputString(input);
    return 0;
}
```

**Output:**

```html
17 > 25 and 25 < 17

```

***时间复杂度:** *O(N)*
**辅助空间:** *O(N)**

**方法 3–使用[正则表达式](https://www.geeksforgeeks.org/write-regular-expressions/)** :
以下是步骤:

1.  将所有表达式及其映射值存储在一个[映射](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/) **M** 中。
2.  对于地图中的每个**键**，使用:

    > 正则表达式 e(密钥);

3.  现在将上面的正则表达式用它在 Map M 中的映射值替换为:

    > regex_replace(str，e，value)；
    > 其中，
    > str 为输入字符串，
    > e 为上一步形成的表达式，
    > val 为地图中用表达式 e 映射的值

4.  重复以上步骤，直到所有表达式都没有被替换。

下面是上述方法的实现:

## C++

```html
// C++ program for the above approach
#include <iostream>
#include <regex>
#include <unordered_map>
using namespace std;

// Given Expression with mapped value
const unordered_map<string, string> m;
m = { { """, "\" },
        { "'", "'" },
        { "&", "&" },
        { ">", ">" },
        { "<", "<" },
        { "⁄", "/" } };

// Function that converts the given
// HTML Entity to its parsed String
string
parseInputString(string input)
{
    for (auto& it : m) {

        // Create ReGex Expression
        regex e(it.first);

        // Replace the above expression
        // with mapped value using
        // regex_replace()
        input = regex_replace(input, e,
                              it.second);
    }

    // Return the parsed string
    return input;
}

// Driver Code
int main()
{
    // Given String
    string input
        = "17 > 25 and 25 < 17";

    // Function Call
    cout << parseInputString(input);
    return 0;
}
```

**Output:**

```html
17 > 25 and 25 < 17

```

***时间复杂度:** *O(N)*
**辅助空间:** *O(N)**