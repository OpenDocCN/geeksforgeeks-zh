# 如何使用安卓工作室

## 创建秒表应用

> 原文: [https://www.geeksforgeeks.org/how-to-create-a-stopwatch-app-using-android-studio/](https://www.geeksforgeeks.org/how-to-create-a-stopwatch-app-using-android-studio/)

在本文中，创建了一个[安卓应用程序](https://www.geeksforgeeks.org/android-app-development-fundamentals-for-beginners/)来显示一个基本的秒表。

秒表的布局包括:

*   一个 [`TextView`](https://www.geeksforgeeks.org/textview-in-kotlin/)：显示已经过去了多少时间
*   三个按钮:
    1.  开始：启动秒表
    2.  停止：停止秒表
    3.  重置：将秒表重置为 00:00:00

**创建秒表的步骤:**

*   为秒表应用程序创建新项目
*   添加字符串资源
*   更新秒表布局代码
*   更新活动代码

下面是一个个详细的步骤:

### 1. 为秒表应用创建新项目

*   Create a new Android project for an application named “Stopwatch” with a company domain of “geeksforgeeks.org”, making the package name `org.geeksforgeeks.stopwatch`.
    [![Create a New project and select Empty Activity](img/29f06e6094262ebb2a9fff7a4ddd7ed5.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200112213123/Screenshot-at-2020-01-12-21-28-45.png)
    创建新项目并选择空活动
    [![Configure the project](img/fc00874030ee1f21b8be1bb11b1b0132.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200112213324/Screenshot-at-2020-01-12-21-30-07.png)
    配置项目
*   最低的 SDK 应该是 API 14，这样它几乎可以在所有设备上运行。
*   An empty activity called `StopwatchActivity` and a layout called `activity_stopwatch` will be created.
    [![First opening screen](img/06b0aefad6f256a5931954b88c3249be.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200112213452/Screenshot-at-2020-01-12-21-30-39.png)
    第一次打开屏幕

### 2. 添加字符串资源

我们将在秒表布局中使用三个字符串值，每个按钮的文本值一个。这些值是字符串资源，因此需要添加到 `strings.xml` 中。将以下字符串值添加到您版本的 `strings.xml`:

#### strings.xml

```java
<resources>
    <string name="app_name">GFG|Stopwatch</string>
    <string name="start">Start</string>
    <string name="stop">Stop</string>
    <string name="reset">Reset</string>
</resources>
```

### 3. 更新秒表布局代码

这里是布局的 XML。它描述了用于显示计时器的单一文本视图，以及控制秒表的三个按钮。将当前在 `activity_stopwatch.xml` 中的 XML 替换为此处显示的 XML:

#### activity_stopwatch.xml

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:background="#0F9D58"
    android:padding="16dp"
    tools:context="org.geeksforgeeks.stopwatch.StopwatchActivity">

    <TextView
        android:id="@+id/time_view"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center_horizontal"
        android:textAppearance="@android:style/TextAppearance.Large"
        android:textSize="56sp" />

    <Button
        android:id="@+id/start_button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center_horizontal"
        android:layout_marginTop="20dp"
        android:onClick="onClickStart"
        android:text="@string/start" />

    <Button
        android:id="@+id/stop_button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center_horizontal"
        android:layout_marginTop="8dp"
        android:onClick="onClickStop"
        android:text="@string/stop" />

    <Button
        android:id="@+id/reset_button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center_horizontal"
        android:layout_marginTop="8dp"
        android:onClick="onClickReset"
        android:text="@string/reset" />
</LinearLayout>
```

### 4. 活动代码如何工作

布局定义了三个按钮，我们将用它们来控制秒表。每个按钮使用其 `onClick` 属性来指定按钮被点击时应运行活动中的哪个方法。当开始按钮被点击时，`onClickStart()` 方法被调用；当停止按钮被点击时，`onClickStop()` 方法被调用；当重置按钮被点击时，`onClickReset()` 方法被调用。我们将使用这些方法来启动、停止和重置秒表。

我们将使用我们将创建的名为 `runTimer()` 的方法更新秒表。`runTimer()` 方法会每秒运行一次代码，检查秒表是否在运行，如果是，则增加秒数，并在文本视图中显示秒数。

为了帮助我们，我们将使用两个私有变量来记录秒表的状态。我们将使用名为 `seconds` 的 `int` 来跟踪秒表开始运行以来已经过去了多少秒，并使用名为 `running` 的 `boolean` 来记录秒表当前是否正在运行。

我们将从编写按钮的代码开始，然后我们将查看 `runTimer()` 方法。

*   **为按钮添加代码**
    当用户点击开始按钮时，我们将 `running` 变量设置为 `true`，这样秒表将开始计时。当用户点击停止按钮时，我们会将 `running` 设置为 `false`，使秒表停止运行。如果用户点击复位按钮，我们会将 `running` 设置为 `false`，`seconds` 到 `0`，这样秒表复位并停止运行。

*   **runTimer()方法**
    接下来我们需要做的是创建 `runTimer()` 方法。此方法将获取对布局中文本视图的引用；将 `seconds` 变量的内容格式化为小时、分钟和秒；然后在文本视图中显示结果。如果 `running` 变量设置为 `true`，将增加 `seconds` 变量。

*   **Handlers 允许你调度代码**
    一个 `Handler` 是一个 Android 类，你可以用它来调度应该在未来某个时间点运行的代码。您也可以使用它来发布需要在不同于安卓主线程的线程上运行的代码。在我们的例子中，我们将使用 `Handler` 来安排秒表代码每秒运行一次。
    要使用 `Handler`，您需要将您想要调度的代码包装在 `Runnable` 对象中，然后使用 `Handler` 的 `post()` 和 `postDelayed()` 方法来指定您希望代码何时运行。

*   **post()方法**
    `post()` 方法发布需要尽快运行的代码(通常是立即运行)。该方法采用一个参数，一个类型为 `Runnable` 的对象。Android 中的一个 `Runnable` 对象就像普通的旧 Java 中的一个 `Runnable`：一个你想要运行的作业。你把要运行的代码放在 `Runnable` 的 `run()` 方法中，`Handler` 会确保代码尽快运行。

*   **postDelayed()方法**
    `postDelayed()` 方法的工作方式类似于 `post()` 方法，只是您使用它来发布将来应该运行的代码。`postDelayed()` 方法采用两个参数：一个 `Runnable` 和一个 `long`。`Runnable` 包含您希望在其 `run()` 方法中运行的代码，`long` 指定您希望代码延迟的毫秒数。延迟后，代码将尽快运行。

以下是 `StopwatchActivity.java` 的代码:

#### StopwatchActivity.java

```java
package org.geeksforgeeks.stopwatch;

import android.app.Activity;
import android.os.Handler;
import android.view.View;
import android.os.Bundle;
import java.util.Locale;
import android.widget.TextView;

public class StopwatchActivity extends Activity {

    // Use seconds, running and wasRunning respectively
    // to record the number of seconds passed,
    // whether the stopwatch is running and
    // whether the stopwatch was running
    // before the activity was paused.

    // Number of seconds displayed
    // on the stopwatch.
    private int seconds = 0;

    // Is the stopwatch running?
    private boolean running;

    private boolean wasRunning;

    @Override
    protected void onCreate(Bundle savedInstanceState)
    {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_stopwatch);
        if (savedInstanceState != null) {

            // Get the previous state of the stopwatch
            // if the activity has been
            // destroyed and recreated.
            seconds
                = savedInstanceState
                      .getInt("seconds");
            running
                = savedInstanceState
                      .getBoolean("running");
            wasRunning
                = savedInstanceState
                      .getBoolean("wasRunning");
        }
        runTimer();
    }
```

```java
// Save the state of the stopwatch
// if it's about to be destroyed.
@Override
public void onSaveInstanceState(Bundle savedInstanceState) {
    savedInstanceState.putInt("seconds", seconds);
    savedInstanceState.putBoolean("running", running);
    savedInstanceState.putBoolean("wasRunning", wasRunning);
}

// If the activity is paused,
// stop the stopwatch.
@Override
protected void onPause() {
    super.onPause();
    wasRunning = running;
    running = false;
}

// If the activity is resumed,
// start the stopwatch
// again if it was running previously.
@Override
protected void onResume() {
    super.onResume();
    if (wasRunning) {
        running = true;
    }
}

// Start the stopwatch running
// when the Start button is clicked.
// Below method gets called
// when the Start button is clicked.
public void onClickStart(View view) {
    running = true;
}

// Stop the stopwatch running
// when the Stop button is clicked.
// Below method gets called
// when the Stop button is clicked.
public void onClickStop(View view) {
    running = false;
}

// Reset the stopwatch when
// the Reset button is clicked.
// Below method gets called
// when the Reset button is clicked.
public void onClickReset(View view) {
    running = false;
    seconds = 0;
}

// Sets the number of seconds on the timer.
// The `runTimer()` method uses a `Handler`
// to increment the seconds and
// update the text view.
private void runTimer() {
    // Get the text view.
    final TextView timeView = (TextView) findViewById(R.id.time_view);

    // Creates a new `Handler`
    final Handler handler = new Handler();

    // Call the `post()` method,
    // passing in a new `Runnable`.
    // The `post()` method processes
    // code without a delay,
    // so the code in the `Runnable`
    // will run almost immediately.
    handler.post(new Runnable() {
        @Override
        public void run() {
            int hours = seconds / 3600;
            int minutes = (seconds % 3600) / 60;
            int secs = seconds % 60;

            // Format the seconds into hours, minutes,
            // and seconds.
            String time = String.format(Locale.getDefault(), "%d:%02d:%02d", hours, minutes, secs);

            // Set the text view text.
            timeView.setText(time);

            // If `running` is true, increment the
            // `seconds` variable.
            if (running) {
                seconds++;
            }

            // Post the code again
            // with a delay of 1 second.
            handler.postDelayed(this, 1000);
        }
    });
}
```

[![秒表应用程序的输出。](img/36f9f16d2b62da032376c5c8c282d7e5.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200113171436/Screenshot_2020-01-13-17-12-28-264_org.geeksforgeeks.stopwatch.jpg)