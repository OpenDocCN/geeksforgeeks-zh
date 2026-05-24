# JavaFX 滑块类

> 原文：[https://www.geeksforgeeks.org/javafx-slider-class/](https://www.geeksforgeeks.org/javafx-slider-class/)

滑块是 JavaFX 中的一个控件，用于显示连续或离散范围的有效数字选项，并允许用户与控件交互。滑块呈现为带有旋钮的垂直或水平条，用户可以滑动该旋钮来指示所需的值。滑块也可以有刻度线和标签来指示沿条的间隔。

## 滑块的基本变量

滑块的三个基本变量是 `min`、`max` 和 `value`。该值应该始终是由最小值和最大值定义的范围内的数字。`min` 应始终小于 `max`。`min` 默认为 0，而 `max` 默认为 100。

## 类的构造函数

*   `Slider()`: 创建默认的滑块实例。
*   `Slider(double min, double max, double value)`: 使用指定的滑块最小值、最大值和当前值构建滑块控件。

## 常用方法

| 方法 | 描述 |
| --- | --- |
| `adjustValue(double newValue)` | 调整值以匹配新值。 |
| `decrement()` | 将值递减区块增量，以最大值为界。 |
| `getBlockIncrement()` | 获取属性 `blockIncrement` 的值。 |
| `getMax()` | 获取属性 `max` 的值。 |
| `getMin()` | 获取属性 `min` 的值。 |
| `getMajorTickUnit()` | 获取 `majorTickUnit` 属性的值。 |
| `getMinorTickCount()` | 获取 `minorTickCount` 属性的值。 |
| `getValue()` | 获取属性 `value`。 |
| `increment()` | 以最大值为界，按块增量递增该值。 |
| `setBlockIncrement(double value)` | 设置属性 `blockIncrement` 的值。 |
| `setMajorTickUnit(double value)` | 设置 `majorTickUnit` 属性的值。 |
| `setMax(double value)` | 设置属性 `max` 的值。 |
| `setMin(double value)` | 设置属性 `min` 的值。 |
| `setMinorTickCount(int value)` | 设置 `minorTickCount` 属性的值。 |
| `setValue(double value)` | 设置属性 `value`。 |
| `setValueChanging(boolean value)` | 设置属性 `valueChanging`。 |
| `setShowTickMarks(boolean value)` | 设置属性 `showTickMarks` 的值。 |
| `setShowTickLabels(boolean value)` | 设置属性 `showTickLabels` 的值。 |
| `isShowTickLabels()` | 获取属性 `showTickLabels` 的值。 |
| `isShowTickMarks()` | 获取属性 `showTickMarks` 的值。 |

下面的程序说明了 `Slider` 类的使用：

### 1. 实现 Slider 类的简单 Java 程序

在这个程序中，我们将创建一个 `Group` 和 `Scene`。将 `Scene` 添加到框架。然后，创建一个 `Slider` 并将其添加到框架。现在启动应用程序。

```java
// Java program to implement the Slider Class
import javafx.application.Application;
import javafx.scene.Group;
import javafx.scene.Scene;
import javafx.scene.control.Slider;
import javafx.stage.Stage;

public class SliderExample extends Application {

    public void start(Stage stage)
    {
        // creating group
        Group root = new Group();
        Scene scene = new Scene(root, 600, 400);

        // set Scene to the stage
        stage.setScene(scene);

        // set title for the frame
        stage.setTitle("Slider Sample");

        // create slider
        Slider slider = new Slider();

        // add slider to the frame
        root.getChildren().add(slider);

        stage.show();
    }

    // Main Method
    public static void main(String[] args)
    {
        // launch the application
        launch(args);
    }
}
```

**输出：**

<video class="wp-video-shortcode" id="video-222956-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20180831_234901.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20180831_234901.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20180831_234901.mp4)</video>

### 2. 使用 TickMarks 和 TickLabels 实现 Slider 类的 Java 程序

在这个程序中，我们将创建一个 `Group` 和 `Scene`。将 `Scene` 添加到框架。创建一个具有指定 `min`、`max` 和 `value` 的滑块。启用刻度标记和标签。设置 `MajorTickUnit` 为指定值。将滑块添加到框架并显示它。

```java
// Java program to implement Slider class
// by using TickMarks and TickLabels
import javafx.application.Application;
import javafx.scene.Group;
import javafx.scene.Scene;
import javafx.scene.control.Slider;
import javafx.stage.Stage;

public class SliderExample extends Application {

    public void start(Stage stage)
    {
        Group root = new Group();

        // create a Scene
        Scene scene = new Scene(root, 600, 400);

        // add Scene to the frame
        stage.setScene(scene);

        // set title of the frame
        stage.setTitle("Slider Sample");

        // Creates a slider
        Slider slider = new Slider(0, 1, 0.5);

        // enable the marks
        slider.setShowTickMarks(true);

        // enable the Labels
        slider.setShowTickLabels(true);

        // set Major tick unit
        slider.setMajorTickUnit(0.25f);

        // sets the value of the property
        // blockIncrement
        slider.setBlockIncrement(0.1f);

        root.getChildren().add(slider);

        // display
        stage.show();
    }

    // Main Method
    public static void main(String[] args)
    {
        // Launch the application
        launch(args);
    }
}
```

**输出：**

<video class="wp-video-shortcode" id="video-222956-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20180901_000557.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20180901_000557.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20180901_000557.mp4)</video>

### 3. 使用 ChangeListener 实现 Slider 类的 Java 程序

在这个程序中，我们将创建一个 `Label` 并为文本设置颜色。创建一个滑块并设置其 `min`、`max` 和 `value`。启用 `TickLabels` 和 `TickMarks`。设置属性 `blockIncrement` 的值。`setBlockIncrement()` 方法定义了当用户点击轨道时滑块移动的距离。添加 `ChangeListener`，移动滑块时亮度值会改变，这将显示在标签中。创建一个 `VBox` 并添加到框架。创建 `Scene` 并添加到框架。最后，启动应用程序。

```java
// Java program to implement Slider Class
// using ChangeListener
import javafx.application.Application;
import javafx.beans.value.ChangeListener;
import javafx.beans.value.ObservableValue;
import javafx.geometry.Insets;
import javafx.scene.Scene;
import javafx.scene.control.Label;
import javafx.scene.control.Slider;
import javafx.scene.layout.VBox;
import javafx.scene.paint.Color;
import javafx.stage.Stage;

public class SliderExample extends Application {

    public void start(Stage stage)
    {
        // create label
        Label label = new Label("Select the Brightness");
        Label l = new Label(" ");

        // set the color of the text
        l.setTextFill(Color.BLACK);

        // create slider
        Slider slider = new Slider();

        // set the value of property min,
        // max and value
        slider.setMin(0);
        slider.setMax(100);
        slider.setValue(80);

        // enable TickLabels and Tick Marks
        slider.setShowTickLabels(true);
        slider.setShowTickMarks(true);

        slider.setBlockIncrement(10);

        // Adding Listener to value property.
        slider.valueProperty().addListener(
            new ChangeListener<Number>() {
                public void changed(ObservableValue<? extends Number> observable, Number oldValue, Number newValue)
                {
                    l.setText("value: " + newValue);
                }
            });

        // create a VBox
        VBox root = new VBox();

        root.setPadding(new Insets(20));
        root.setSpacing(10);
        root.getChildren().addAll(label, slider, l);

        stage.setTitle("Slider Sample");

        // create Scene and add to the frame
        Scene scene = new Scene(root, 350, 200);
        stage.setScene(scene);
        stage.show();
    }

    // Main Method
    public static void main(String[] args)
    {
        // Launch Application
        Application.launch(args);
    }
}
```

**输出：**

<video class="wp-video-shortcode" id="video-222956-3" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20180901_010316.mp4?_=3">[https://media.geeksforgeeks.org/wp-content/uploads/20180901_010316.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20180901_010316.mp4)</video>

**注意：** 上述程序可能无法在在线 IDE 中运行。请使用离线编译器。

**参考：** [https://docs.oracle.com/javase/8/javafx/api/javafx/scene/control/Slider.html](https://docs.oracle.com/javase/8/javafx/api/javafx/scene/control/Slider.html)