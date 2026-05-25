# 如何在 JavaScript 中从对象自身的可枚举属性中获取函数属性名的数组？

> 原文：[https://www.geeksforgeeks.org/how-to-get-an-array-of-function-property-names-from-own-enumerable-properties-of-an-object-in-javascript/](https://www.geeksforgeeks.org/how-to-get-an-array-of-function-property-names-from-own-enumerable-properties-of-an-object-in-javascript/)

**可枚举属性：** 可以使用 `for...in` 循环或 [`Object.keys()`](https://www.geeksforgeeks.org/object-keys-javascript/) 方法进行迭代的对象的所有属性被称为可枚举属性。

在本文中，我们将看到如何获取一个对象的函数数组，这些函数是**可枚举的**。这可以通过以下两个步骤来实现。

*   使用 [`Object.keys()`](https://www.geeksforgeeks.org/object-keys-javascript/) 方法，我们可以获取一个对象所有可枚举属性（包含函数和数据成员）的数组。

**语法：**

```javascript
Object.keys(object_name)
```

*   然后我们可以使用 [`Array.filter()`](https://www.geeksforgeeks.org/javascript-array-filter-method/) 方法过滤上面获得的数组，使其只包含可枚举的函数名（消除所有数据成员）。

**语法：**

```javascript
new_arr = arr_name.filter( (element)=> {.....} )
```

在下面创建不可枚举属性的实现中，我们使用了 [`Object.defineProperty()`](https://www.geeksforgeeks.org/javascript-object-defineproperty-method/) 方法。

## 示例

```javascript
<script>
// Person object has name, age, salary
    // and print properties
    // Except salary, all properties are enumerable
    let Person = {
        name: "Mahesh",
        age: 25,
        print: function () {
            console.log(`${this.name} ${(this, age)}`);
        },
    };

// salary- non enumerable property
    Object.defineProperty(Person, "salary", {
        value: "Rs. 50,000",
        enumerable: false,
    });

// greeting- non enumerable function
    Object.defineProperty(Person, "greeting", {
        value: function () {
            console.log("Welcome to GFG");
        },
        enumerable: false,
    });

// arr contains all the enumerable
    // properties of Person
    let arr = Object.keys(Person);

// functionsArr contains enumerable
    // function properties of Person.
    // typeof returns an string representing
    // data type.
    // Using filter() method to filter the array
    let functionsArr = arr.filter((key) => {
        return typeof Person[key] === "function";
    });

console.log(arr);
    console.log(functionsArr);
</script>
```

## 输出

```javascript
["name", "age", "print"]
["print"]
```

## 说明

在上面的代码中，我们有一个名为 `Person` 的对象，它有 3 个数据成员（`name`、`age` 和 `salary`）和 2 个函数（`print` 和 `greeting`），其中 `salary` 数据成员和 `greeting` 函数是不可枚举的属性。

| 属性 | 类型 | 可枚举性 |
| :--- | :--- | :--- |
| `name` | 变量 | 可枚举 |
| `age` | 变量 | 可枚举 |
| `salary` | 变量 | 不可枚举 |
| `print` | 函数 | 可枚举 |
| `greeting` | 函数 | 不可枚举 |

这里的 `print` 是唯一可枚举的功能。使用 `Object.keys(Person)` 我们得到一个包含所有可枚举属性的数组，即 `["name", "age", "print"]`。

然后我们用 `Array.filter()` 方法过滤掉所有变量，使数组只有函数属性名，即 `["print"]`。