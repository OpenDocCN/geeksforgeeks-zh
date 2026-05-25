# Moment.js `moment().calendar()` 功能

> 原文: [https://www.geeksforgeeks.org/moment-js-moment-calender-function/](https://www.geeksforgeeks.org/moment-js-moment-calender-function/)

`moment().calendar()` 功能用于显示相对于给定参考日期的日历时间。默认情况下，它被设置为当天即今天的开始。

## 语法

```
moment().calendar(referenceDay, formats);
```

## 参数

这个函数有两个参数，第一个是 `referenceDay`，另一个是 `format`。

## 返回值

此函数返回日期。

## Moment 模块安装

1.  您可以访问 [安装 Moment 模块](https://www.npmjs.com/package/moment) 的链接。您可以使用此命令安装此软件包。

    ```
    npm install moment
    ```

2.  安装 Moment 模块后，您可以使用命令在命令提示符下检查您的 `moment` 版本。

    ```
    npm version moment
    ```

3.  之后，您可以创建一个文件夹并添加一个文件，例如 `index.js`，如下所示。

## 示例 1

**文件名:** `index.js`

```javascript
// Requiring the module
const moment = require('moment');

// Function call
var result1 = moment(new Date()).calendar(null, {
    sameDay: function (now) {
      if (this.isBefore(now)) {
        return '[Something Will Happen Today Only]';
      } else {
        return '[Something Already Happened Today]';
      }
    }
});

var result2 = moment().calendar(null, {
    sameDay: function (now) {
       if (this.isBefore(now)) {
          return '[Something Will Happen Today Only]';
       } else {
          return '[Something Already Happened Today]';
       }
    }
});

console.log(result1);
console.log(result2);
```

### 运行程序的步骤

1.  项目结构会是这样的:
    ![](img/3209d9b4369c180282a34be8070d7d6e.png)
2.  使用以下命令运行 `index.js` 文件:

    ```
    node index.js
    ```

### 输出

```
Something Will Happen Today Only
Something Already Happened Today
```

## 示例 2

**文件名:** `index.js`

```javascript
// Requiring the module
const moment = require('moment');

function getCalendar(date){
   return moment().calendar();
}

// Function call
var result = getCalendar(moment);
console.log("Result:", result);
```

### 运行程序的步骤

1.  项目结构会是这样的:
    ![](img/3209d9b4369c180282a34be8070d7d6e.png)
2.  使用以下命令运行 `index.js` 文件:

    ```
    node index.js
    ```

### 输出

```
Result: Today at 10:28 PM
```

## 参考

[https://momentjs.com/docs/#/displaying/calendar-time/](https://momentjs.com/docs/#/displaying/calendar-time/)