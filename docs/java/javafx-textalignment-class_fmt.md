# JavaFX TextAlignment 类

> 原文：[https://www.geeksforgeeks.org/javafx-textalignment-class/](https://www.geeksforgeeks.org/javafx-textalignment-class/)

`TextAlignment` 类是 JavaFX 的一部分。`TextAlignment` 类表示水平文本对齐。`TextAlignment` 类继承自枚举类。

## 常用方法

| 方法 | 说明 |
| --- | --- |
| `valueOf(String name)` | 返回指定名称的文本对齐方式。 |
| `values()` | 返回包含所有文本对齐值的数组。 |

## 示例说明

**Java 程序创建一个 `TextFlow` 并向其中添加文本对象，设置文本对齐方式并同时设置一个组合框来更改对齐方式并设置文本流的行距：**

在本程序中我们将创建一个名为 `tile pane` 的 `pane`。将名为 `label` 的标签和一些按钮添加到 `tile pane` 中。使用 `setAlignment()` 功能设置 `tile pane` 的对齐。将文本对齐值的所有名称存储在字符串数组中。现在创建一个 `ComboBox`，它将包含文本对齐值的名称，并创建一个操作事件来处理 `ComboBox` 事件。事件处理程序会将文本流的文本对齐设置为选定的文本对齐值。现在创建一个 `VBox`，并将 `tilepane` 和组合框添加到 `vbox` 中。最后，将 `vbox` 添加到场景中，将场景添加到舞台中，并调用 `show()` 函数显示最终结果。

## 代码示例

```java
// Java program to create a TextFlow and
// add text object to it, set text Alignment
// and also set a combo box to change Alignment
// and set line spacing of the text flow.
import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.*;
import javafx.scene.layout.*;
import javafx.stage.Stage;
import javafx.scene.layout.*;
import javafx.scene.paint.*;
import javafx.scene.text.*;
import javafx.geometry.*;
import javafx.scene.layout.*;
import javafx.scene.shape.*;
import javafx.collections.*;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;

public class Alignment_1 extends Application {

    // launch the application
    public void start(Stage stage)
    {
        try {
            // set title for the stage
            stage.setTitle("Alignment");

            // create TextFlow
            TextFlow text_flow = new TextFlow();

            // create text
            Text text_1 = new Text("GeeksforGeeks\n");

            // set the text color
            text_1.setFill(Color.GREEN);

            // set font of the text
            text_1.setFont(Font.font("Verdana", 25));

            // create text
            Text text_2 = new Text("How many times were you frustrated "+
                                   "while looking out for a good "+
                                   "collection of programming/algorithm/ "+
                                   "interview questions? What did you "+
                                   "expect and what did you get? "+
                                   "This portal has been created to "+
                                   "provide well written, well "+
                                   "thought and well explained solutions "+
                                   "for selected questions.");

            // set the text color
            text_2.setFill(Color.BLUE);

            // set font of the text
            text_2.setFont(Font.font("Helvetica",
                            FontPosture.ITALIC, 15));

            // add text to textflow
            text_flow.getChildren().add(text_1);
            text_flow.getChildren().add(text_2);

            // alignment names
            String weight[] = { "CENTER", "JUSTIFY", "LEFT", "RIGHT" };

            // Create a combo box
            ComboBox combo_box =
                new ComboBox(FXCollections.observableArrayList(weight));

            // Create action event
            EventHandler<ActionEvent> event = new EventHandler<ActionEvent>()
            {
                public void handle(ActionEvent e)
                {
                    // set alignment
                    text_flow.setTextAlignment(TextAlignment.valueOf(
                                              (String)combo_box.getValue()));
                }
            };

            // Set on action
            combo_box.setOnAction(event);

            // set text Alignment
            text_flow.setTextAlignment(TextAlignment.CENTER);

            // set line spacing
            text_flow.setLineSpacing(20.0f);

            // create VBox
            VBox vbox = new VBox(combo_box, text_flow);

            // set alignment of vbox
            vbox.setAlignment(Pos.CENTER);

            // create a scene
            Scene scene = new Scene(vbox, 400, 300);

            // set the scene
            stage.setScene(scene);

            stage.show();
        }
        catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }

    // Main Method
    public static void main(String args[])
    {
        // launch the application
        launch(args);
    }
}
```

## 输出

<video class="wp-video-shortcode" id="video-226120-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/Alignment.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/Alignment.mp4](https://media.geeksforgeeks.org/wp-content/uploads/Alignment.mp4)</video>

## 注意

上述程序可能无法在联机 IDE 中运行，请使用脱机编译器。

## 参考

[https://docs.oracle.com/javase/8/javafx/api/javafx/scene/text/TextAlignment.html](https://docs.oracle.com/javase/8/javafx/api/javafx/scene/text/TextAlignment.html)