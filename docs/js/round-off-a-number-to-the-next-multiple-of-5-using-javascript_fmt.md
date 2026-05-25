# 用 JavaScript 将一个数字四舍五入到 5 的下一个倍数

> 原文：[https://www.geeksforgeeks.org/round-off-a-number-to-the-next-multiple-of-5-using-javascript/](https://www.geeksforgeeks.org/round-off-a-number-to-the-next-multiple-of-5-using-javascript/)

给定一个正整数 `n`，任务是将该数舍入到下一个可被 5 整除的整数。

**例：**

```javascript
Input : 46 
Output : 50

Input : 21
Output : 25

Input : 30 
Output : 30
```

**方法 1：**

*   将数字存入变量。
*   除以 5 得到小数值。
*   使用 `Math.ceil()` 获取该小数值的向上取整值。
*   乘以 5 得到结果。

```javascript
<script>
    function round(x) {
        return Math.ceil(x / 5) * 5;
    }

    var n = 34;
    console.log(round(n)); 
</script>
```

**输出：**

```javascript
35
```

**方法 2：**

*   将数字存入变量。
*   如果能被 5 整除，则返回原数。
*   否则，除以 5，取向下取整值，乘以 5，再加 5。

```javascript
<script>
    function round(x) {
        if (x % 5 == 0) {
            return int(Math.floor(x / 5)) * 5;
        } else {
            return (int(Math.floor(x / 5)) * 5) + 5;
        }
    }

    var n = 34;
    console.log(round(n)); 
</script>
```

**输出：**

```javascript
35
```