# 如何在 Node.js 中使用 Sequelize？

> 原文: [https://www.geeksforgeeks.org/how-to-use-sequelize-in-node-js/](https://www.geeksforgeeks.org/how-to-use-sequelize-in-node-js/)

Sequelize 是一个基于承诺的 Node.js ORM，适用于 Postgres、MySQL、MariaDB、SQLite 和微软 SQL Server。它的特点是坚实的事务支持、关系、急切和懒惰的加载、读复制等等。

## Sequelize 的特性

*   Sequelize 是一个第三方包，具体来说是一个**对象关系映射库 (ORM)**。
*   **标准化**的表单通常在代码中只有一个模式定义。这使得模式非常清晰，并且更改起来非常简单。
*   **无需学习 SQL** - 查询是用普通的 JavaScript 编写的。

## 设置 Node.js app

使用以下命令启动 `node.js` 应用：

```js
npm init -y
```

## 安装 Sequelize

1.  Sequelize 需要在你的项目中安装 `MySql` 模块。如果你尚未安装 `MySql` 模块，请确保在安装 Sequelize 之前先安装 [MySQL 2 模块](https://www.npmjs.com/package/mysql2)。你需要使用以下命令来安装此模块。

```js
npm install mysql2
```

2.  安装 *MySQL 2 模块* 后，我们需要安装 [Sequelize 模块](https://www.npmjs.com/package/sequelize)。使用以下命令安装此模块。

```js
npm install sequelize
```

## 需求模块

你需要使用以下代码行在项目中引入 Sequelize 模块。

```js
const Sequelize = require('sequelize');
```

## 配置文件

```js
// 引入 Sequelize 模块
const Sequelize = require('sequelize')

// 创建 Sequelize 的新对象
const sequelize = new Sequelize(
    'DATABASE_NAME',
    'DATABASE_USER_NAME',
    'DATABASE_PASSWORD', {
        // 显式指定 mysql 数据库
        dialect: 'mysql',
        // 默认主机是 'localhost'
        host: 'localhost'
    }
);

// 导出 sequelize 对象。
// 我们可以在另一个文件中使用它
// 来创建模型
module.exports = sequelize
```