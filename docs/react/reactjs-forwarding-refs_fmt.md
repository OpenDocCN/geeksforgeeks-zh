# React中的Ref转发

## 代码示例

```jsx
import React from 'react'

class App extends React.Component {
  constructor(props) {
    super(props)
    this.aRef = React.createRef()
  }
  render() {
    return (
      <>
        <Counter ref={this.aRef} />
        <button onClick={() => { console.log(this.aRef) }}>
          Ref
        </button>
      </>
    )
  }
}

const Counter = React.forwardRef((props, ref) => {
  class Counter extends React.Component {
    constructor(props) {
      super(props)
      this.state = {
        count: 0
      }
    }
    render() {
      return (
        <div>
          Count: {this.state.count}
          <button ref={ref} onClick={() => this.setState(
            { count: this.state.count + 1 })}>
              Increment
          </button>
        </div>
      )
    }
  }
  return <Counter />
})

export default App
```

## 说明

**说明:** 由于计数器在函数内，所以可以使用闭包访问道具和 `ref` 参数。计数器被呈现并返回。传递给计数器组件的引用被设置为按钮元素的引用属性值。计数器元素的 `ref` 属性现在将被设置为引用按钮元素。

计数器组件由应用程序组件呈现。它从创建一个引用开始。这个引用被赋值给计数器组件的引用属性作为一个值。我们已经包括了一个记录 `this.aRef` 价值的按钮。`this.aRef` 将在计数器组件中保持递增按钮的 html 按钮元素。点击参考按钮将确认它将记录 `this.aRef` 这将记录 Incr 按钮的对象。它没有记录计数器的实例，因为计数器组件将其转发给其子组件“增量”按钮。

## 运行与输出

**运行应用程序的步骤:** 从项目的根目录使用以下命令运行应用程序:

```jsx
npm start
```

**输出:** 现在打开浏览器，转到`http://localhost:3000/`，会看到如下输出:

![](img/131ecd1afbdf55dd22d1e3d05e7ff40a.png)

**参考:** [https://reactjs.org/docs/forwarding-refs.html](https://reactjs.org/docs/forwarding-refs.html)