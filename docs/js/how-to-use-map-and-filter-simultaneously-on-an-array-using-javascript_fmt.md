# 如何用 JavaScript 在数组上同时使用映射和过滤？

> 原文: [https://www.geeksforgeeks.org/how-to-use-map-and-filter-simultaneously-on-an-array-using-javascript/](https://www.geeksforgeeks.org/how-to-use-map-and-filter-simultaneously-on-an-array-using-javascript/)

给定一个数组，任务是同时使用过滤器和映射函数到给定的数组。首先让我们简单地看一下映射和过滤函数:

## filter() 方法

`filter()` 方法返回一个新数组，其中包含通过在原始数组上执行的特定测试的元素。

### 语法

```
let newArray = oldArray.filter((currentValue, index, array) {
    // Returns element to new Array
});
```

### 使用的参数和变量

*   `newArray`: 返回的数组。
*   `oldArray`: 过滤函数运行在这个数组的每个元素上。
*   `currentValue`: 当前元素的值。
*   `index`: 当前元素的数组索引。
*   `array`: 当前元素所属的数组对象。

## map() 方法

`map()` 方法用于对数组中的每个元素应用一个函数，并返回一个与输入数组大小相同的新数组。

### 语法

```
let newArray = oldArray.map((currentValue, index, array) {
    // Returns element to new Array
});
```

### 使用的参数和变量

*   `newArray`: 要返回的数组。
*   `oldArray`: 映射函数运行在这个数组的每个元素上。
*   `currentValue`: 当前元素的值。
*   `index`: 当前元素的数组索引。
*   `array`: 当前元素所属的数组对象。

## 方法

首先，通过使用 `filter()` 函数，我们将从满足给定条件的数组中检索那些元素。因为 `filter()` 方法将返回包含所需元素的数组。现在我们将应用 `map()` 方法对 `filter()` 方法返回的数组的所有元素执行指定的操作。

## 示例

```
<script>
    /* Printing the name of students who play
       basketball using filter and map method 
       simultaneously. */

    // Taking an array of Student object
    let students = [
        { id: "001", name: "Anish", sports: "Cricket" },
        { id: "002", name: "Smriti", sports: "Basketball" },
        { id: "003", name: "Rahul", sports: "Cricket" },
        { id: "004", name: "Bakul", sports: "Basketball" },
        { id: "005", name: "Nikita", sports: "Hockey" }
    ]

    /* Applying filter function on students array to
       retrieve those students Objects who play 
       basketball and then the new array returned by
       filter method is mapped in order to get the name
       of basketball players instead of whole object.*/
    let basketballPlayers = students.filter(function (student) {
        return student.sports === "Basketball";
    }).map(function (student) {
        return student.name;
    })

    console.log("Basketball Players are:");

    // Printing out the name of Basketball players
    basketballPlayers.forEach(function (players) {
        console.log(players);
    });
</script>
```

## 输出

```
Basketball Players are:
Smriti
Bakul
```