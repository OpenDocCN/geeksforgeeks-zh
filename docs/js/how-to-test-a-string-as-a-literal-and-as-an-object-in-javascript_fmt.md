# 如何在 JavaScript 中将字符串作为文字和对象进行测试？

> 原文：[https://www.geeksforgeeks.org/how-to-test-a-string-as-a-literal-and-as-an-object-in-javascript/](https://www.geeksforgeeks.org/how-to-test-a-string-as-a-literal-and-as-an-object-in-javascript/)

在本文中，我们学习如何使用 [JavaScript](https://www.geeksforgeeks.org/javascript-tutorial/) 将字符串作为文字和对象进行测试。

## 什么是 JavaScript Literal？

文字是在源代码中表示固定值的方式。在大多数编程语言中，值由整数、浮点数、字符串来标记，通常由布尔值和字符来标记，枚举类型和复合值（如数组、记录和对象）也由其他名称来标记。

## 什么是 JavaScript 对象？

每个对象都包含一个无序列表的原始数据类型（有时是引用数据类型）存储成对的名称和值。在列表中，每个项目都是一个属性。

## typeof 运算符

JavaScript 中的 `typeof` 运算符返回一个字符串，该字符串标识表达式的数据类型。它用于确定其操作数的数据类型（返回一个字符串）。操作数可以是文字或数据结构，如变量、函数或对象。运算符返回数据的类型。`typeof` 的结果可以是一个 `object`，一个 `boolean`，一个 `function`，一个 `number`，一个 `string`，或者一个 `undefined` 值。

## instanceof 运算符

`instanceof` 运算符检查 LHS（左侧）对象是否是 RHS（右侧）类的对象。如果对象属于该特定类别，则返回 `true`，否则返回 `false`。

## 示例

在本例中，我们将使用 `if-else` 条件来检查字符串是对象还是文字。

```javascript
<script>
    function check(str) {
        if(str instanceof String) {
            return "It is an object of string";
        } else {
            if(typeof str === "string") {
                return "It is a string literal";
            } else {
                return "another type";
            }
        }
    }

    // Pass a literal
    console.log(check("Hello geeks"));

    // Pass an object of string
    let s = new String("Hi");
    console.log(check(s));
</script>
```

**输出：**

```
It is a string literal
It is an object of string
```