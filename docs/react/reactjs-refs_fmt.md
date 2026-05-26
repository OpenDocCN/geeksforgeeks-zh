## java 描述语言

### 示例1：不使用refs

```jsx
// without refs
class App extends React.Component {
  constructor(){
   super();
   this.state = { sayings: ""};
   }
  update(e){
   this.setState({ sayings: e.target.value});
  }
  render(){
   return (
    <div>
     Mukul Says <input type="text" onChange = {this.update.bind(this)}/>
    <br/>
    <em>{this.state.sayings}</em>
   </div>
  );
 }
}
ReactDOM.render(< App />, document.getElementById('root'));
```

**输出:**

![](img/014db218ea33bcc4edb43b61f1c9ab82.png)

在上面的例子中，我们利用事件`e`的目标值，来得到Mukul所说的值。上述输出也可以通过使用参考文献来实现。

### 示例2：使用refs

```jsx
// using refs
class App extends React.Component {
 constructor(){
  super();
  this.state = { sayings: ""};
 }
 update(e){
  this.setState({ sayings: this.refs.anything.value});
 }
 render(){
  return (
   <div>
    Mukul Says <input type="text" ref="anything"
      onChange = {this.update.bind(this)}/>
   <br/>
   <em>{this.state.sayings}</em>
  </div>
  );
 }
}
 ReactDOM.render(< App />, document.getElementById('root'));
```

**输出:**

![](img/1ebd5b789833d5bbc1ec7d58dd4a5421.png)

在上面我们利用了React提供的`refs`，它们也可以用来在内部添加回调函数，这在很多情况下是有帮助的。

### 示例3：在ref内部使用回调

```jsx
// callback used inside ref
class App extends React.Component {
  constructor(){
   super();
   this.state = { sayings: ""};
  }
  update(e){
   this.setState({ sayings: this.a.value});
  }
  render(){
   return (
    <div>
     Mukul Says <input type="text"
     ref={(call_back) => {this.a = call_back}} onChange =
     {this.update.bind(this)}/>
   <br/>
   <em>{this.state.sayings}</em>
   </div>
  );
 }
}
ReactDOM.render(< App />, document.getElementById('root'));
```

**输出:**

![](img/b73ebecca15c4e0aafebb6fb4d0bd6fd.png)

**何时使用参考文献**

*   使用第三方库时很有帮助。
*   对动画很有帮助。

**何时不使用参考文献**

*   不应与功能组件一起使用，因为它们没有实例。
*   不要用在可以声明的事情上。