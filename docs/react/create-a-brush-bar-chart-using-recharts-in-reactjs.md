# 使用反应堆中的充电创建刷条图

> 原文:[https://www . geeksforgeeks . org/create-a-brush-bar-chart-use-recharts-in-reactjs/](https://www.geeksforgeeks.org/create-a-brush-bar-chart-using-recharts-in-reactjs/)

**简介:Rechart JS** 是一个用于为 React JS 创建图表的库。借助 React 和 D3(数据驱动文档)，该库用于构建折线图、条形图、饼图等。

**刷条**图就是那些有大量数据点的条形图。因此，为了有效地查看和分析它们，有一个向下滑动的滑块可以帮助查看者选择一些需要显示的数据点。

**方法:**我们使用条形图和 recharts npm 包的条形图组件创建一个普通的条形图。要将其转换为画笔条形图，我们将画笔组件添加到条形图组件中。

**创建反应应用程序并安装模块:**

**步骤 1:** 使用以下命令创建一个 React 应用程序。

```jsx
npx create-react-app foldername
```

**步骤 2:** 创建项目文件夹(即文件夹名)后，使用以下命令移动到该文件夹。

```jsx
cd foldername
```

**步骤 3:** 创建 ReactJS 应用程序后，使用以下命令安装所需的模块。

```jsx
npm install --save recharts
```

**项目结构:**如下图。

![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

**示例 1:** 在本例中，我们将使用 bar chart 组件创建一个基本的条形图。为了将它转换成笔刷图表，我们将在条形图组件中添加笔刷组件。

现在在 App.js 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。

## java 描述语言

```jsx
import React from 'react';
import { BarChart, Bar, Brush, XAxis, 
    YAxis, CartesianGrid} from 'recharts';

const App = () => {

// Sample data
const data = [
  {name:'A', x:861},
  {name:'B', x:862},
  {name:'C', x:343},
  {name:'D', x:454},
  {name:'E', x:435},
  {name:'F', x:653},
  {name:'G', x:734},
  {name:'H', x:845},
  {name:'I', x:932},
  {name:'J', x:133},
  {name:'K', x:222},
  {name:'L', x:332},
  {name:'M', x:554},
  {name:'N', x:554},
  {name:'O', x:633},
  {name:'P', x:722},
  {name:'Q', x:638},
  {name:'R', x:229},
  {name:'S', x:321},
  {name:'T', x:222},
  {name:'U', x:573},
  {name:'V', x:464},
  {name:'W', x:565},
  {name:'X', x:656},
  {name:'Y', x:764},
  {name:'Z', x:348},
];

return (
  <BarChart width={500} height={700} data={data} >
      <CartesianGrid/>
      <XAxis dataKey="name" />
      <YAxis />
      <Brush dataKey="name" height={30} stroke="#8884d8" />
      <Bar dataKey="x" fill="green" />
  </BarChart>
);
}

export default App;
```