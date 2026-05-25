# 如何用 JavaScript 获取字符串的前三个字符？

> 原文：[https://www.geeksforgeeks.org/how-to-get-the-first-three-characters-of-a-string-using-javascript/](https://www.geeksforgeeks.org/how-to-get-the-first-three-characters-of-a-string-using-javascript/)

下面的方法介绍了如何找到字符串的 3 个字母，这里我们将使用给定日期的 JavaScript 将日期名称作为字符串。

**例：**

```
Input: today
Output: SUN

Input: tomorrow
Output: MON

Input: yesterday
Output: SAT

Input: 01-04-2021
Output: THU
```

**方法：**

*   首先，使用 `new Date()` 获取当前日期并将其存储在变量 `date` 中。
*   如果输入日期是明天，使用 `setDate()` 方法将 `date` 增加一天；如果输入日期是昨天，则从 `date` 中减少一天。
*   如果值不是今天的，那么我们将把输入的日期传递给 `Date()` 对象。这就是为什么如果用户输入 `today`，那么 `Date()` 将是默认值，默认的 `Date()` 对象描述今天的日期。
*   现在我们通过使用 `date.getDay()` 方法获取日期。它将返回一个介于 0 到 6 之间的数字，其中 0 代表 `Sunday`，6 代表 `Saturday`，其余的日期按顺序排列。创建一个包含星期几的数组。使用索引来获取所需的日期名称。
*   通过切片提取前三个字符。

**示例：** 创建一个 `index.js` 文件，并写下以下代码。

```javascript
<script>
// Javascript program to get three beginning characters of the day

function getDay(d) {
    let date = new Date();
    let days = ["SUNDAY", "MONDAY", "TUESDAY", "WEDNESDAY",
        "THURSDAY", "FRIDAY", "SATURDAY"]

    if (d === "tomorrow") {
        date.setDate(date.getDate() + 1)
    } else if (d === "yesterday") {
        date.setDate(date.getDate() - 1)
    } else if (d != "today") {
        date = new Date(d);
    }

    // Get the todays day
    let day = days[date.getDay()]

    // Extract three characters from the beginning
    let threeCharDay = day.slice(0, 3)

    // Print or return the three character day
    console.log(threeCharDay)
}

// Function calls
getDay("yesterday")
getDay("today")
getDay("tomorrow")
getDay("2021-03-30")
getDay("2021-03-31")
getDay("2021-04-01")
</script>
```