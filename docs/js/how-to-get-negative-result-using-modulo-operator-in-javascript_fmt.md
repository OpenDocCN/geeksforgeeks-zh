# 如何在 JavaScript 中使用模运算符得到否定结果？

> 原文: [https://www.geeksforgeeks.org/how-to-get-negative-result-using-modulo-operator-in-javascript/](https://www.geeksforgeeks.org/how-to-get-negative-result-using-modulo-operator-in-javascript/)

JavaScript 中的 `%` [(模)](https://en.wikipedia.org/wiki/Modulo_operation) 运算符给出了两个数相除后的余数。`%(模)` 和 `余数` 运算符有区别。当余数或 `%` 模是对正数计算时，两者的行为相似，但当使用负数时，两者的行为不同。
JavaScript 的 `%(模)` 的行为类似于 `余数` 运算并给出余数，由于余数为负，因此余数也为负。
让我们一起来了解和比较 `%` 模和余数运算结果的清晰性。

### 模运算符示例:

```javascript
For Positive Numbers:
Input: a = 21, b = 4
Output: 1
Explanation: 
modulo = 21 % 4
modulo = 21 - 4 * 5
modulo = 21 - 20 = 1 
Other Explanation:
The number 21 can be written in terms of 4 as
21 = 5 * 4 + 1
So, here '1' is the result.

For Negative Numbers:
Input: a = -23, b = 4
Output: 1
Explanation: 
modulo = -23 % 4
modulo = -23 + 4 * 6
modulo = -23 + 24 = 1
Other Explanation:
The number -23 can be written in terms of 4 as
-23 = (-6) * 4 + 1
So, here '1' is the result.
```

### 余数运算符示例:

```javascript
Remainder operator uses the formula:
Remainder = a - (a / b) * b

Note: Result of (a / b) is first converted into Integer Value.

For Positive Numbers:
Input: a = 21, b = 4
Output: 1
Explanation: 
Remainder = 21 - (21 / 4) * 4 
Remainder = 21 - 5 * 4   
Remainder = 21 - 20 = 1

For Negative Numbers:
Input: a = -23, b = 4
Output: -3
Explanation: 
Remainder = -23 -( -23 / 4) * 4
Remainder = -23 -(-5) * 4
Remainder = -23 + 20 = -3
```

因此，从上面的比较中，很明显余数和模运算是不同的。JavaScript `%` 模(模)运算符只不过是余数运算符，这就是它对负数给出负结果的原因。

### 使用 Number.prototype 创建 mod 函数

`Number.prototype` 构造函数允许向 JavaScript 数字添加新的属性和方法，使得所有数字默认都能获得此属性并可以访问该方法。
因此，我们将使用 `Number.prototype` 来创建一个 mod 函数，该函数将返回两个数字的模。

#### 语法:

```javascript
Number.prototype.mod = function(a) {
    // Calculate
    return this % a;
}
```

下面的程序说明了 JavaScript 中的 `%` 模运算符:

#### 例 1:

本例使用模运算符(%)进行运算。

```javascript
<script>
// JavaScript code to perform modulo (%)
// operation on positive numbers

// mod() function
Number.prototype.mod = function(a) {
    // Calculate
    return this % a;
}

// Driver code
var x = 21;
var b = 4;

// Call mod() function
var result = x.mod(b);

// Print result
document.write("The outcome is: " + result);
</script>
```

#### 输出:

```javascript
The outcome is: 1
```

#### 例 2:

```javascript
<script>
// JavaScript code to perform modulo (%)
// operation on negative numbers

// Use mod() function
Number.prototype.mod = function(a) {
    // Calculate
    return this % a;
}

// Driver code
var x = -21;
var b = 4;

// Call mod()
var result = x.mod(b);

// Print result
document.write("The outcome is: " + result);
</script>
```

#### 输出:

```javascript
The outcome is: -1
```

因此，很清楚为什么 JavaScript `%` module 给出了否定的结果。

### 修改 JavaScript %(模) 使其作为模运算符工作

要执行模运算符 (%) 像真正的模运算而不是计算余数。我们将使用以下公式。
假设数字是 a 和 b，然后计算 `mod = a % b`

#### 语法:

```javascript
Number.prototype.mod = function(b) {
    // Calculate
    return ((this % b) + b) % b;
}
```

在上面的公式中，我们使用模属性 `(a+b) mod c = (a mod c + b mod c) mod c` 从余数计算模。

下面的程序说明了上述方法:

#### 示例:

```javascript
<script>
// JavaScript implementation of above approach

// Use mod() function
Number.prototype.mod = function(b) {
    // Calculate
    return ((this % b) + b) % b;
}

// Driver code
var x = -21;
var b = 4;

// Call mod() function
var result = x.mod(b);

// Print result
document.write("The outcome is: " + result + "</br>");

x = -33;
b = 5;

// Call mod() function
result = x.mod(b);

// Print result
document.write("The outcome is: " + result);
</script>
```

#### 输出:

```javascript
The outcome is: 3
The outcome is: 2
```