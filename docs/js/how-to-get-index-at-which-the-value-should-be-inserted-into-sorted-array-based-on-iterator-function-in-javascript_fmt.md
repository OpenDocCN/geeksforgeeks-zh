# 如何基于 JavaScript 中的迭代器函数获取值应该插入排序数组的索引？

> 原文：[https://www.geeksforgeeks.org/how-to-get-index-at-which-the-value-should-be-inserted-into-sorted-array-based-on-iterator-function-in-javascript/](https://www.geeksforgeeks.org/how-to-get-index-at-which-the-value-should-be-inserted-into-sorted-array-based-on-iterator-function-in-javascript/)

这里，我们使用排序函数对数组进行排序，并打印数组和新元素在 DOM 中的位置。

**进场：**

*   创建一个空数组。
*   现在创建一个以数组为参数的排序函数。
*   现在创建一个 `onClick` 函数，因为它会在按钮被按下时自动运行。
*   在 `onClick` 函数中，我们首先向数组添加元素，然后使用迭代器函数。
*   查找元素的位置。当我们找到位置时，我们会查看数组元素是否大于新元素，如果是，则标记该位置并跳出循环。
*   最后，我们将把数组和新添加元素在 DOM 中的位置打印出来。

## HTML

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <script src="gfg.js"></script>

    <style>
        input {
            width: 300px;
            height: 25px;
        }

        button {
            width: 100px;
            height: 31px;
        }
    </style>
</head>

<body>
    <p style="font-size: 35px;">
        Input the elements in the array : 
    </p>

    <input type="text" id="element">
    <button type="button" onclick="add()">ADD</button>
    <br>

    <span id="array" style="font-size: 25px;"></span>
    <br>

    <span id="new-position-array" 
          style="font-size: 25px;">
    </span>
</body>

</html>
```

## gfg.js

```javascript
// Creating an empty array and when we add the
// elements we increase the number of elements
// by 1
const arr = Array();
var numberOfElements = 0;

// Sorting function to sort the array 
// Here we use the selection sort 
// algorithm for sorting
function sort(arr) {
    for (let i = 0; i < arr.length; i++) {
        let min = i;
        for (let j = i + 1; j < arr.length; j++) {
            if (arr[j] < arr[min])
                min = j;
        }
        let temp = arr[min];
        arr[min] = arr[i];
        arr[i] = temp;
    }
}

// onClick function add 
function add() {

    // Taking the input from the text box to
    // add the element to the given array
    arr[numberOfElements] = parseInt(
        document.getElementById("element").value);

    // Increasing the array length to add
    // next number to the array
    numberOfElements++;

    // Variables to find the position of
    // the newly added element
    var position = 0;
    var flag = false;

    // Finding the position of the newly added
    // element in the sorted array
    var newElement = arr[numberOfElements - 1];
    for (let i = 0; i < arr.length; i++) {

        // If the array element is greater then
        // the newly added element than mark that
        // position and break the loop as this is
        // the position of newly added element in
        // the gieven sorted array
        if (arr[i] > newElement) {
            position = i;
            flag = true;
            break;
        }
    }

    // If the newly added element is highest among
    // the elements in the array then its position
    // would be the array length - 1
    if (flag == false)
        position = arr.length - 1;

    // Now calling the sort function to sort the
    // given array after insertion
    sort(arr);

    // For printing into the DOM
    document.getElementById("element").value = "";

    var print = "Array is : ";

    for (let i = 0; i < arr.length; i++) {
        print += arr[i] + " ";
    }

    document.getElementById("array").innerHTML = print;

    document.getElementById("new-position-array").innerHTML 
        = "New element: " + newElement + " at Position: " 
        + position;
}
```