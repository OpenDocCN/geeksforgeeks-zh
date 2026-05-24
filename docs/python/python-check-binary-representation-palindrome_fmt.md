# 检查 Python 中二进制表示是否为回文

> 原文：[https://www.geeksforgeeks.org/python-check-binary-representation-palindrome/](https://www.geeksforgeeks.org/python-check-binary-representation-palindrome/)

给定一个整数`n`，编写一个 Python 函数，如果`n`的二进制表示是回文，则返回`True`，否则返回`False`。

示例：

```py
Input : n = 9
Output : True
Binary representation of n=9 is 1001 which 
is palindrome as well.

Input : n = 10
Output : False
Binary representation of n=10 is 1010 which 
is not palindrome.
```

这个问题我们已经有了解决方案，请参考[检查一个数字的二进制表示是否是回文](https://www.geeksforgeeks.org/check-binary-representation-number-palindrome/)链接。我们可以用 Python 非常快速地解决这个问题。方法很简单：

1.  使用 [`bin(num)`](https://www.geeksforgeeks.org/bin-in-python/) 函数将给定数字转换为其二进制表示。
2.  现在反转数字的二进制表示字符串，并将其与原始二进制表示字符串进行比较。如果两者相等，则数字的二进制表示是回文，否则不是。

**注：** 我们可以用[其他方法检查一个字符串是不是回文](https://www.geeksforgeeks.org/c-program-check-given-string-palindrome/)。

```py
# Function to check if binary representation of
# a number is pallindrome or not

def binaryPallindrome(num):

    # convert number into binary
    binary = bin(num)

    # skip first two characters of string
    # because bin function appends '0b' as 
    # prefix in binary representation of
    # a number
    binary = binary[2:]

    # now reverse binary string and compare
    # it with original
    return binary == binary[-1::-1]

# Driver program
if __name__ == "__main__":
    num = 9
    print binaryPallindrome(num)
```

输出：

```py
True
```