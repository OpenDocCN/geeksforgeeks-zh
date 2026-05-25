# Node.js `fs.rmSync()`方法

> 原文: [https://www.geeksforgeeks.org/node-js-fs-rmsync-method/](https://www.geeksforgeeks.org/node-js-fs-rmsync-method/)

`fs.rmSync()`方法用于同步删除给定路径上的文件。它也可以通过配置 `options` 对象递归地用于移除目录。它返回未定义。

**语法:**

```js
fs.rmSync( path, options );
```

**参数:** 该方法接受两个参数，如上所述，如下所述:

*   **Path:** 要删除的文件的路径。它可以是一个字符串、一个缓冲区或一个 web 地址。
*   **Option:** 是一个可用于指定可选参数的对象，这些参数将影响操作，如下所示:
    *   **force:** 是一个布尔值。如果路径不存在，异常将被忽略。
    *   **Recursion:** 是一个布尔值，指定是否执行递归目录删除。在此模式下，如果找不到指定路径并且操作在失败时重试，则不会报告错误。默认值为 `false`。

下面的例子说明了 Node.js 中的 `fs.rmSync()`方法:

### 示例 1: 本示例使用 `fs.rmSync()`方法删除文件。

**文件名: `index.js`**

```js
// Import necessary modules
let fs = require('fs');

// List files before deleting
getCurrentFilenames();

fs.rmSync('./dummy.txt');

// List files after deleting
getCurrentFilenames();

// This will list all files in current directory
function getCurrentFilenames() { 
    console.log("\nCurrent filenames:"); 
    fs.readdirSync(__dirname).forEach(file => { 
        console.log(file); 
    }); 
    console.log(""); 
}
```

使用以下命令运行 `index.js` 文件:

```bash
node index.js
```

**输出:**

```js
Current filenames:
dummy.txt
index.js
node_modules
package-lock.json
package.json

Current filenames:
index.js
node_modules
package-lock.json
package.json
```

### 示例 2: 本示例使用带有递归参数的 `fs.rmSync()`方法删除目录。

**文件名: `index.js`**

```js
// Import the filesystem module 
const fs = require('fs');

// List the files in current directory 
getCurrentFilenames();

// Using the recursive option to delete directory 
fs.rmSync("./build", { recursive: true });

// List files after delete 
getCurrentFilenames();

// List all files in current directory
function getCurrentFilenames() { 
  console.log("\nCurrent filenames:"); 
  fs.readdirSync(__dirname).forEach(file => { 
    console.log(file); 
  }); 
  console.log("\n"); 
}
```

使用以下命令运行 `index.js` 文件:

```bash
node index.js
```

**输出:**

```js
Current filenames:
build
index.js
node_modules     
package-lock.json
package.json

Current filenames:
index.js
node_modules
package-lock.json
package.json
```

**参考:** [https://nodejs.org/api/fs.html#fs_fs_rmsync_path_options](https://nodejs.org/api/fs.html#fs_fs_rmsync_path_options)