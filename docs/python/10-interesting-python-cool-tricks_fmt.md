
# 10 个有趣的蟒蛇酷招

> 原文: [https://www.geeksforgeeks.org/10-interesting-python-cool-tricks/](https://www.geeksforgeeks.org/10-interesting-python-cool-tricks/)

在 Python 中，我们可以返回多个值-

1.  A very unique feature of Python is that it returns multiple values at a time.

```py
    def GFG():
        g = 1
        f = 2
        return g, f

    x, y = GFG()
    print(x, y)
```

**Output:**

```py
    (1, 2)
```

2.  允许负索引: Python 允许对它的序列进行负索引。索引 -1 指的是最后一个元素，-2 指的是倒数第二个元素，依此类推。

```py
    my_list = ['geeks', 'practice', 'contribute']
    print(my_list[-1])
```

**Output:**

```py
    contribute
``` 
