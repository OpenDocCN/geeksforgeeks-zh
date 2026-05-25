# Moment.js `moment().unix()`功能

> 原文: [https://www.geeksforgeeks.org/moment-js-moment-unix-function/](https://www.geeksforgeeks.org/moment-js-moment-unix-function/)

`moment().unix()`函数用于获取自 Unix Epoch 以来的秒数。基本上，Unix 时间是描述时间点的系统。

## 语法:
```
moment().unix();
```

## 参数:
此功能无参数。

## 返回值:
该函数以秒为单位返回 Unix 时间戳。

## 力矩模块安装:
1.  您可以访问[安装力矩模块](https://www.npmjs.com/package/moment)的链接。您可以使用此命令安装此软件包。
```
npm install moment
```
2.  安装力矩模块后，可以使用命令在命令提示符下检查您的`moment`版本。
```
npm version moment
```
3.  之后，您可以创建一个文件夹并添加一个文件，例如`index.js`，如下所示。

## 示例 1: 文件名:`index.js`
```
// Requiring the module
const moment = require('moment');

// Function call
var result = moment().unix();

console.log("Result:", result)
```

### 运行程序的步骤:
1.  项目结构会是这样的:
    ![](img/3209d9b4369c180282a34be8070d7d6e.png)
2.  运行`index.js`文件使用以下命令:
```
node index.js
```

### 输出:
```
Result: 1595007379
```

## 示例 2: 文件名:`index.js`
```
// Requiring the module
const moment = require('moment');

function getUnixTimeStamp() {
   return moment().unix();
}

// Function call
var result = getUnixTimeStamp();
console.log("Unix Timestamp in seconds:", result)
```

### 运行程序的步骤:
1.  项目结构会是这样的:
    ![](img/3209d9b4369c180282a34be8070d7d6e.png)
2.  运行`index.js`文件使用以下命令:
```
node index.js
```

### 输出:
```
Unix Timestamp in seconds: 1595007321
```

## 参考:
[https://momentjs.com/docs/#/displaying/unix-timestamp/](https://momentjs.com/docs/#/displaying/unix-timestamp/)