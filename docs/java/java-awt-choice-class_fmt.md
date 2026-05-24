# Java AWT | `Choice` 类

> 原文: [https://www.geeksforgeeks.org/java-awt-choice-class/](https://www.geeksforgeeks.org/java-awt-choice-class/)

`Choice` 类是 Java 抽象窗口工具包 (AWT) 的一部分。`Choice` 类为用户提供了一个弹出菜单，用户可以从弹出菜单中选择一个项目。选定的项目出现在顶部。`Choice` 类继承了 `Component`。

## `Choice` 类的构造函数

- **`Choice()`**: 创建一个新的空选择菜单。

## `Choice` 类的不同方法

| 方法 | 说明 |
| --- | --- |
| `add(String)` | 向此选择菜单添加一个项目。 |
| `addItemListener(ItemListener l)` | 添加指定的项目侦听器，以从该选项菜单接收项目事件。 |
| `addNotify()` | 创建选择的对等项。 |
| `getAccessibleContext()` | 获取与此选项关联的 `AccessibleContext`。 |
| `getItem(int i)` | 获取此选择菜单中指定索引处的字符串。 |
| `getItemCount()` | 返回此选项菜单中的项目数。 |
| `getItemListeners()` | 返回在此选项上注册的所有项目侦听器的数组。 |
| `getListeners(Class l)` | 返回一个数组，其中包含当前在此选项中注册为 `l` 类型的所有对象。 |
| `getSelectedIndex()` | 返回当前选定项的索引。 |
| `getSelectedItem()` | 获取当前选择的字符串表示形式。 |
| `insert(String s, int i)` | 将项目插入此选项的指定位置。 |
| `paramString()` | 返回表示此选项菜单状态的字符串。 |
| `processEvent(AWTEvent e)` | 根据此选择处理事件。 |
| `processItemEvent(ItemEvent e)` | 通过将选项菜单上发生的项目事件分派到任何已注册的项目侦听器对象来处理它们。 |
| `remove(int p)` | 从选项菜单的指定位置移除一个项目。 |
| `remove(String)` | 从“选择”菜单中删除第一个出现的项目。 |
| `removeAll()` | 从选项菜单中删除所有项目。 |
| `select(int p)` | 将此“选择”菜单中的选定项目设置为指定位置的项目。 |

下面的程序说明了 Java AWT 中的 `Choice` 类:

### Program to create a simple choice and add elements to it

```java
// Java Program to create a simple
// choice and add elements to it .
import java.awt.*;
import javax.swing.*;

class choice {

    // choice
    static Choice c;

    // frame
    static JFrame f;

    // default constructor
    choice()
    {
    }

    // Main Method
    public static void main(String args[])
    {

        // create a frame
        f = new JFrame("choice");

        // create e panel
        JPanel p = new JPanel();

        // create a choice
        c = new Choice();

        // add element to the list
        c.add("Andrew");
        c.add("Arnab");
        c.add("Ankit");

        // add choice to panel
        p.add(c);

        // add panel to the frame
        f.add(p);

        // show the frame
        f.show();
        f.setSize(300, 300);
    }
}
```

**输出:**
![](img/501d858d2cc3beef83732e58a18651c5.png)

### Program to create a simple choice and add ItemListener to it

```java
// Java  Program to create a simple
// choice and add ItemListener to it
import java.awt.*;
import javax.swing.*;
import java.awt.event.*;

class choice implements ItemListener {

    // choice
    static Choice c;

    // frame
    static JFrame f;

    // label
    static Label l;

    // default constructor
    choice()
    {
    }

    // Main Method
    public static void main(String args[])
    {

        // create a frame
        f = new JFrame("choice");

        // object
        choice ch = new choice();

        // create e panel
        JPanel p = new JPanel();

        // create a choice
        c = new Choice();

        // add element to the list
        c.add("Andrew");
        c.add("Arnab");
        c.add("Ankit");

        // add itemListener to it
        c.addItemListener(ch);

        // create a label
        l = new Label();

        // set the label text
        l.setText(c.getSelectedItem() + " selected");

        // add choice to panel
        p.add(c);
        p.add(l);

        // add panel to the frame
        f.add(p);

        // show the frame
        f.show();
        f.setSize(300, 300);
    }

    // if an item is selected
    public void itemStateChanged(ItemEvent e)
    {
        l.setText(c.getSelectedItem() + " selected");
    }
}
```

**输出:**
![](img/d8cd8c95a09696b29ec189d51612b41d.png)

### 用于创建选项并手动添加元素的程序 (使用 `add(String)` 功能)

```java
// Java Program to create a choice and
// manually add elements to it
// (using add(String s) function)
import java.awt.*;
import javax.swing.*;
import java.awt.event.*;

class choice implements ItemListener, ActionListener {

    // choice
    static Choice c;

    // frame
    static JFrame f;

    // label
    static Label l;

    // textfield
    static TextField tf;

    // default constructor
    choice()
    {
    }

    // Main Method
    public static void main(String args[])
    {

        // create a frame
        f = new JFrame("choice");

        // object
        choice ch = new choice();

        // create e panel
        JPanel p = new JPanel();

        // create a choice
        c = new Choice();

        // add element to the list
        c.add("Andrew");

        // create a textfield
        tf = new TextField(7);

        // create a button
        Button b = new Button("ok");

        // add actionListener
        b.addActionListener(ch);

        // add itemListener to it
        c.addItemListener(ch);

        // create a label
        l = new Label();
        Label l1 = new Label("add names");

        // set the label text
        l.setText(c.getSelectedItem() + " selected");

        // add choice to panel
        p.add(c);
        p.add(l);
        p.add(l1);
        p.add(tf);
        p.add(b);

        // add panel to the frame
        f.add(p);

        // show the frame
        f.show();
        f.setSize(250, 300);
    }

    // if an item is selected
    public void itemStateChanged(ItemEvent e)
    {
        l.setText(c.getSelectedItem() + " selected");
    }

    // if button is pressed
    public void actionPerformed(ActionEvent e)
    {
        // add item to the choice
        c.add(tf.getText());
    }
}
```

**输出:**
![](img/c2036a95ec7c048775782a4ad41b45df.png) ![](img/8031c8e18bfcacb6a2d16be307e8facb.png)

**注意:** 程序可能无法在联机 IDE 中运行，请使用脱机 IDE。

**参考:** [https://docs.oracle.com/javase/7/docs/api/java/awt/Choice.html](https://docs.oracle.com/javase/7/docs/api/java/awt/Choice.html)