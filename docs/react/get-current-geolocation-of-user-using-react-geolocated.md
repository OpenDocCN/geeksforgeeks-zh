# 使用反应-地理定位

获取用户的当前地理位置

> 原文:[https://www . geeksforgeeks . org/get-current-geolocation-of-user-use-react-geolocated/](https://www.geeksforgeeks.org/get-current-geolocation-of-user-using-react-geolocated/)

在某些情况下，应用程序需要访问用户的当前位置属性。位置属性包括纬度、经度以及关于用户当前位置的更多信息。从位置属性，用户可以知道用户的当前地理位置。

该应用程序可以根据当前的地理位置向用户提供特定的服务。例如，Wheather 应用程序使用 [OpenWeatherMap API](https://www.geeksforgeeks.org/python-find-current-weather-of-any-city-using-openweathermap-api/) 显示用户当前地理位置的当前天气。带有地图集成的应用程序可以使用[谷歌地图应用编程接口](https://www.geeksforgeeks.org/python-get-google-map-image-specified-location-using-google-static-maps-api/)在谷歌地图上显示用户的当前位置。

在本教程中，我们将学习通过使用地理定位包来访问 react js 中用户的当前地理定位属性。通过使用 react-geolocated 包，用户可以获得以下详细信息。

*   纬度
*   经度
*   海拔
*   准确(性)
*   速度

用户需要首先在他们的本地计算机上设置 react 项目环境。

**创建新的反应项目**

**第一步:**要创建一个新的 react 应用程序，运行下面的命令到你的终端。

```jsx
npx create-react-app testapp
```

**步骤 2:** 现在，使用下面的命令在项目目录中移动。

```jsx
cd testapp
```

**项目目录:**应该如下图所示。

![](img/7d6b5271640f4fd75c9ea607691d3798.png)

**步骤 3:** 通过在终端中运行下面的命令，在项目目录中安装 react-Geolocated 包。

```jsx
npm install react-geolocated --save
```

现在，我们准备使用 react-geolocated 获取用户的地理位置。

**语法:**

```jsx
1\. Check if browser is supporting geolcated or not
   if(this.props.isGeolocationAvailable) {

     a. check if location in browser is enabled or not
        if(this.props.isGeolocationEnabled){

         i. check if coordinates of current location is 
             available or not
            if(this.props.coords){
            render the coordinates of current location.
            }  
        }     
    }
```

**示例:**现在，编辑 app.js 文件，并将下面的代码复制/粘贴到其中。

在这个文件中，我们将导入 react-geolocated 包并打印当前位置的坐标。我们将把 App 组件与减速器功能*地理定位()*绑定。地理定位的 Reducer 函数在应用程序组件渲染时将道具分配给它。

## App.js

```jsx
import React, { Component } from "react";

// Importing geolocated reducer function
import { geolocated } from "react-geolocated";

class App extends Component {
  render() {

    // Check geolocation supported in
    // browser or not
    return this.props.isGeolocationAvailable ? (

      // Check location is enable in
      // browser or not
      this.props.isGeolocationEnabled ? (

        // Check coordinates of current
        // location is available or not
        this.props.coords ? (
          <div>
            <h1 style={{ color: "green" }}>GeeksForGeeks</h1>
            <h3 style={{ color: "red" }}>
              Current latitude and longitude of the user is
            </h3>
            <ul>
              <li>latitude - {this.props.coords.latitude}</li>
              <li>longitude - {this.props.coords.longitude}</li>
            </ul>
          </div>
        ) : (
          <h1>Getting the location data</h1>
        )
      ) : (
        <h1>Please enable location on your browser</h1>
      )
    ) : (
      <h1>Please, update your or change the browser </h1>
    );
  }
}

// Binding geolocated() reducer function to
// App component, while exporting it
export default geolocated()(App);
```

**运行步骤:**要运行项目，请在项目目录中向您的终端输入以下命令。

```jsx
npm start
```

**输出:**

![](img/18aa7b69d06152dd06e352fdb8945ead.png)

**支持的浏览器:**只有特定版本以下的浏览器支持 react-geolocated。

*   铬≥ 5
*   Firefox ≥ 3.5
*   Internet Explorer ≥ 9
*   Opera ≥ 10.60
*   行程≥ 5

**参考:**T2】https://www.npmjs.com/package/react-geolocated