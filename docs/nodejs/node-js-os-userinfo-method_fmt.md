# Node.js | os.userInfo()方法

> 原文:[https://www.geeksforgeeks.org/node-js-os-userinfo-method/](https://www.geeksforgeeks.org/node-js-os-userinfo-method/)

`os.userInfo()`方法是`os`模块内置的应用编程接口，用于获取当前有效用户的信息。

## 语法:

```js
os.userInfo( options )
```

## 参数:

该方法接受单参数`options`，为可选参数。它指定要传递的进程选项，并且返回一个包含编码作为参数的对象。

*   `code`: 指定返回数据的字符编码。如果设置为`"Buffer"`，用户名、shell和homedir值将是buffer实例。默认值是`utf8`。

## 返回值:

返回一个指定当前有效用户信息的对象，包含用户名、uid、gid、shell、homedir类的值。

**注意:**在POSIX平台上，这一般是密码文件的子集，包含用户名、uid、gid、shell和homedir。Windows shell设置为`null`，uid、gid为`-1`。

下面的例子说明了`os.userInfo()`在Node.js中的使用:

## 示例 1:

```js
// Node.js program to demonstrate the
// os.userInfo() Method

// Allocating os module
const os = require('os');

// Printing os.userInfo() values
try {

// Printing user information
    console.log(os.userInfo());
} catch (err) {

// Printing if any exception occurs
    console.log(": error occurred" + err);
}
```

**输出:**

```js
{ uid: -1,
  gid: -1,
  username: 'gekcho',
  homedir: 'C:\\Users\\gekcho',
  shell: null }
```

## 示例 2:

```js
// Node.js program to demonstrate the
// os.userInfo() Method

// Allocating os module
const os = require('os');

// Printing os.userInfo()
try{

// Setting options for os.userInfo()
    // method
    var options = {
        encoding: 'buffer'
    };

// Printing user information
    console.log(os.userInfo(options));
} catch(err){

// Printing exception if any
    console.log(": error occurred" + err);
}
```

**输出:**

```js
{ uid: -1,
  gid: -1,
  username: <Buffer 6d 75 6b 75 6c>,
  homedir: <Buffer 43 3a 5c 55 73 65 72 73 5c 6d 75 6b 75 6c>,
  shell: null }
```

**注意:**以上程序将使用`node filename.js`命令编译运行。

**参考:**[https://nodejs.org/api/os.html#os_os_userinfo_options](https://nodejs.org/api/os.html#os_os_userinfo_options)