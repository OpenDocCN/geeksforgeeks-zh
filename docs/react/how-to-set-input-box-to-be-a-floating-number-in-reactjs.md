# 如何在 ReactJS 中将输入框设置为浮点数？

> 原文:[https://www . geesforgeks . org/如何将输入框设置为 reactjs 中的浮点数/](https://www.geeksforgeeks.org/how-to-set-input-box-to-be-a-floating-number-in-reactjs/)

如果我们想将输入框设置为**浮点数**，那么我们可以使用**输入标签**的**步长属性**。我们必须将输入类型设置为要增加/减少浮点数的数量和步长值。我们还可以设置 **min** 和 **max** 属性，使数值在最小值后不减少，在最大值后不增加。

**创建反应应用程序:**

*   **步骤 1:** 使用以下命令创建一个反应应用程序:

    ```jsx
    npx create-react-app foldername
    ```

*   **步骤 2:** 创建项目文件夹(即文件夹名)后，使用以下命令移动到该文件夹:

    ```jsx
    cd foldername
    ```

**项目结构:**如下图。

![](img/7741c5c80ef4f444b97fd777e206a1c3.png)

**示例:**

## App.js

```jsx
import React from 'react'

class App extends React.Component {

  state = {
      value: 10
  }

  onValueChange = (event) => {
      this.setState({value:event.target.value})
  }

  render () {
    return (
      <td>
        <label> Floating Number: </label>
            <input
                type='number'
                step="0.1"
                min='0'
                max='20'
                value={this.state.value}
                onChange= {(event) => this.onValueChange(event)}
              />
      </td>
    )
  }

}

export default App;
```

**输出:**

<video class="wp-video-shortcode" id="video-587069-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210408200351/input-box.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210408200351/input-box.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210408200351/input-box.mp4)</video>