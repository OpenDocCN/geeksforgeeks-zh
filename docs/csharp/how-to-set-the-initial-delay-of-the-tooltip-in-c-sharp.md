# 如何在 C# 中设置工具提示的初始延迟？

> 原文:[https://www . geeksforgeeks . org/如何设置 c-sharp 中工具提示的初始延迟/](https://www.geeksforgeeks.org/how-to-set-the-initial-delay-of-the-tooltip-in-c-sharp/)

在 windows 窗体中，工具提示代表一个微小的弹出框，当您将指针或光标放在控件上时，该框会出现，该控件的目的是提供有关 Windows 窗体中控件的简要说明。在工具提示中，可以使用 **InitialDelay Property** 设置工具提示框弹出前经过的时间。
借助此属性，您可以增加或减少工具提示框出现在控件上之前所花费的时间。该房产最高限价为 *32767* 。您可以通过两种不同的方式设置此属性:

**1。设计时:**设置 InitialDelay 属性的值是最简单的方法，如以下步骤所示:

*   **第一步:**创建如下图所示的窗口表单:
    **Visual Studio->File->New->Project->windows formpp**
    ![](img/de9202f1f4646167e60ea580d67273d9.png)
*   **第 2 步:**从工具箱中拖动工具提示并将其放到表单上。当您将此工具提示拖放到窗体上时，它将自动添加到当前窗口中出现的每个控件的属性(在工具提示 1 中命名为工具提示)中。
    T3】
*   **Step 3:** After drag and drop you will go to the properties of the ToolTip and set the value of the InitialDelay property.
    ![](img/58a49febb80e738c5f80686b42080088.png)

    **输出:**
    ![](img/a9c99fc5a64ebf4384226643a98c7da5.png)

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以借助给定的语法以编程方式设置工具提示的 InitialDelay 属性:

```cs
public int InitialDelay { get; set; }
```

这里，该属性的值为*系统。Int32* 类型，时间周期始终以毫秒为单位。

**注意:**始终将 InitialDelay 属性的值设置为小，因为如果设置较大的值，那么在屏幕上显示将花费更多的时间。由于延迟时间较长，用户无法享受工具提示窗口的好处。
以下步骤展示了如何动态设置工具提示的 InitialDelay 属性:

*   **步骤 1:** 使用 ToolTip()构造函数创建工具提示，该构造函数由 ToolTip 类提供。

    ```cs
    // Creating a ToolTip
    ToolTip t = new ToolTip();

    ```

*   **第二步:**创建工具提示后，设置工具提示类提供的工具提示的 InitialDelay 属性。

    ```cs
    // Setting the InitialDelay property
    t.InitialDelay = 600;

    ```

*   **Step 3:** And last add this ToolTip to the controls using SetToolTip() method. This method contains the control name and the text which you want to display in the ToolTip box.

    ```cs
     t.SetToolTip(box1, "Name should be start with Capital letters");
    ```

    **示例:**

    ```cs
    using System;
    using System.Collections.Generic;
    using System.ComponentModel;
    using System.Data;
    using System.Drawing;
    using System.Linq;
    using System.Text;
    using System.Threading.Tasks;
    using System.Windows.Forms;

    namespace WindowsFormsApp33 {

    public partial class Form1 : Form {

        public Form1()
        {
            InitializeComponent();
        }

        private void Form1_Load(object sender, EventArgs e)
        {
            // Creating and setting the 
            // properties of the Label
            Label l1 = new Label();
            l1.Location = new Point(140, 122);
            l1.Text = "Name";

            // Adding this Label 
            // control to the form
            this.Controls.Add(l1);

            // Creating and setting the 
            // properties of the TextBox
            TextBox box1 = new TextBox();
            box1.Location = new Point(248, 119);
            box1.BorderStyle = BorderStyle.FixedSingle;

            // Adding this TextBox 
            // control to the form
            this.Controls.Add(box1);

            // Creating and setting the 
            // properties of the Label
            Label l2 = new Label();
            l2.Location = new Point(140, 152);
            l2.Text = "Password";

            // Adding this Label 
            // control to the form
            this.Controls.Add(l2);

            // Creating and setting the 
            // properties of the TextBox
            TextBox box2 = new TextBox();
            box2.Location = new Point(248, 145);
            box2.BorderStyle = BorderStyle.FixedSingle;

            // Adding this TextBox 
            // control to the form
            this.Controls.Add(box2);

            // Creating and setting the
            // properties of the ToolTip
            ToolTip t = new ToolTip();
            t.Active = true;
            t.AutoPopDelay = 4000;
            t.InitialDelay = 600;
            t.SetToolTip(box1, "Name should be start with Capital letters");
            t.SetToolTip(box2, "Password should be greater than 8 words");
        }
    }
    }
    ```

    **输出:**

    ![](img/47302d9af4fde14a29574bfff1cb3b67.png)