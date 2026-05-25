# Node.js 导出模块

> 原文: [https://www.geeksforgeeks.org/node-js-export-module/](https://www.geeksforgeeks.org/node-js-export-module/)

Node.js 中的 `module.exports` 用于将任何文字、函数或对象作为一个模块导出。它用于将 JavaScript 文件包含到 node.js 应用程序中。`module` 类似于用于表示当前模块的变量，`exports` 是作为模块公开的对象。

## 语法

### 语法 1

```js
module.exports = literal | function | object
```

**说明:** 这里赋值（字面|函数|对象）直接作为模块公开，可以直接使用。

### 语法 2

```js
module.exports.variable = literal | function | object
```

**说明:** 这里赋值（字面|函数|对象）是作为模块间接公开的，可以使用变量来消耗。

## 示例 1: 导出文字

1.  创建一个名为 `app.js` 的文件，并使用 `module.exports` 导出文本。

    ```js
    module.exports = "GeeksforGeeks";
    ```

2.  创建一个名为 `index.js` 的文件，导入文件 `app.js` 以将导出的文本打印到控制台。

    ```js
    const company = require("./app");
    console.log(company);
    ```

3.  **输出:**

    ```js
    GeeksforGeeks
    ```

## 示例 2: 导出对象

1.  创建一个名为 `app.js` 的文件，并使用 `module.exports` 导出对象。

    ```js
    module.exports = {
      name: 'GeeksforGeeks',
      website: 'https://geeksforgeeks.org'
    }
    ```

2.  创建一个名为 `index.js` 的文件，导入文件 `app.js` 以将导出的对象数据打印到控制台。

    ```js
    const company = require('./app');

    console.log(company.name);
    console.log(company.website);
    ```

3.  **输出:**

    ```js
    GeeksforGeeks
    https://geeksforgeeks.org
    ```

## 示例 3: 导出功能

1.  创建一个名为 `app.js` 的文件，并使用 `module.exports` 导出该函数。

    ```js
    module.exports = function (a, b) {
      console.log(a + b);
    }
    ```

2.  创建一个名为 `index.js` 的文件，导入文件 `app.js` 使用导出的功能。

    ```js
    const sum = require('./app');

    sum(2, 5);
    ```

3.  **输出:**

    ```js
    7
    ```

## 示例 4: 将函数导出为类

1.  创建一个名为 `app.js` 的文件。使用 `this` 关键字定义函数，并使用 `module.exports` 导出该函数。

    ```js
    module.exports = function () {
      this.name = 'GeeksforGeeks';
      this.website = 'https://geeksforgeeks.org';
      this.info = () => {
        console.log(`Company name - ${this.name}`);
        console.log(`Website - ${this.website}`);
      }
    }
    ```

2.  创建一个名为 `index.js` 的文件，导入文件 `app.js` 并将导出的函数作为类使用。

    ```js
    const Company = require('./app');

    const firstCompany = new Company();

    firstCompany.info();
    ```

3.  **输出:**

    ```js
    Company name - GeeksforGeeks
    Website - https://geeksforgeeks.org
    ```

## 示例 5: 从单独的文件夹加载模块

```js
const index = require('./models/lang/index.js');
```

**说明:** 在上面的例子中，`index.js` 文件位于 `models` 文件夹内的 `lang` 文件夹下。我们可以使用 `./` 转到根文件夹，然后相对于它移动。