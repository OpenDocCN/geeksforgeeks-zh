# Moment.js `moment().from()`函数

> 原文: [https://www.geeksforgeeks.org/moment-js-moment-from-function/](https://www.geeksforgeeks.org/moment-js-moment-from-function/)

`moment().from()`函数用于计算 Node.js 中任何其他时间的时间，它以日期为参数，从该日期开始计算时间。

## 语法

```
moment().from(Moment|String|Number|Date|Array, Boolean);
```

## 参数

这个函数接受两个参数，第一个是日期参数，可以是 `Moment`|`String`|`Number`|`Date`|`Array` 类型。第二个是可选的 `Boolean` 参数，返回不带后缀的值。

## 返回值

此函数返回日期。

## 力矩模块安装

1.  您可以访问[安装力矩模块](https://www.npmjs.com/package/moment)的链接。您可以使用此命令安装此软件包。
    ```
    npm install moment
    ```
2.  安装力矩模块后，可以使用命令在命令提示符下检查您的 `moment` 版本。
    ```
    npm version moment
    ```
3.  之后，您可以创建一个文件夹并添加一个文件，例如 `index.js`，如下所示。

## 示例 1

**文件名:** `index.js`

```
// Requiring the module
const moment = require('moment');

// Function call
var result = moment([2010, 8, 24]).from([2017, 1, 25]);
console.log(result);
```

**运行程序的步骤:**

1.  项目结构会是这样的:
    ![](img/3209d9b4369c180282a34be8070d7d6e.png)
2.  运行 `index.js` 文件使用以下命令:
    ```
    node index.js
    ```

**输出:**

```
6 years ago
```

## 示例 2

**文件名:** `index.js`

```
// Requiring the module
const moment = require('moment');

function timeFromDate(date){
   return moment([2011, 8, 24]).from([2019, 8, 24]);
}

var result = timeFromDate(moment);
console.log("Result:", result);
```

**运行程序的步骤:**

1.  项目结构会是这样的:
    ![](img/3209d9b4369c180282a34be8070d7d6e.png)
2.  运行 `index.js` 文件使用以下命令:
    ```
    node index.js
    ```

**输出:**

```
Result: 8 years ago
```

## 参考

[https://momentjs.com/docs/#/displaying/from/](https://momentjs.com/docs/#/displaying/from/)