# 如何在 React-Native App 中创建按钮？

> 原文:[https://www . geesforgeks . org/how-create-button-in-react-native-app/](https://www.geeksforgeeks.org/how-to-create-button-in-react-native-app/)

在本文中，我们将看到如何在 react-native 中创建按钮，它们的语法，以及 react native 中可用的不同类型的按钮。

在 react native 中创建一个按钮非常简单。首先，我们必须从 React Native 导入按钮组件。

```jsx
import { Button } from 'react-native'
```

如果您不熟悉 react native 的组件，那么您可以查看 [React Native](https://www.geeksforgeeks.org/introduction-react-native/) 上的介绍性文章

**语法:**

```jsx
import React, { Component } from 'react'
import { Button } from 'react-native'
const Test = () => {
    return(
        <Button 
            // Define Button property
        />
    )
}
export default Test
```

上面的语法显示了按钮是如何在 react native 中使用的。它包括用一个按钮元素定义一个 XML 标签，现在根据我们的需求，可以为一个按钮定义不同的属性。

**反应原生按钮的类型**按钮有五种类型，如下所示:

1.  **基本类型:**这些属于基本类别，可以是以下类型:
    *   **按钮:**用于定义点击按钮。
    *   **提交:**此类按钮与表单一起使用，用于提交详细信息。
    *   **复位:**用于点击清除字段内容。
2.  **扁平按钮:**有无背景色的风格。要在 react 中创建平面按钮，请将 CSS 类设置为 e-flat。
3.  **轮廓按钮:**这种类型的按钮包含一个透明背景的边框。要创建这种类型的按钮，请将 CSS 类设置为电子大纲。
4.  **圆形按钮:**此按钮为圆形。要创建圆形按钮，请将 CSS 类设置为 e-round。
5.  **切换按钮:**切换按钮是状态可以改变的按钮。让我们考虑一个播放和暂停按钮的例子。单击此按钮时，其状态会改变，并且在再次单击后，它会恢复其原始状态。该状态改变功能通过按钮的点击事件来实现。要创建切换，我们需要将 isToggle 属性设置为 true。

**创建按钮的步骤:**

*   编写并导出代码来制作按钮，并将其放入可重用的组件中。
*   将该组件导入 App.js 文件。
*   将该按钮与任何其他组件一样放入您的文件中。
*   在按钮文件中添加一些样式。

完整的代码来创建一个反应原生按钮:

```jsx
import React from 'react';

// Import the essential components from react-native
import {
    StyleSheet, Button, View, SafeAreaView,
    Text, Alert
} from 'react-native';

// Function for creating button
export default function App() {
    return (
        <View style={styles.container}>

            // Create a button
            <Button

                // Some properties given to Button
                title="Geeks"
                onPress={() => Alert.alert(
                    'Its GeeksforGeeks !')}
            />
        </View>
    );
}

// Some styles given to button
const styles = StyleSheet.create({
    container: {
        flex: 1,
        backgroundColor: '#71EC4C',
        alignItems: 'center',
        justifyContent: 'center',
    },
});
```

**输出:**

*   **之前点击按钮:**
    ![](img/8bf5421881304944c53f64eddc1eb427.png)
*   **点击按钮后:**
    ![](img/ea394787fcbb1f5d18ca96941666a9ff.png)

**运行项目的步骤:**

*   转到项目文件夹，在终端上键入以下命令。以下命令创建您的项目。

    ```jsx
    react-native init MyAppName
    ```

*   选择 App.js 文件，粘贴项目代码(上面给出的项目完整代码)，然后保存文件。
*   启动模拟器来运行项目。以下命令将启动模拟器。

    ```jsx
    emulator -avd MyAVD
    ```

*   现在，使用以下命令运行项目。

    ```jsx
    react-native run-android
    ```

**运行项目的另一种方法:**

*   打开终端并跳转到您的项目文件夹。

    ```jsx
    cd ProjectName
    ```

*   要在 Expo 上运行项目，请在终端中键入以下命令。

    ```jsx
    expo start
    ```

*   在手机的世博应用中扫描世博应用条形码。