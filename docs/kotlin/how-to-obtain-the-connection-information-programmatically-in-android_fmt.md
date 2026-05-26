# 如何在安卓中编程获取连接信息？

> 原文：[https://www.geeksforgeeks.org/how-to-obtain-the-connection-information-programmatically-in-android/](https://www.geeksforgeeks.org/how-to-obtain-the-connection-information-programmatically-in-android/)

有时，查找网络相关的详细信息变得很有挑战性，尤其是设备的 IP 地址，这可能是通过调制解调器软件授予唯一首选项所必需的。由于多个安卓设备（三星、米、熔岩）向用户显示的信息存在差异，我们实现了一个应用程序，通过该应用程序，可以轻松获取当前网络的详细信息，并在一个地方可用。我们在程序中从设备提取的关于连接的信息或实体是：

1.  **[IP address](https://www.geeksforgeeks.org/introduction-of-classful-ip-addressing/)**：这是一个数字标签，分配给每一个使用互联网协议进行通信的网络上的连接设备。
2.  **Link speed**：是设备与同一网络上其他设备通信所能达到的最大速度（以比特每秒为单位）。
3.  **Network ID**：是主机所在的 IP 地址部分。它标识 TCP/IP 网络。
4.  **[SSID](https://www.geeksforgeeks.org/service-set-identifier-ssid-in-computer-network/) (Service Set Identifier)**：是一个由 32 个字符组成的唯一标识符，用于命名无线网络。
5.  **Hide SSID**：与 SSID 相同。隐藏 SSID 是保护网络安全的有效方法。当人们扫描附近的无线网络连接时，这将防止网络出现在可用无线网络列表中。
6.  **[BSSID](https://www.geeksforgeeks.org/introduction-of-mac-address-in-computer-network/)**：SSID 确保数据包在正确的 WLAN 中传输。即使存在重叠的无线局域网，数据包也是安全的。然而，每个 WLAN 中有多个接入点。**基本服务集标识符 (BSSID)** 标识这些接入点和相关客户端，并包含在所有无线数据包中。

不幸的是，一些实体，如 **[媒体访问控制地址](https://www.geeksforgeeks.org/introduction-of-mac-address-in-computer-network/)**，无法正确获取，这是有真正原因的。

*   MAC 地址在世界上是唯一的，这使得每个设备都是唯一的。此标签无法由用户重置，并且在出厂重置后仍然有效。因此，最好不要用它来唯一标识用户。
*   从 **Android 6.0 (API 23)** 和 **Android 9 (API 28)** 开始，无法通过第三方 API 获取本地设备（如蓝牙和 Wi-Fi）的 MAC 地址。
*   `WifiInfo.getMacAddress()` 和 `BluetoothAdapter.getDefaultAdapter().getAddress()` 都会返回 `02:00:00:00:00:00`。
*   此外，在 Android 6 到 Android 9 之间，您必须拥有以下权限才能通过蓝牙和 Wi-Fi 扫描访问附近外部设备的 MAC 地址：
*   所需方法/属性权限：`ACCESS_FINE_LOCATION` 或 `ACCESS_COARSE_LOCATION`。

## 方法

要获取安卓系统中的当前连接信息，我们将按照以下步骤操作。注意我们将使用 **Kotlin** 来实施这个项目。

### 第一步：创建新项目

要在安卓工作室创建新项目，请参考 [如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Kotlin** 作为编程语言。

### 步骤 2：使用 AndroidManifest.xml 文件

转到 **[AndroidManifest.xml](https://www.geeksforgeeks.org/application-manifest-file-android/)** 文件，添加这些使用权限：`ACCESS_WIFI_STATE`、`ACCESS_FINE_LOCATION`、`ACCESS_COARSE_LOCATION`。

```xml
<uses-permission android:name="android.permission.ACCESS_WIFI_STATE"/>
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION"/>
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION"/>
```

以下是 `AndroidManifest.xml` 文件的完整版本。

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="org.geeksforgeeks.connectioninfo">

    <!--Add these permissions-->
    <uses-permission android:name="android.permission.ACCESS_WIFI_STATE"/>
    <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION"/>
    <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION"/>

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/AppTheme">
        <activity android:name=".MainActivity">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>
```