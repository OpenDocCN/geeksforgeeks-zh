# 脸书观众网(FAN)有奖视频广告如何融入安卓？

> 原文：[https://www.geeksforgeeks.org/how-to-integrate-facebook-audience-network-fan-rewarded-video-ads-in-android/](https://www.geeksforgeeks.org/how-to-integrate-facebook-audience-network-fan-rewarded-video-ads-in-android/)

为了从[安卓](https://www.geeksforgeeks.org/android-app-development-fundamentals-for-beginners/)应用或游戏中赚钱，有很多方式，如应用内购买、赞助、广告等。但是还有一种从安卓应用中赚钱的流行方法是整合第三方广告，例如名为[脸书观众网络](https://developers.facebook.com/products/audience-network/)。脸书观众网旨在帮助用户体验货币化。通过使用高价值的格式、高质量的广告、和创新的出版商工具，它有助于在保持人们参与的同时发展业务。

## 为什么是脸书观众网？

*   脸书观众网是谷歌广告业务货币化安卓或 IOS 应用的最佳选择之一。
*   最低支付额为 `$100`
*   广泛的广告格式
*   最大填充率
*   高 `eCPM` (每千分之一有效成本)
*   优质广告
*   个性化广告

## 脸书观众网业态

在脸书观众网络中，主要有五种灵活、高性能的格式

*   **原生：** 你设计的适合应用的广告，无缝衔接
*   **间隙：** 吸引眼球并成为体验一部分的全屏广告。
*   **横幅：** 传统业态多种摆放。
*   **奖励视频：** 一款沉浸式、用户发起的视频广告，奖励用户观看。
*   **Playables：** 先试后买的广告体验，允许用户在安装前预览游戏。

在本文中，让我们将**脸书观众网络奖励视频广告**整合到安卓应用中。

### 有奖视频

*   有奖视频广告是覆盖应用整个 UI 的全屏广告。奖励视频广告的 `eCPM` (每千分之一的有效成本)相对高于`横幅`和`间隙`广告，也导致**更高的点击率**(点击率)，从而从该应用中获得更多收益。
*   当用户从头到尾观看奖励视频时，他们会获得应用内奖励。

![FAN rewared video](img/40e206a50ddfaade6279b63d8405ea23.png)

## 方法

### 第一步：创建新的项目

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目。](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)注意选择 `Java` 作为语言，虽然我们要用 Java 语言实现这个项目。

### 第二步：去编码区之前先做一些前置任务

*   转到`应用程序->res->values->colors.xml`文件，为应用程序设置颜色。

```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <color name="colorPrimary">#0F9D58</color>
    <color name="colorPrimaryDark">#0F9D58</color>
    <color name="colorAccent">#05af9b</color>
</resources>
```

*   转到`Gradle Scripts->build.gradle (Module: app)`部分，导入以下依赖项，点击上方弹出的“**立即同步**”。

```gradle
implementation 'com.facebook.android:audience-network-sdk:5.+'
```

*   转到`app -> manifests -> AndroidManifest.xml`部分，允许“[互联网许可](https://www.geeksforgeeks.org/android-how-to-request-permissions-in-android-application/)”。

### 第三步：设计 UI

在 `activity_main.xml` 文件中只添加一个`按钮`，这样每当用户点击按钮时，奖励视频广告就会播放。

```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <!-- Button to Show Rewarded Video Ad By Clicking it -->
    <Button
        android:id="@+id/showVideoBtn"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true"
        android:layout_margin="8dp"
        android:background="@color/colorPrimary"
        android:padding="16dp"
        android:text="Show Rewarded Video Ad"
        android:textColor="#ffff"
        android:textSize="20dp" />

</RelativeLayout>
```

### 第四步：使用 `MainActivity.java` 文件

*   在类中打开 `MainActivity.java` 文件，首先创建 `Button` 类的对象。

```java
//创建按钮类的对象
Button showVideoAdBtn;
```

*   现在在 `onCreate()` 方法中，将这些对象与 `activity_main.xml` 文件中给出的它们各自的标识链接起来。

```java
//将这些对象与我们在 activity_main.xml 文件中给出的它们各自的 id 链接起来
showVideoAdBtn = (Button) findViewById(R.id.showVideoBtn);
```

*   现在在 `onCreate()` 方法里面，初始化**脸书观众网 SDK**

```java
//初始化受众网络软件开发工具包
AudienceNetworkAds.initialize(this);
```

*   在 `MainActivity.java` 类中创建一个 `RewardedVideoAd` 的对象

```java
//创建 RewardedVideoAd 的对象
private RewardedVideoAd fbRewardedVideoAd;
```

*   接下来在类中创建一个私有的 `void loadRewardedVideoAd()` 方法，然后定义它。

```java
private void loadRewardedVideoAd()
{
    //正在初始化 RewardedVideoAd 对象
    //RewardedVideoAd 构造函数接受 2 个参数
    // 1) 上下文
    // 2) 放置标识
    fbRewardedVideoAd = new RewardedVideoAd(this, "YOUR_PLACEMENT_ID");
    //加载 Ad
    fbRewardedVideoAd.loadAd();
}
```

*   初始化软件开发工具包后，调用 `onCreate()` 方法中的 `loadRewardedVideoAd()`

> **注**：将 `YOUR_PLACEMENT_ID` 替换为自己的 placement id，展示真实广告。

*   接下来在类中创建一个 `void showRewardedVideoAd()` 方法，我们稍后会调用这个方法来显示 ad。

```java
public void showRewardedVideoAd()
{
    //检查广告是否已加载
    if(fbRewardedVideoAd.isAdLoaded())
    {
        //显示视频广告
        fbRewardedVideoAd.show();
    }
    else
    {
        //如果未加载视频广告，则加载视频广告
        fbRewardedVideoAd.loadAd();
    }
}
```

*   接下来就是当用户点击 show ad 按钮时，调用 `showRewardedVideoAd()` 方法。
*   现在在 `onCreate()` 方法中，为按钮创建一个`点击监听器`，调用 `showRewardedVideoAd()`

```java
//单击监听器显示奖励视频广告
showVideoAdBtn.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View view) {
        showRewardedVideoAd();
    }
});
```

*   现在我们为奖励视频广告添加 `RewardedVideoAdListener`，这样用户就知道广告的状态了。
*   要添加 `RewardedVideoAdListener`，打开 `loadRewardedVideoAd()` 方法，在 `fbRewardedVideoAd.loadAd()` 前添加以下代码；

```java
// RewardedVideoAdListener
fbRewardedVideoAd.setAdListener(new RewardedVideoAdListener() {
    @Override
    public void onError(Ad ad, AdError error) {
        //显示祝酒词
        Toast.makeText(MainActivity.this, "onError", Toast.LENGTH_SHORT).show();
    }

    @Override
    public void onAdLoaded(Ad ad) {
        //显示祝酒词
        Toast.makeText(MainActivity.this, "onAdLoaded", Toast.LENGTH_SHORT).show();
    }

    @Override
    public void onAdClicked(Ad ad) {
        //显示祝酒词
        Toast.makeText(MainActivity.this, "onAdClicked", Toast.LENGTH_SHORT).show();
    }

    @Override
    public void onLoggingImpression(Ad ad) {
        //显示祝酒词
        Toast.makeText(MainActivity.this, "onLoggingImpression", Toast.LENGTH_SHORT).show();
    }

    @Override
    public void onRewardedVideoCompleted() {
        //显示祝酒词
        Toast.makeText(MainActivity.this, "onRewardedVideoCompleted", Toast.LENGTH_SHORT).show();
    }

    @Override
    public void onRewardedVideoClosed() {
        //显示祝酒词
        Toast.makeText(MainActivity.this, "onRewardedVideoClosed", Toast.LENGTH_SHORT).show();
    }
});
```

*   而在 `RewardedVideoAdListener` 内，Override 方法会显示一条[祝酒信息](https://www.geeksforgeeks.org/android-what-is-toast-and-how-to-use-it-with-examples/)，让用户知道广告的状态。以下是 `MainActivity.java` 文件的完整代码。

## MainActivity.java

```java
package org.geeksforgeeks.project;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.Toast;
import androidx.appcompat.app.AppCompatActivity;
import com.facebook.ads.Ad;
import com.facebook.ads.AdError;
import com.facebook.ads.AudienceNetworkAds;
import com.facebook.ads.RewardedVideoAd;
import com.facebook.ads.RewardedVideoAdListener;

public class MainActivity extends AppCompatActivity {

    // Creating a object of Button class
    Button showVideoAdBtn;

    @Override
    protected void onCreate(Bundle savedInstanceState)
    {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // link those objects with their respective id's
        // that we have given in activity_main.xml file
        showVideoAdBtn
            = (Button)findViewById(R.id.showVideoBtn);

        // initializing the Audience Network SDK
        AudienceNetworkAds.initialize(this);

        // initializing and loading rewarded video ad
        loadRewardedVideoAd();

        // click listener to show Rewarded Video  Ad
        showVideoAdBtn.setOnClickListener(
            new View.OnClickListener() {
                @Override public void onClick(View view)
                {
                    showRewardedVideoAd();
                }
            });
    }

    // creating object of RewardedVideoAd
    private RewardedVideoAd fbRewardedVideoAd;

    void loadRewardedVideoAd()
    {
        // initializing RewardedVideoAd Object
        // RewardedVideoAd  Constructor Takes 2 Arguments
        // 1)Context
        // 2)Placement Id
        fbRewardedVideoAd = new RewardedVideoAd(
            this, "YOUR_PLACEMENT_ID");

        // RewardedVideoAd AdListener
        fbRewardedVideoAd.setAdListener(
            new RewardedVideoAdListener() {
                @Override
                public void onError(Ad ad, AdError error)
                {
                    // Showing Toast Message
                    Toast
                        .makeText(MainActivity.this,
                                  "onError",
                                  Toast.LENGTH_SHORT)
                        .show();
                }

                @Override public void onAdLoaded(Ad ad)
                {
                    // Showing Toast Message
                    Toast
                        .makeText(MainActivity.this,
                                  "onAdLoaded",
                                  Toast.LENGTH_SHORT)
                        .show();
                }

                @Override public void onAdClicked(Ad ad)
                {
                    // Showing Toast Message
                    Toast
                        .makeText(MainActivity.this,
                                  "onAdClicked",
                                  Toast.LENGTH_SHORT)
                        .show();
                }

                @Override
                public void onLoggingImpression(Ad ad)
                {
                    // Showing Toast Message
                    Toast
                        .makeText(MainActivity.this,
                                  "onLoggingImpression",
                                  Toast.LENGTH_SHORT)
                        .show();
                }

                @Override
                public void onRewardedVideoCompleted()
                {
                    // Showing Toast Message
                    Toast
                        .makeText(
                            MainActivity.this,
                            "onRewardedVideoCompleted",
                            Toast.LENGTH_SHORT)
                        .show();
                }

                @Override
                public void onRewardedVideoClosed()
                {
                    // Showing Toast Message
                    Toast
                        .makeText(MainActivity.this,
                                  "onRewardedVideoClosed",
                                  Toast.LENGTH_SHORT)
                        .show();
                }
            });

        // loading Ad
        fbRewardedVideoAd.loadAd();
    }

    public void showRewardedVideoAd()
    {
        // Checking If Ad is Loaded
        // or Not
        if (fbRewardedVideoAd.isAdLoaded()) {
            // showing Video Ad
            fbRewardedVideoAd.show();
        }
        else {
            // Loading Video Ad If it  is Not Loaded
            fbRewardedVideoAd.loadAd();
        }
    }
}
```

## 输出:在仿真器上运行

<video class="wp-video-shortcode" id="video-474093-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200825100305/Facebook-Audience-Network-Rewarded-Video-Ad-Demo-.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200825100305/Facebook-Audience-Network-Rewarded-Video-Ad-Demo-.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200825100305/Facebook-Audience-Network-Rewarded-Video-Ad-Demo-.mp4)</video>