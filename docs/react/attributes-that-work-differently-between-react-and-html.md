# 在 React 和 HTML 之间工作方式不同的属性

> 原文:[https://www . geeksforgeeks . org/attributes-工作方式不同-反应与-html/](https://www.geeksforgeeks.org/attributes-that-work-differently-between-react-and-html/)

[**React(JSX)**](https://www.geeksforgeeks.org/react-jsx-in-depth/) 和[**HTML**](https://www.geeksforgeeks.org/html-tutorials/) 属性略有不同。比如的**类**和**等 HTML 属性在 React 中替换为**类名**和**HTML。React 和 HTML 之间有许多不同的属性。 **JSX** 中的语法与 HTML 中的语法基本相同，但有细微的差异需要注意。****

我们不能在 React 和 HTML 中使用同名的属性，因为当代码在 React 中渲染时，JSX 被翻译成 JavaScript，像**类**和的**这样的属性是 JavaScript 中的保留词，所以我们不能在 React 中使用相同的属性名。**

**1。类名:**在 HTML 中，通常使用*类*作为属性名，如下所示:

```jsx
<h1 class="gfg">Welcome to GeeksforGeeks</h1>
```

但是在 JSX，我们不能用*类*这个词。我们必须使用*类名*来代替它，它适用于所有常规的 DOM 元素，如< div >、< a >等。这是因为 JSX 被翻译成了 JavaScript，*类*是 JavaScript 中的保留词。

```jsx
<h1 className="gfg">Welcome to GeeksforGeeks</h1>
```

渲染 JSX 时，JSX *类名*属性会自动渲染为*类* 属性。

**2。自关闭标签:**一些 HTML 元素如< img >、< br >、<输入>只使用一个标签。属于既没有开始标记也没有结束标记的单个标记的标记，称为**自结束标记**。

当我们在 HTML 中编写自闭标签时，使用自闭标签是可选的。例如:

```jsx
<img src=""> and <input>
```

但是在 JSX，我们必须包含正斜杠。

```jsx
<img src="" /> and <input />
```

**3。htmlFor:** 在 HTML 中，我们经常在<标签>元素中使用 ***表示*** 属性，该标签元素被标记为标签元素的控件。

```jsx
<label for="username">Click me</label>
<input type="text" id="username">
```

但是在 React 中代替 ***为*** 属性，我们可以使用**html 为**属性。

**4。** **选择标签:**在 HTML 中，<选择>标签创建多个选项和值。我们的 react-select 组件遵循相同的约定，但是选项和值是作为道具传递的。例如:

```jsx
<select>
  <option value="GFG">GFG</option>
  <option value="OS">OS</option>
  <option value="DBMS">DBMS</option>
  <option selected value="Data Structure">
    Data Structure
  </option>
</select>
```

**注意:**数据结构选项最初是选中的，因为选中了属性。但是在 React 中，它使用根选择标记上的值属性，而不是使用选定的属性，如下例所示。

```jsx
render() {
   return (
       <select value={this.state.value} 
                  onChange={this.handleChange}>
          <option value="GFG">GFG</option>
          <option value="OS">OS</option>
          <option value="DBMS">DBMS</option>
          <option selected value="Data Structure">
               Data Structure
          </option>
        </select>
   )
}
```

**5。textarea** **标签:**在 HTML 中 **< textarea >** 标签定义了一个多行文本输入控件，如下图所示。

```jsx
<textarea>Welcome to GeeksforGeeks</textarea>
```

但是在 React <textarea>中使用了如下所示的值属性。</textarea>

```jsx
render() {
  return (
    <textarea value={this.state.value} 
        onChange={this.handleChange} />
  )
}
```

**6。在 HTML 中，我们经常使用*内置 HTML* 来设置或返回元素的 HTML 内容。**

## 超文本标记语言

```jsx
<!DOCTYPE html>
<html>
<body style="text-align: center">
    <h1 style="color:green">GeeksforGeeks</h1>
    <h2>DOM innerHTML Property</h2>
    <p id="P">A computer science portal for geeks.</p>

    <button onclick="geek()">
      Try it
    </button>
    <p id="p"></p>

    <script>
        function geek() {
            var x = document.getElementById("P").innerHTML;
            document.getElementById("p").innerHTML = x;
            document.getElementById("p").style.color = "green";
        }
    </script>
</body>
</html>
```

但是在 React 而不是 *innerHTML* 中，我们可以在浏览器 DOM 中使用*dangerouslystinnerhtml*，如下所示。

```jsx
function gfg() {
    return { __html: 'First &middot; Second' };
}; 

<div dangerouslySetInnerHTML={gfg()} />  
```