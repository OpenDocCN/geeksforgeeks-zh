# 带演示应用的安卓意图过滤器

> 原文: [https://www.geeksforgeeks.org/intent-filter-in-android-with-demo-app/](https://www.geeksforgeeks.org/intent-filter-in-android-with-demo-app/)

[意图](https://www.geeksforgeks.org/what-is-intent-in-android/)是一个消息对象，它告诉要执行哪种操作。意图最重要的用途是活动的启动。意图有助于组件之间的通信。

> **注:** App 组件是 App 的基本构件。

## 意图的基本用例

### 开始活动

一个活动代表应用程序中的单个屏幕，绕过意图实例，我们可以开始一个活动。

**例:**

```kt
var intent = Intent(this, SecondActivity::class.java)
startIntent(intent)
```

您可以使用`putExtra()`添加额外的信息。

### 启动服务

服务是在没有用户界面的情况下在后台执行操作的组件，也称为后台进程。

### 发送广播

广播是任何应用程序都能接收到的消息。在安卓系统中，该系统提供各种广播系统事件，如设备开始充电、禁用或启用飞机模式等。

## 意图类型

有两种意图

1.  **显式意图:** 显式意图可以执行由代码设置的特定应用程序操作，如更改活动，在显式意图中，用户知道所有的事情，如单击按钮后将启动哪个活动，显式意图用于应用程序内部的通信。
2.  **隐式意图:** 隐式意图不像显式意图那样命名特定组件，而是声明要执行的一般操作，这允许来自另一个应用程序的组件进行处理。

例如: 当您轻按任何应用程序中的共享按钮时，您可以看到 Gmail、蓝牙和其他共享应用程序选项。

## 意图过滤器

*   隐式意图使用意图过滤器来服务用户请求。
*   意图过滤器指定活动、服务或广播接收器可以响应的意图类型。
*   意图过滤器在安卓清单文件中声明。
*   意图过滤器必须包含

**示例:**

```xml
<intent-filter
  android:icon="drawable resource"
  android:label="string resource"
  android:priority="integer" >
   . . .
</intent-filter>
```

大部分意图过滤器都是通过其

1.  `<action>`
2.  `<category>` 和
3.  `<data>`

### 1. `<action>`

**语法:**

```xml
<action android:name="string" />
```

向意图过滤器添加操作。一个`<intent-filter>`元素必须包含一个或多个`<action>`元素。如果意图过滤器中没有`<action>`元素，则过滤器不接受任何意图对象。

**常见动作示例:**

*   **ACTION_VIEW:** 当您有一些活动要向用户显示信息时，例如在图库应用程序中显示图像或在地图应用程序中显示要查看的地址。
*   **ACTION_SEND:** 当您有一些数据用户可以通过另一个应用程序（如电子邮件应用程序或社交分享应用程序）共享时，您应该在`startActivity()`中使用此操作。

### 2. `<category>`

**语法:**

```xml
<category android:name="string" />
```