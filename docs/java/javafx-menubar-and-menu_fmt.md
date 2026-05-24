# JavaFX | 菜单栏和菜单

> 原文: [https://www.geeksforgeeks.org/javafx-menubar-and-menu/](https://www.geeksforgeeks.org/javafx-menubar-and-menu/)

**菜单**是一个包含多个菜单项的弹出菜单，当用户单击一个菜单时会显示这些菜单项。用户可以选择菜单项，之后菜单进入隐藏状态。

**菜单栏**通常位于包含多个菜单的屏幕顶部。JavaFX `MenuBar` 类通常是菜单栏的实现。

## 菜单栏类的构造函数

1.  `MenuBar()`: 创建一个新的空菜单栏。
2.  `MenuBar(Menu… m)`: 用给定的一组菜单创建一个新的菜单栏。

## 菜单类的构造函数

1.  `Menu()`: 创建一个空菜单。
2.  `Menu(String)`: 创建一个以字符串为标签的菜单。
3.  `Menu(String s, Node n)`: 构造一个菜单，用指定的文本设置显示文本，并将图形节点设置为给定的节点。
4.  `Menu(String s, Node n, MenuItem… i)`: 构造一个菜单，用指定的文本设置显示文本，将图形节点设置到给定的节点，并将给定的项目插入到项目列表中。

## 常用方法

| 方法 | 说明 |
| --- | --- |
| `getItems()` | 返回菜单项目 |
| `hide()` | 隐藏菜单 |
| `show()` | 显示菜单 |
| `getMenus()` | 要在此菜单栏中显示的菜单。 |
| `isUseSystemMenuBar()` | 获取 `useSystemMenuBar` 属性的值 |
| `setUseSystemMenuBar(boolean v)` | 设置 `useSystemMenuBar` 属性的值。 |
| `setOnHidden(EventHandler v)` | 设置“开”属性的值。 |
| `setOnHiding(EventHandler v)` | 设置属性的值。 |
| `setOnShowing(EventHandler v)` | 设置上属性的值。 |
| `setOnShown(EventHandler v)` | 设置向下属性的值。 |

下面的程序说明了 `MenuBar` 和 `Menu` 类：

## 示例1：创建菜单栏并添加菜单和菜单项

Java program to create a menu bar and add menu to it and also add menuitems to the menu: This program creates a menubar indicated by the name `mb`. A menu will be created by name `m` and 3 menuitems `m1`, `m2`, `m3` will be added to the menu `m` and the menu `m` will be added to menubar `mb`. The menubar will be created inside a scene, which in turn will be hosted inside a stage. The function `setTitle()` is used to provide title to the stage. Then a `VBox` is created, on which `addChildren()` method is called to attach the menubar inside the scene. Finally, the `show()` method is called to display the final results.

```java
// Java program to create a menu bar and add
// menu to it and also add menuitems to menu
import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.*;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.control.*;
import javafx.stage.Stage;
import javafx.scene.control.Alert.AlertType;
import java.time.LocalDate;
public class MenuBar_1 extends Application {

    // launch the application
    public void start(Stage s)
    {
        // set title for the stage
        s.setTitle("creating MenuBar");

        // create a menu
        Menu m = new Menu("Menu");

        // create menuitems
        MenuItem m1 = new MenuItem("menu item 1");
        MenuItem m2 = new MenuItem("menu item 2");
        MenuItem m3 = new MenuItem("menu item 3");

        // add menu items to menu
        m.getItems().add(m1);
        m.getItems().add(m2);
        m.getItems().add(m3);

        // create a menubar
        MenuBar mb = new MenuBar();

        // add menu to menubar
        mb.getMenus().add(m);

        // create a VBox
        VBox vb = new VBox(mb);

        // create a scene
        Scene sc = new Scene(vb, 500, 300);

        // set the scene
        s.setScene(sc);

        s.show();
    }

    public static void main(String args[])
    {
        // launch the application
        launch(args);
    }
}
```

**输出**:
![](img/4d639090a7e82ddcecd5c958af4f9772.png)

## 示例2：为菜单项添加事件监听器

Java program to create a menu bar and add a menu to it and also add menu items to menu and also add an event listener to handle the events: This program creates a menubar indicated by the name `mb`. A menu will be created by name `m` and 3 menuitems `m1`, `m2`, `m3` will be added to the menu `m` and the menu `m` will be added to the menubar `mb`. The menubar will be created inside a scene, which in turn will be hosted inside a stage. The function `setTitle()` is used to provide title to the stage. Then a `VBox` is created, on which `addChildren()` method is called to attach the menubar inside the scene. Finally, the `show()` method is called to display the final results. A label will also be created that will show which menuitem is selected. An action event will be created to process the action when the menu item is clicked by the user.

```java
// Java program to create a menu bar and add menu to
// it and also add menuitems to menu and also add
// an event listener to handle the events
import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.*;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.control.*;
import javafx.stage.Stage;
import javafx.scene.control.Alert.AlertType;
import java.time.LocalDate;
public class MenuBar_2 extends Application {

    // launch the application
    public void start(Stage s)
    {
        // set title for the stage
        s.setTitle("creating MenuBar");

        // create a menu
        Menu m = new Menu("Menu");

        // create menuitems
        MenuItem m1 = new MenuItem("menu item 1");
        MenuItem m2 = new MenuItem("menu item 2");
        MenuItem m3 = new MenuItem("menu item 3");

        // add menu items to menu
        m.getItems().add(m1);
        m.getItems().add(m2);
        m.getItems().add(m3);

        // label to display events
        Label l = new Label("\t\t\t\t"
                            + "no menu item selected");

        // create events for menu items
        // action event
        EventHandler<ActionEvent> event = new EventHandler<ActionEvent>() {
            public void handle(ActionEvent e)
            {
                l.setText("\t\t\t\t" + ((MenuItem)e.getSource()).getText() +
                                                " selected");
            }
        };

        // add event
        m1.setOnAction(event);
        m2.setOnAction(event);
        m3.setOnAction(event);

        // create a menubar
        MenuBar mb = new MenuBar();

        // add menu to menubar
        mb.getMenus().add(m);

        // create a VBox
        VBox vb = new VBox(mb, l);

        // create a scene
        Scene sc = new Scene(vb, 500, 300);

        // set the scene
        s.setScene(sc);

        s.show();
    }

    public static void main(String args[])
    {
        // launch the application
        launch(args);
    }
}
```

**输出**:
![](img/0883295a04248d7aa0e0191317da8837.png)

**注意:** 上述程序可能无法在联机 IDE 中运行，请使用脱机转换器。

**参考:**

*   [https://docs.oracle.com/javase/8/javafx/api/javafx/scene/control/Menu.html](https://docs.oracle.com/javase/8/javafx/api/javafx/scene/control/Menu.html)
*   [https://docs.oracle.com/javase/8/javafx/api/javafx/scene/control/MenuBar.html](https://docs.oracle.com/javase/8/javafx/api/javafx/scene/control/MenuBar.html)