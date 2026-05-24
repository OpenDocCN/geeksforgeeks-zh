# Java Swing | ScrollPaneLayout 类

> 原文：[https://www.geeksforgeeks.org/java-swing-scrollpanelayout-class/](https://www.geeksforgeeks.org/java-swing-scrollpanelayout-class/)

`JScrollPane` 使用的布局管理器。`ScrollPaneLayout` 基于九个组件：一个视口、两个滚动条、一个行标题、一个列标题和四个“角”组件。

**该类的构造函数：**

*   `ScrollPaneLayout()`: 用于构建新的滚动面板布局。

**常用方法：**

1.  `removeLayoutComponent(Component component)`: 从布局中移除指定的组件。
2.  `getColumnHeader()`: 它返回作为列标题的 `JViewport` 对象。
3.  `getVerticalScrollBar()`: 返回处理垂直滚动的 `JScrollBar` 对象。
4.  `getHorizontalScrollBar()`: 返回处理水平滚动的 `JScrollBar` 对象。
5.  `addLayoutComponent(String st, Component c)`: 将指定的组件添加到布局中。
6.  `getViewport()`: 返回显示可滚动内容的 `JViewport` 对象。
7.  `getCorner(String key)`: 用于返回指定角点的组件。

下面的程序说明了 `ScrollPaneLayout` 类的使用：

1.  下面的程序通过在一个 `JFrame` 中排列几个 `JLabel` 组件来说明 `ScrollPaneLayout` 的使用，该 `JFrame` 的实例类是“`Geeks`”。我们创建了一个名为“`scrollpane`”的 `JScrollPane` 组件和一个名为“`list`”的 `JList` 组件。我们使用 `setSize()` 和 `setVisible()` 方法设置框架的大小和可见性。布局使用 `setLayout()` 方法设置。

## 示例 1

```java
// Java Program to illustrate the
// ScrollPaneLayout class
import java.awt.BorderLayout;
import javax.swing.JFrame;
import javax.swing.JList;
import javax.swing.JScrollPane;

// create a class Geeks extending JFrame
public class Geeks extends JFrame
{
    // Declaration of objects of the
    // JScrollPane class.
    JScrollPane scrollpane;

    // Constructor of Geeks class
    public Geeks()
    {
        // used to call super class
        // variables and methods
        super("JScrollPane Demonstration");

        // Function to set size of JFrame.
        setSize(300, 200);

        // Function to set Default close
        // operation of JFrame.
        setDefaultCloseOperation(EXIT_ON_CLOSE);

        // to contain a string value
        String categories[] = {"Geeks", "Language", "Java",
                               "Sudo Placement", "Python",
                               "CS Subject", "Operating System",
                               "Data Structure", "Algorithm",
                               "PHP language", "JAVASCRIPT",
                               "C Sharp" };

        // Creating Object of "JList" class
        JList list = new JList(categories);

        // Creating Object of
        // "scrollpane" class
        scrollpane = new JScrollPane(list);

        // to get content pane
        getContentPane().add(scrollpane, BorderLayout.CENTER);
    }

    // Main Method
    public static void main(String args[])
    {
        // Creating Object of Geeks class.
        Geeks sl = new Geeks();

        // Function to set visibility of JFrame.
        sl.setVisible(true);
    }
}
```

**输出：**

<video class="wp-video-shortcode" id="video-221671-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/Untitled-20.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/Untitled-20.mp4](https://media.geeksforgeeks.org/wp-content/uploads/Untitled-20.mp4)</video>

2.  下面的程序通过在一个 `JFrame` 中排列几个 `JLabel` 组件来说明 `ScrollPaneLayout` 的使用，其实例类被命名为“`ScrollPanel`”。我们创建了一个名为“`scrollpane`”的 `JScrollPane` 组件。同时，创建 `JRadioButton` 和 `ButtonGroup`。我们使用 `setSize()` 和 `setVisible()` 方法设置框架的大小和可见性。布局使用 `setLayout()` 方法设置。

## 示例 2

```java
// Java Program to illustrate the
// ScrollPaneLayout class
import java.awt.BorderLayout;
import java.awt.GridLayout;
import javax.swing.ButtonGroup;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JPanel;
import javax.swing.JRadioButton;
import javax.swing.JScrollPane;

// create a class ScrollPanel
// extending JFrame
public class ScrollPanel extends JFrame {

    // Declaration of objects of the
    // JScrollPane class
    JScrollPane scrollpane;

    // Constructor of ScrollPanel class
    public ScrollPanel()
    {
        // used to call super class
        // variables and methods
        super("JScrollPane Demonstration");

        // Function to set size of JFrame.
        setSize(300, 200);

        // Function to set Default
        // close operation of JFrame.
        setDefaultCloseOperation(EXIT_ON_CLOSE);
        init();

        // Function to set
        // visible of JFrame.
        setVisible(true);
    }

    // class init
    public void init()
    {
        // Declaration of objects
        // of JRadioButton class.
        JRadioButton form[][] = new JRadioButton[12][5];

        // to contain a string count
        String counts[] = {"", "1 star", "2 star",
                    "3 star", "4 star", "5 star"};

        // to contain a string value
        String categories[] = {"Geeks", "Language", "Java",
                               "Sudo Placement", "Python",
                               "CS Subject", "Operating System",
                               "Data Structure", "Algorithm",
                               "PHP language", "JAVASCRIPT",
                               "C Sharp" };

        // Declaration of objects
        // of the JPanel class.
        JPanel p = new JPanel();

        // Function to set size of JFrame.
        p.setSize(600, 400);

        // Function to set Layout of JFrame.
        p.setLayout(new GridLayout(13, 6, 10, 0));

        // for loop
        for (int row = 0; row < 13; row++) {

            // Declaration of objects
            // of ButtonGroup class
            ButtonGroup bg = new ButtonGroup();

            for (int col = 0; col < 6; col++)
            {
                // If condition
                if (row == 0) {
                    // add new Jlabel
                    p.add(new JLabel(counts[col]));
                }
                else {
                    // If condition
                    if (col == 0)
                    {
                        // add new Jlabel
                        p.add(new JLabel(categories[row - 1]));
                    }
                    else
                    {
                        form[row - 1][col - 1] = new JRadioButton();

                        // add form in ButtonGroup
                        bg.add(form[row - 1][col - 1]);

                        // add form in JFrame
                        p.add(form[row - 1][col - 1]);
                    }
                }
            }
        }

        // Declaration of objects
        // of scrollpane class.
        scrollpane = new JScrollPane(p);

        // to get content pane
        getContentPane().add(scrollpane, BorderLayout.CENTER);
    }

    // Main Method
    public static void main(String args[])
    {
        new ScrollPanel();
    }
}
```

**输出：**

<video class="wp-video-shortcode" id="video-221671-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/Untitled-21.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/Untitled-21.mp4](https://media.geeksforgeeks.org/wp-content/uploads/Untitled-21.mp4)</video>

**注意：** 上述程序可能无法在在线 IDE 中运行。请使用离线编译器。

**参考：** [https://docs.oracle.com/javase/7/docs/api/javax/swing/ScrollPaneLayout.html](https://docs.oracle.com/javase/7/docs/api/javax/swing/ScrollPaneLayout.html)