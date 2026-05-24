# 反应原生抽屉导航组件

> 原文:[https://www . geesforgeks . org/react-native-抽屉-导航-组件/](https://www.geeksforgeeks.org/react-native-drawer-navigation-component/)

在本文中，我们将看到如何在 react-native 中实现抽屉导航。为此，我们将使用 createDrawerNavigator 组件。基本上是 UI 面板显示导航菜单。默认情况下，它是隐藏的，但当用户从屏幕边缘刷手指时，它会出现。如今，移动应用程序由一个屏幕组成，所以在 React Native 中创建各种导航组件。我们想使用反应导航。

**语法:**

```jsx
const Drawer = createDrawerNavigator();
<Drawer.Navigator>
   <Drawer.Screen />
   <Drawer.Screen />
</Drawer.Navigator> 
```

**抽屉的打开和关闭方法:**

*   **navigation.openDrawer():** 用于打开抽屉。
*   **导航. closeDrawer():** 用于关闭抽屉。
*   **navigation . toggleawer():**用于拨动抽屉。

**现在我们从实现开始:**

*   **步骤 1:** 打开终端，通过以下命令安装 expo-cli。

    ```jsx
    npm install -g expo-cli
    ```

*   **步骤 2:** 现在通过以下命令创建一个项目。

    ```jsx
    expo init myapp
    ```

*   **第三步:**现在进入你的项目文件夹，即 myapp

    ```jsx
    cd myapp
    ```

*   **第 4 步:**现在在你的项目中安装反应导航。反应导航用于从一个页面导航到另一个页面。使用以下命令安装它。

    ```jsx
    npm install @react-navigation/native
    ```

*   **步骤 5:** 现在使用以下命令将依赖项安装到您的 react-native 项目中。

    > npm 安装反应-本地-重新激活反应-本地-手势-处理程序反应-本地-屏幕反应-本地-安全区域-上下文@反应-本地-社区/屏蔽-视图

*   **第 6 步:**现在从反应导航安装抽屉。

    ```jsx
    npm install @react-navigation/drawer
    ```

**对于反应标签导航:**这也可以用于反应原生

```jsx
https://reactnavigation.org/docs/drawer-based-navigation/
```

**项目结构:**

![](img/d1dd9b7852291ac05370c2b5d8920ad3.png)

**示例:**现在让我们实现抽屉导航。

## App.js

```jsx
import * as React from 'react';
import { Text, View } from 'react-native';
import { createDrawerNavigator } 
         from '@react-navigation/drawer';
import { NavigationContainer } 
         from '@react-navigation/native';

function HomeScreen() {
  return (
    <View style={{ flex: 1, alignItems: 'center', 
                   justifyContent: 'center' }}>
        <Text>Home page</Text>
    </View>
  );
}

function NotificationsScreen() {
  return (
    <View style={{ flex: 1, alignItems: 'center', 
                   justifyContent: 'center' }}>
      <Text>Notifications Page</Text>
    </View>
  );
}

function AboutScreen() {
  return (
    <View style={{ flex: 1, alignItems: 'center', 
                   justifyContent: 'center' }}>
      <Text>About Page</Text>
    </View>
  );
}
const Drawer = createDrawerNavigator();

export default function App() {
  return (
    <NavigationContainer>
      <Drawer.Navigator initialRouteName="Home">
        <Drawer.Screen name="Home" component={HomeScreen} />
        <Drawer.Screen name="Notifications" 
                       component={NotificationsScreen} />
        <Drawer.Screen name="About" component={AboutScreen} />
      </Drawer.Navigator>
    </NavigationContainer>
  );
}
```

使用以下命令启动服务器。

```jsx
npm run android
```

**输出:**如果你的模拟器没有自动打开，那么你需要手动打开。首先，去你的安卓工作室运行模拟器。现在再次启动服务器。

![](img/ee49eb9a98f0b20f378c48736641f519.png)

**参考:**T2】https://reactnative.dev/docs/navigation#react-navigation