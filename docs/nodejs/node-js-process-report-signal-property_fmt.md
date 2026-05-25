# Node.js `process.report.signal` 属性

> 原文: [https://www.geeksforgeeks.org/node-js-process-report-signal-property/](https://www.geeksforgeeks.org/node-js-process-report-signal-property/)

`process.report` 是一个对象，其方法用于生成当前进程的诊断报告。`signal` 属性用于指定触发诊断报告创建的信号。默认为 `'SIGUSR2'`。

### 语法:
```js
process.report.signal
```

### 返回值:
该属性返回当前进程生成的诊断报告。

下面的例子说明了 Node.js 中 `process.report.signal` 属性的使用:

### 示例:
#### index.js
```js
// Node.js program to demonstrate the 
// process.report.signal Property

// Include process module 
const process = require('process');

// Printing process.report.signal property value 
console.log(`Report signal: ${process.report.signal}`);
```

### 运行命令:
```bash
node index.js
```

### 输出:
![](img/fcc7765ff0bd3e8e9a47f7f36fd3ba0d.png)

### 注意:
以上程序将使用 `node filename.js` 命令编译运行。

### 参考:
[https://nodejs.org/api/process.html#process_process_report_signal](https://nodejs.org/api/process.html#process_process_report_signal)