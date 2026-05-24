# 如何在 react 路由器中显示简单的路由间负载指示器？

> 原文:[https://www . geesforgeks . org/how-display-a-simple-loading-indicator-routes-in-react-router/](https://www.geeksforgeeks.org/how-to-display-a-simple-loading-indicator-between-routes-in-react-router/)

在准备显示页面时显示加载屏幕是一个很好的做法。在 react-router 中，在路由之间显示一个简单的负载指示器非常容易。

**创建反应应用程序:**

*   **步骤 1:** 使用以下命令创建一个反应应用程序:

    ```jsx
    npx create-react-app foldername
    ```

*   **步骤 2:** 在创建项目文件夹(即文件夹名**)后，使用以下命令将**移动到该文件夹:

    ```jsx
    cd foldername
    ```

**项目结构:**如下图。

![](img/15850e254fd495f11c5bffbaa542390d.png)

创建*home . js**app . js*如上图所示。

**实现:**现在在 **App.js** 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。

## App.js

```jsx
import React from "react";
import { BrowserRouter as Router, Route } from "react-router-dom";
import {useState} from "react";
import Home from'./components/Home';

function App() {
  return (
    // Create route for each page, since we 
    // have only one page. So we are defining 
    // only one route.
    <Router>
      <Route path="/" exact component={Home} />
    </Router>
  );
}

export default App;
```

## Home.js

```jsx
import React from "react";
import {useEffect, useState} from "react";

const Home = () => {

    // Set loading state to true initially
    const [loading, setLoading] = useState(true);

    useEffect(() => {
      // Loading function to load data or 
      // fake it using setTimeout;
      const loadData = async () => {

        // Wait for two second
        await new Promise((r) => setTimeout(r, 2000));

        // Toggle loading state
        setLoading((loading) => !loading);
      };

      loadData();
    }, [])

    // If page is in loading state, display 
    // loading message. Modify it as per your 
    // requirement.
    if (loading) {
        return <div>Loading....</div>
    }

    // If page is not in loading state, display page.
    else {
        return <h1>Home</h1>
    }
}

export default Home;
```

**运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:

```jsx
npm start
```

**输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:

![](img/320b930920a3df334390761c12563112.png)

结果