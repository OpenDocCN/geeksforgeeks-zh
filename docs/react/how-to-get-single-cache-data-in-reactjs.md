# 如何在 ReactJS 中获取单缓存数据？

> 原文:[https://www . geeksforgeeks . org/如何获取单缓存数据 in-reactjs/](https://www.geeksforgeeks.org/how-to-get-single-cache-data-in-reactjs/)

我们可以在 ReactJS 中使用以下方法来获取单个缓存数据。我们可以从浏览器中获取单个缓存数据，并在需要时在我们的应用程序中使用它。缓存是一种技术帮助我们将给定资源的副本存储到我们的浏览器中，并在请求时提供给我们。

**方法:**按照以下简单步骤依次  获取单缓存 ReactJS 中的数据。我们已经创建了我们的 *getSingleCacheData* 函数，该函数采用缓存名称并从浏览器缓存中获取其数据。当我们点击按钮时，该函数被触发，数据从缓存中获取。在下面的示例中，我们试图从浏览器中获取名为缓存一的单个缓存数据，该浏览器有五个缓存，名为缓存一、缓存二、缓存三、缓存四和缓存五，如下所示:

![](img/8ac15bc68f3016d570fd085243e903ac.png)

**创建反应应用程序:**

*   **步骤 1:** 使用以下命令创建一个反应应用程序:

    ```jsx
    npx create-react-app foldername
    ```

*   **步骤 2:** 创建项目文件夹(即文件夹名**)后，使用以下命令移动到该文件夹中:**

    ```jsx
    cd foldername
    ```

**项目结构:**如下图。

![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构

**App.js:** 现在在 **App.js** 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。

## java 描述语言

```jsx
import * as React from 'react';

export default function App() {

  // Our state to store fetched cache data
  const [cacheData, setCacheData] = React.useState();

  // Function to get single cache data
  const getSingleCacheData = async (cacheName, url) => {
    if (typeof caches === 'undefined') return false;

    const cacheStorage = await caches.open(cacheName);
    const cachedResponse = await cacheStorage.match(url);

    // If no cache exists
    if (!cachedResponse || !cachedResponse.ok) {
      setCacheData('Fetched failed!')
    }

    return cachedResponse.json().then((item) => {
      setCacheData(item)
    });
  };

  // Cache Object 
  const cacheToFetch = { cacheName: 'CacheOne', url: 'https://localhost:300' }

  return (
    <div style={{ height: 500, width: '80%' }}>
      <h4>How to get single cache data in ReactJS?</h4>
      <button onClick={() => getSingleCacheData(cacheToFetch.cacheName, 
        cacheToFetch.url)} >
        Get Single Cache Data</button>  <br/>
        <h6>Cache Data is: {cacheData} </h6>
    </div>
  );
}
```

**运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:

```jsx
npm start
```

**输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:

![](img/9068d61e9993af2193cb6b62260e1cf6.png)