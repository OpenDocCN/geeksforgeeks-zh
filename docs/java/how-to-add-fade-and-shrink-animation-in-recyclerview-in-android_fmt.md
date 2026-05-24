# 如何在安卓 RecyclerView 中添加淡入淡出和收缩动画？

> 原文：[https://www.geeksforgeeks.org/how-to-add-fade-and-shrink-animation-in-recyclerview-in-android/](https://www.geeksforgeeks.org/how-to-add-fade-and-shrink-animation-in-recyclerview-in-android/)

在本文中，我们将展示`RecyclerView`中的淡入淡出和收缩动画。当我们向下移动时，顶部的项目会逐渐消失，然后它会收缩。在输出中，我们可以看到它是如何发生的。我们将使用`Java`编程语言来实现这种效果。

[https://media.geeksforgeeks.org/wp-content/uploads/20210403001528/faderv.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210403001528/faderv.mp4)

## 分步实施

### 第一步：创建新项目

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择`Java`作为编程语言。

### 第二步：将此添加到 `build.gradle` 文件

```gradle
implementation 'com.stone.vega.library:VegaLayoutManager:1.0.6'
```

### 步骤 3：使用 `items.xml` 文件

转到`app > res > layout > New > Layout Resource File`并将文件命名为`items`。转到`item.xml`文件并参考以下代码。下面是`item.xml`文件的代码。

```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:orientation="vertical">

    <Button
        android:id="@+id/itemclick"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Click Here" />

</LinearLayout>
```

### 步骤 4：处理 `RecyclerViewAdapter.java` 文件

在安卓工作室中创建新的`Java`类，并将该类命名为`RecyclerViewAdapter`。转到`RecyclerViewAdapter.java`文件，参考以下代码。以下是`RecyclerViewAdapter.java`文件的代码。

```java
import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;
import android.widget.Button;
import android.widget.Toast;

import androidx.annotation.NonNull;
import androidx.recyclerview.widget.RecyclerView;

public class RecyclerViewAdapter extends RecyclerView.Adapter<RecyclerViewAdapter.ViewHolder> {

    private int mcount;

    public RecyclerViewAdapter(int mcount) {
        this.mcount = mcount;
    }

    @NonNull
    @Override
    public RecyclerViewAdapter.ViewHolder onCreateViewHolder(@NonNull ViewGroup parent, int viewType) {
        View view = LayoutInflater.from(parent.getContext()).inflate(R.layout.items, parent, false);
        return new ViewHolder(view);
    }

    @Override
    public void onBindViewHolder(@NonNull final RecyclerViewAdapter.ViewHolder holder, final int position) {
        holder.itemclick.setText("Button" + position);
        holder.itemclick.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Toast.makeText(holder.itemView.getContext(), "Clicked : " + position, Toast.LENGTH_LONG).show();
            }
        });
    }

    @Override
    public int getItemCount() {
        return mcount;
    }

    public class ViewHolder extends RecyclerView.ViewHolder {
        Button itemclick;

        public ViewHolder(@NonNull View itemView) {
            super(itemView);
            itemclick = itemView.findViewById(R.id.itemclick);
        }
    }
}
```

### 第 5 步：使用 `activity_main.xml` 文件

导航到`app > res > layout > activity_main.xml`并将下面的代码添加到该文件中。下面是`activity_main.xml`文件的代码。

```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <androidx.recyclerview.widget.RecyclerView
        android:id="@+id/rcv"
        android:layout_width="match_parent"
        android:layout_height="match_parent" />

</RelativeLayout>
```

### 第 6 步：使用 `MainActivity.java` 文件

转到`MainActivity.java`文件，参考以下代码。以下是`MainActivity.java`文件的代码。代码中添加了注释，以更详细地理解代码。

```java
import android.os.Bundle;

import androidx.appcompat.app.AppCompatActivity;
import androidx.recyclerview.widget.RecyclerView;

import com.pluscubed.recyclerfastscroll.RecyclerFastScroller;
import com.stone.vega.library.VegaLayoutManager;

public class MainActivity extends AppCompatActivity {

    RecyclerView recyclerView;
    RecyclerFastScroller fastScroller;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        recyclerView = findViewById(R.id.rcv);

        // We have used this to add fade and shrink method
        recyclerView.setLayoutManager(new VegaLayoutManager());
        recyclerView.setAdapter(new RecyclerViewAdapter(50));
    }
}
```

**输出：**

[https://media.geeksforgeeks.org/wp-content/uploads/20210403001528/faderv.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210403001528/faderv.mp4)