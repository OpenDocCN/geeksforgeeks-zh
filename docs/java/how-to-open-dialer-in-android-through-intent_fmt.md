# 如何通过意向在安卓中打开拨号器？

> 原文：[https://www.geeksforgeeks.org/how-to-open-dialer-in-android-through-intent/](https://www.geeksforgeeks.org/how-to-open-dialer-in-android-through-intent/)

电话拨号器是安卓操作系统中的一项活动，用于拨打电话。通常，此类活动可能有也可能没有编辑文本（用于输入号码）和呼叫按钮。当用户按下呼叫按钮时，它会调用拨号器应用程序活动。建议使用`tel:`前缀，否则会抛出`java.lang.IllegalStateException`。`ACTION_DIAL`不需要任何权限。下面是 Java 和 Kotlin 中`MainActivity`文件的代码。

## Java 语言

```java
package com.geeksforgeeks.gfg.dial;

// importing packages
import android.content.Intent;
import android.net.Uri;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        // Binding MainActivity.java with
        // activity_main.xml file
        setContentView(R.layout.activity_main);
    }

    // This function is called when button is clicked.
    public void Call(View v) {
        // Find the EditText by its unique ID
        EditText e = (EditText) findViewById(R.id.editText);

        // show() method display the toast with message
        // "clicked"
        Toast.makeText(this, "clicked", Toast.LENGTH_LONG).show();

        // Use format with "tel:" and phoneNumber created is
        // stored in u.
        Uri u = Uri.parse("tel:" + e.getText().toString());

        // Create the intent and set the data for the
        // intent as the phone number.
        Intent i = new Intent(Intent.ACTION_DIAL, u);

        try {
            // Launch the Phone app's dialer with a phone
            // number to dial a call.
            startActivity(i);
        } catch (SecurityException s) {
            // show() method display the toast with
            // exception message.
            Toast.makeText(this, "An error occurred", Toast.LENGTH_LONG).show();
        }
    }
}
```

## Kotlin 语言

```kotlin
package com.geeksforgeeks.gfg.dial

import android.content.Intent
import android.net.Uri
import import android.os.Bundle
import android.view.View
import android.widget.EditText
import android.widget.Toast
import androidx.appcompat.app.AppCompatActivity
import com.example.gfgreviewinjava.R

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        // Binding MainActivity.java with
        // activity_main.xml file
        setContentView(R.layout.activity_main)
    }

    // This function is called when button is clicked.
    fun Call(v: View?) {
        // Find the EditText by its unique ID
        val e = findViewById<View>(R.id.editText) as EditText

        // show() method display the toast with message
        // "clicked"
        Toast.makeText(this, "clicked", Toast.LENGTH_LONG).show()

        // Use format with "tel:" and phoneNumber created is
        // stored in u.
        val u = Uri.parse("tel:" + e.text.toString())

        // Create the intent and set the data for the
        // intent as the phone number.
        val i = Intent(Intent.ACTION_DIAL, u)
        try {
            // Launch the Phone app's dialer with a phone
            // number to dial a call.
            startActivity(i)
        } catch (s: SecurityException) {
            // show() method display the toast with
            // exception message.
            Toast.makeText(this, "An error occurred", Toast.LENGTH_LONG).show()
        }
    }
}
```

为了在不切换到拨号器活动的情况下进行直接呼叫，您需要添加`Intent.ACTION_CALL`代替`Intent.ACTION_DIAL`。

## Activity_T2

## XML

```xml
<?xml version="1.0" encoding="utf-8"?>
<android.support.constraint.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context="com.example.hp.dial.MainActivity">

    <EditText
        android:id="@+id/editText"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginLeft="8dp"
        android:layout_marginRight="8dp"
        android:layout_marginTop="65dp"
        android:hint="Phone No."
        android:inputType="phone"
        app:layout_constraintHorizontal_bias="0.503"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginLeft="8dp"
        android:layout_marginRight="8dp"
        android:layout_marginTop="67dp"
        android:onClick="Call"
        android:text="DIAL"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/editText" />
</android.support.constraint.ConstraintLayout>
```