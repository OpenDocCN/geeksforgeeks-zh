# JavaScript 面试问答|第三集

> 原文: [https://www.geeksforgeeks.org/javascript-interview-questions-and-answers-set-3/](https://www.geeksforgeeks.org/javascript-interview-questions-and-answers-set-3/)

![Javascript interview questions list](img/785984b25214a9e5001c3949ea64c0c1.png)

我们已经讨论过一些基于 JavaScript 的面试问题。

*   [JavaScript 面试问答|第 1 集](https://www.geeksforgeeks.org/javascript-interview-questions-and-answers/)
*   [JavaScript 面试问答|第 2 集](https://www.geeksforgeeks.org/javascript-interview-questions-and-answers-set-2/)

以下是一些更相关的问题:

## 1. [What is the ‘Strict’ mode in JavaScript and how can it be enabled?](https://www.geeksforgeeks.org/strict-mode-javascript/)

Strict Mode 是 ECMAScript 5 中的一项新功能，它允许你将程序或函数置于“严格”的操作上下文中。这种严格上下文会阻止执行某些操作并抛出更多异常。语句 `"use strict"` 指示浏览器使用严格模式，这是 JavaScript 的一个精简且更安全的功能子集。

## 2. [如何获取 CheckBox 的状态？](https://www.geeksforgeeks.org/html-dom-input-checkbox-checked-property/)

DOM 输入复选框属性用于设置或返回复选框字段的选中状态。该属性用于反映 HTML `checked` 属性。

```
document.getElementById("GFG").checked;
```

如果复选框被选中，则返回 `true`。

## 3. [How to explain closures in JavaScript and when to use it ?](https://www.geeksforgeeks.org/closure-in-javascript/)

当一个子函数即使在其父函数已经执行完毕后，仍然保持父函数作用域的环境时，就创建了闭包。闭包是与函数相关的局部声明变量。使用闭包可以提供更好的代码控制。

```
// Explanation of closure 
function foo() { 
    var b = 1; 
    function inner() { 
        return b; 
    } 
    return inner; 
} 
var get_func_inner = foo();

console.log(get_func_inner()); 
console.log(get_func_inner()); 
console.log(get_func_inner()); 
```

## 4. [What is the difference between call() and apply() methods ?](https://www.geeksforgeeks.org/what-is-the-difference-between-call-and-apply-in-javascript/)

两种方法用于不同的情况：
*   **`call()` 方法:** 它调用一个方法，并以所有者对象作为参数。关键字 `this` 指的是函数或其所属对象的“所有者”。我们可以调用一个可以在不同对象上使用的方法。
*   **`apply()` 方法:** `apply()` 方法用于编写可以在不同对象上使用的方法。它与 `call()` 的不同之处在于它将参数作为数组传递。

## 5. [How to target a particular frame from a hyperlink in JavaScript ?](https://www.geeksforgeeks.org/how-can-a-particular-frame-be-targeted-from-a-hyperlink-in-javascript/)

这可以通过在超链接中使用 `target` 属性来实现。例如：

```
<a href="/geeksforgeeks.htm" target="newframe">New Page</a>
```

## 6. [Write the errors shown in JavaScript ?](https://www.geeksforgeeks.org/javascript-error-and-exceptional-handling-with-examples/)

JavaScript 中有三种不同类型的错误：
*   **语法错误:** 语法错误是字符或标记序列的语法错误，这些字符或标记本应按照特定编程语言的规则编写。
*   **逻辑错误:** 这是最难跟踪的错误，因为它是编码逻辑部分的错误，或者说是程序中的一个错误，导致操作不正确和异常终止。
*   **运行时错误:** 运行时错误是程序运行过程中发生的错误，也称为异常。

## 7. What is the difference between JavaScript and Jscript ?

**JavaScript:**
*   它是由网景公司开发的脚本语言。
*   它用于设计客户端和服务器端应用程序。
*   它完全独立于 Java 语言。

**Jscript:**
*   它是微软开发的脚本语言。
*   它用于为万维网设计活跃的在线内容。

## 8. What does `var myArray = [[]];` statement declares ?

在 JavaScript 中，此语句用于声明一个二维数组。

## 9. How many ways an HTML element can be accessed in a JavaScript code ?

有四种可能的方法可以在 JavaScript 代码中访问 HTML 元素：
*   **[`getElementById()` 方法:](https://www.geeksforgeeks.org/html-dom-getelementbyid-method/)** 用于通过元素的 Id 名称来获取元素。
*   **[`getElementsByClass()` 方法:](https://www.geeksforgeeks.org/html-dom-getelementsbyclassname-method/)** 用于获取所有具有给定类名的元素。
*   **[`getElementsByTagName()` 方法:](https://www.geeksforgeeks.org/html-dom-getelementsbytagname-method/)** 用于获取所有具有给定标签名的元素。
*   **[`querySelector()` 方法:](https://www.geeksforgeeks.org/html-dom-queryselector-method/)** 这个函数取 CSS 样式选择器，返回第一个选中的元素。

## 10. [What is the difference between innerHTML & innerText ?](https://www.geeksforgeeks.org/difference-between-innertext-and-innerhtml/)

`innerText` 属性设置或返回指定节点及其所有后代的纯文本内容，而 `innerHTML` 属性设置或返回元素中的纯文本或 HTML 内容。与 `innerText` 不同，`innerHTML` 允许你处理 HTML 富文本，并且不会自动编码和解码文本。

## 11. [What is an event bubbling in JavaScript ?](https://www.geeksforgeeks.org/html-bubbles-event-property/)

考虑一个元素存在于另一个元素内部，并且两者都处理一个事件的情况。当事件发生时，在冒泡过程中，最内层的元素首先处理事件，然后是外层元素，依此类推。

## 12. What will be the output of the following code ?

```
var X = { geeks : 1}; 
var Output = (function() { 
    delete X.geeks; 
    return X.geeks; 
})();

console.log(output);
```

这里的 `delete` 将删除对象的属性。`X` 是带有 `geeks` 属性的对象，它是一个自调用函数，将从对象 `X` 中删除 `geeks` 属性，因此结果将是 `undefined`。

## 13. How are JavaScript and ECMA Script related ?

JavaScript 是主要语言，它必须遵守一些规则和规范，即 ECMAScript，这些规则也为 JavaScript 语言带来了新特性。

## 14. How to hide JavaScript code from old browsers that don’t support JavaScript ?

为了向不支持 JavaScript 的旧浏览器隐藏 JavaScript 代码，你可以使用

```
<!-- before <script> tag and another //--> after </script> tag
```

所有的旧浏览器都会把它当成 HTML 的长注释。支持 JavaScript 的新浏览器会把它作为行内注释。

## 15. What will be the output of the following code ?

```
var output = (function(x) {
    delete x;
    return x;
})(0);

document.write(output);
```

输出将为 `0`。`delete` 运算符用于删除对象的属性，但 `x` 不是对象，它是一个局部变量。`delete` 运算符不影响局部变量。

## 16. In JavaScript, answer if the following expressions result in true or false.

```
"0" == 0   // true or false ? 
"" == 0   // true or false ? 
"" == "0"   // true or false ?
```

第一和第二种情况的结果将是 `true`，第三种情况的结果将是 `false`。

## 17. How to use any browser for debugging ?

通过按下 `F12`，我们可以触发任何浏览器的调试模式，并通过查看控制台来查看结果。

## 18. What is javascript Hoisting ?

当解释器运行代码时，所有变量都会被提升到其原始作用域的顶部。此方法适用于变量的声明，而不适用于变量的初始化。这被称为 JavaScript 提升。

## 19. What is the syntax of ‘Self Invoking Function’ ?

自调用函数的语法：最后一对括号包含函数表达式。

```
(function () {
    return () 
} () ;
```

## 20. [如何在另一个 JavaScript 文件中使用外部 JavaScript 文件？](https://www.geeksforgeeks.org/how-to-include-a-javascript-file-in-another-javascript-file/)

你可以用下面的代码把外部使用的 JavaScript 代码包含到另一个 JavaScript 文件中。

```
<script type="text/javascript">
    var script = document.createElement('script');
    script.src = "external javascript file";
    document.head.appendChild(script) 
</script> 
```