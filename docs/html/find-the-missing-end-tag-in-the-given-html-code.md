# 在给定的 HTML 代码中找到缺失的结束标签

> 原文:[https://www . geesforgeks . org/find-the-missing-end-tag-in-给定的 html-code/](https://www.geeksforgeeks.org/find-the-missing-end-tag-in-the-given-html-code/)

给定一个字符串 **htmlCode** ，它是网页的 HTML 代码，任务是在 HTML 代码中找到丢失的结束标签。
**例:**

```html
Input: htmlCode = "<!DOCTYPE html>
<html>
<head>
    <title>
        GeeksforGeeks
    </title>
</head>
<body>
    <button>
</body>
</html>"
Output: </button>

Input: htmlCode = "<!DOCTYPE html>
<html>
<body>
    <p>Hello</p>

</html>"
Output: </body>
```

**方法:**想法是使用[栈](https://www.geeksforgeeks.org/stack-data-structure/)来跟踪 HTML 代码中的当前开始标记，如果在任何时刻有一个结束标记与表示开始标记的栈顶不匹配。那么堆栈顶部的标签将首先被关闭。因此，栈顶将是 HTML 代码中所需的缺失标记。
以下是上述方法的实施:

## 计算机编程语言

```html
# Python implementation to find the
# the missing end in the HTML code

# Function to Auto complete the
# missing tag in the html Code
def autoComplete(s):

    # Split the html Code in line
    linesOfCode = list(s.strip().split("\n"))

    # Tags which are self closed doesn't
    # needs to be closed
    selfClosedTags = ["area",  "base", "br", \
            "col",   "embed",  "hr",    "img", \
            "input", "link", "meta", "param", \
                    "source", "track", "wbr"]
    n = len(linesOfCode)

    stack = []

    # Loop to iterate over the
    # lines of code
    for i in range(n):
        j = 0

        # Current Line
        line = linesOfCode[i]
        while j < len(linesOfCode[i]):

            # Condition to check if the current
            # character is a end tag in the code
            if j + 1 < len(line) and line[j] == "<"\
                            and line[j + 1] == "/":
                tag = []
                j += 2

                # Loop to get the tag
                while j < len(line) and\
                   "a" <= line[j] <= "z":
                    tag.append(line[j])
                    j += 1
                while j < len(line) and line[j] != ">":
                    j += 1
                if stack[-1] != tag:
                    tag = stack[-1]
                    return "</" + "".join(tag) + ">"
                stack.pop()

            # Condition to check if the current
            # character denotes the code is
            # of the HTML 5
            elif j + 1 < len(line) and line[j] == "<"\
                                  and line[j] == "!":
                continue

            # Condition to check if the current
            # tag is a start tag of the HTML Code
            elif line[j] == "<":
                tag = []
                j += 1

                # Loop to get the tag of the HTML
                while j < len(line) and\
                      "a" <= line[j] <= "z":
                    tag.append(line[j])
                    j += 1
                while j < len(line) and line[j] != ">":
                    j += 1

                # Condition to check if the
                # current tag is not a self closed tag
                if "".join(tag) not in selfClosedTags:
                    stack.append(tag)
            j += 1

    # Condition to check if any tag
    # is unbalanced then return that tag
    if stack:
        tag = stack.pop()
        return "</" + "".join(tag) + ">"
    return -1

# Driver Code
if __name__ == "__main__":
    s = """<! DOCTYPE html>
<html>
<head>
    <title>
        GeeksforGeeks
    </title>
</head>
<body>
    <button>
</body>
</html>"""
    tag = autoComplete(s)
    print(tag)
```

**Output:** 

```html
</button>
```