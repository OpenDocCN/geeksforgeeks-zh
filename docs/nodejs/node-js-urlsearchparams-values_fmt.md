# Node.js URLSearchParams.values()

> 原文: [https://www.geeksforgeeks.org/node-js-urlsearchparams-values/](https://www.geeksforgeeks.org/node-js-urlsearchparams-values/)

在`URLSearchParams`接口中，`values()`方法返回一个迭代器，它允许我们遍历对象中存在的所有值。

## 语法:

```js
searchParams.values();
```

## 返回:
返回每个名称-值对的值的ES6迭代器。

## 例 1:

```js
// Create a test URLSearchParams object
var searchParams = new URLSearchParams("keyA=valueA&keyB=valueB");

// Display the values
for(var value of searchParams.values()) {
  console.log(value);
}
```

## 输出:

```js
valueA
valueB
```

## 示例 2: 直接创建参数

```js
// Create a test URLSearchParams object
var searchParams = new URLSearchParams("name=deepak&age=18");

// Display the values
for(var value of searchParams.values()) {
  console.log(value);
}
```

## 输出:

```js
deepak
```

## 支持的浏览器:

*   Google Chrome
*   Internet Explorer
*   Edge
*   Opera
*   Safari