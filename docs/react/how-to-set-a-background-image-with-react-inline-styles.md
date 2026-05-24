# 如何设置具有反应内嵌样式的背景图像？

> 原文:[https://www . geeksforgeeks . org/如何设置带有内联样式的背景图像/](https://www.geeksforgeeks.org/how-to-set-a-background-image-with-react-inline-styles/)

使用***创建-反应-应用程序*** 命令创建反应项目，任务是使用反应内联样式设置背景图像。下面讨论三种方法:

**方法一:使用外部 URL 设置背景图像:**如果图像位于某处在线，那么元素的背景图像可以这样设置:

**档案名称:app . js**

## 【JavaScript】

```jsx
import React from "react";

const App = () => {
  return (
    <div style={{
      backgroundImage: 'url("https://media.geeksforgeeks.org/'+
      'wp-content/uploads/20201221222410/download3.png")',
      height: "300px", backgroundRepeat: "no-repeat"
    }}>
      <h1> HELLO </h1>
    </div>
  );
};

export default App;
```