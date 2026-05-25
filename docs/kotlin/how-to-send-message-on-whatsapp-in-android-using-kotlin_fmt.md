# 如何使用 Kotlin 在安卓 WhatsApp 上发送消息

> 原文: [https://www.geeksforgeeks.org/how-to-send-message-on-whatsapp-in-android-using-kotlin/](https://www.geeksforgeeks.org/how-to-send-message-on-whatsapp-in-android-using-kotlin/)

Whatsapp 是最受欢迎的消息应用之一。许多安卓应用程序需要直接从他们的应用程序向 WhatsApp 共享一些消息的功能。例如，如果用户想要共享该应用程序或共享来自该应用程序的消息，则使用该功能。用户可以发送文本，也可以通过此发送预定义的文本。本文演示了安卓应用程序如何在 WhatsApp 上发送消息。Whatsapp 必须安装在用户的设备上。

在本文中，我们将尝试创建一个安卓应用程序，使用 Kotlin 在 WhatsApp 上发送消息。

> **注意:** 要查看如何在 Java 中做到这一点，请参考[如何使用 Java 在安卓的 WhatsApp 上发送消息](https://www.geeksforgeeks.org/how-to-send-message-on-whatsapp-in-android/)。

## 方法

### 第一步: 修改 `activity_main.xml` 文件
打开 `activity_main.xml` 文件，添加布局代码。`activity_main.xml` 包含[线性布局](https://www.geeksforgeeks.org/android-linearlayout-in-kotlin/)，该布局包含输入消息的[编辑文本](https://www.geeksforgeeks.org/android-edittext-in-kotlin/)和提交消息的[按钮](https://www.geeksforgeeks.org/button-in-kotlin/)。

## `activity_main.xml`

```kt
<LinearLayout 
      xmlns:android="http://schemas.android.com/apk/res/android"
      xmlns:app="http://schemas.android.com/apk/res-auto"
      xmlns:tools="http://schemas.android.com/tools"
      android:layout_width="match_parent"
      android:layout_height="match_parent"
      tools:context=".MainActivity"
      android:orientation="vertical">

<!--EditText to take message input from user-->
  <EditText
      android:id="@+id/message"
      android:layout_width="match_parent"
      android:layout_height="wrap_content"
      android:layout_margin="16dp"
      android:hint="Enter you message here"
      android:lines="8"
      android:inputType="textMultiLine"
      android:gravity="left|top"
      />

<!--Button to send message on Whatsapp-->
  <Button
      android:id="@+id/submit"
      android:layout_width="wrap_content"
      android:layout_height="wrap_content"
      android:layout_gravity="center_horizontal"
      android:text="Submit"
      android:background="@color/colorPrimary"
      android:textColor="@android:color/white"/>
</LinearLayout>
```

### 第二步: 使用 `MainActivity.kt` 文件

*   在 Kotlin 文件中获取 `EditText` 和 `Button` 的引用。使用 `findViewById()` 方法通过 id 获取引用。

**获取 `EditText` 引用**

> // 参考编辑文字
> val messageedittext = findviewbyid<edittext>(r . id . message)

**同样获取按钮引用**

> // 引用按钮
> val submit = findwiewbyid<按钮>

*   编写一个函数来向 WhatsApp 发送消息。使用 `ACTION_SEND` 创建一个[意图](https://www.geeksforgeeks.org/android-implicit-and-explicit-intents-with-examples/)，并为此指定 WhatsApp 包名以便直接打开。`com.whatsapp` 是官方 WhatsApp 应用的包名。

```kt
    fun sendMessage(message:String){

// Creating intent with action send
          val intent = Intent(Intent.ACTION_SEND)

// Setting Intent type
          intent.type = "text/plain"

// Setting whatsapp package name
          intent.setPackage("com.whatsapp")

// Give your message here
          intent.putExtra(Intent.EXTRA_TEXT, message)

// Checking whether whatsapp is installed or not
          if (intent.resolveActivity(packageManager) == null) {
              Toast.makeText(this, 
                             "Please install whatsapp first.", 
                             Toast.LENGTH_SHORT).show()
              return
          }

// Starting Whatsapp
          startActivity(intent)
      }
```

*   在按钮上使用 `setOnClickListener` 发送信息。获取用户输入的文本，并调用函数在 WhatsApp 上发送消息。

```kt
    // Setting on click listener
    submit.setOnClickListener {
        val message = messageEditText.text.toString()

// Calling the function
        sendMessage(message);
    }
```

## 完整的 `MainActivity.kt` 文件

```kt
package com.gfg

import android.content.Intent
import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.Toast

class MainActivity : AppCompatActivity() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

// Referencing the Edit Text
        val messageEditText = findViewById<EditText>(R.id.message)

// Referencing the button
        val submit = findViewById<Button>(R.id.submit)

// Setting on click listener
        submit.setOnClickListener {
            val message = messageEditText.text.toString()

// Calling the function
            sendMessage(message);
        }
    }

    fun sendMessage(message: String) {

// Creating intent with action send
        val intent = Intent(Intent.ACTION_SEND)

// Setting Intent type
        intent.type = "text/plain"

// Setting whatsapp package name
        intent.setPackage("com.whatsapp")

// Give your message here
        intent.putExtra(Intent.EXTRA_TEXT, message)

// Checking whether whatsapp is installed or not
        if (intent.resolveActivity(packageManager) == null) {
            Toast.makeText(this, 
                           "Please install whatsapp first.", 
                           Toast.LENGTH_SHORT).show()
            return
        }

// Starting Whatsapp
        startActivity(intent)
    }
}
```

**输出**

<video class="wp-video-shortcode" id="video-440389-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200528210120/2020_05_28_20_50_08_trim.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200528210120/2020_05_28_20_50_08_trim.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200528210120/2020_05_28_20_50_08_trim.mp4)</video>