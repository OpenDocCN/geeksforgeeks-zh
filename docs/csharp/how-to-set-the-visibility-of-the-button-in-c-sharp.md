# 如何在 C# 中设置按钮的可见性？

> 原文:[https://www . geeksforgeeks . org/如何设置 c-sharp 中按钮的可见性/](https://www.geeksforgeeks.org/how-to-set-the-visibility-of-the-button-in-c-sharp/)

按钮是应用程序、软件或网页的重要组成部分。它允许用户与应用程序或软件交互。在按钮中，您可以使用**可见属性**设置代表按钮及其子按钮显示的值。它由 Button 类提供。
如果要显示给定的按钮及其子控件，则将 Visible 属性的值设置为 true，否则设置为 false。此属性的默认值为真。您可以在两种不同的方法中使用此属性:

**1。设计时:**设置按钮的可见性是最简单的方法。使用以下步骤:

*   **第一步:**创建如下图所示的窗口表单:
    **Visual Studio->File->New->Project->windows formpp**
    ![](img/9889dfd1d09174ca813cf58170ab9cc8.png)
*   **步骤 2:** 从工具箱中拖动按钮控件，并将其放到窗口窗体上。您可以根据需要将按钮控件放置在窗口窗体的任何位置。
    T3】
*   **Step 3:** After drag and drop you will go to the properties of the Button control to set the Visible property of the Button.
    ![](img/44cdcc7f3aa80af3795e648a01876bcc.png)

    **输出:**
    ![](img/ff3240db4c200ca4dbcf871b163a5d5e.png)

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以借助给定的语法以编程方式设置按钮的可见属性:

```cs
public bool Visible { get; set; }
```

这里这个属性的返回类型是*系统。布尔*。以下步骤用于设置按钮的可见属性:

*   **步骤 1:** 使用 button 类提供的 Button()构造函数创建按钮。

    ```cs
    // Creating Button using Button class
    Button MyButton = new Button();

    ```

*   **步骤 2:** 创建按钮后，设置按钮类提供的按钮的可见属性。

    ```cs
    // Set the visibility of the button
    MyButton.Visible = true;

    ```

*   **Step 3:** And last add this button control to from using Add() method.

    ```cs
    // Add this Button to form
    this.Controls.Add(Mybutton);

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

    namespace WindowsFormsApp8 {

    public partial class Form1 : Form {

        public Form1()
        {
            InitializeComponent();
        }

        private void Form1_Load(object sender, EventArgs e)
        {

            // Creating and setting the properties of label
            Label l = new Label();
            l.AutoSize = true;
            l.Text = "Do you want to submit this form?";
            l.Location = new Point(222, 145);

            // Adding this label to form
            this.Controls.Add(l);

            // Creating and setting the properties of Button
            Button Mybutton = new Button();
            Mybutton.Location = new Point(225, 198);
            Mybutton.Text = "Submit";
            Mybutton.AutoSize = true;
            Mybutton.BackColor = Color.LightBlue;
            Mybutton.Visible = true;

            // Adding this button to form
            this.Controls.Add(Mybutton);

            // Creating and setting the properties of Button
            // This button in not visible in the output because the
            // visibility of this button is set to be false
            Button Mybutton1 = new Button();
            Mybutton1.Location = new Point(438, 198);
            Mybutton1.Text = "Cancel";
            Mybutton1.AutoSize = true;
            Mybutton1.BackColor = Color.LightPink;
            Mybutton1.Visible = false;

            // Adding this button to form
            this.Controls.Add(Mybutton1);
        }
    }
    }
    ```

    **输出:**
    在将取消按钮的可见性设置为假之前，输出如下:
    ![](img/9d8ee370508c964a783310e27f30fba1.png)

    将取消按钮的可见性设置为假后，输出如下:
    ![](img/52afce37d31b6ae9dba0cb60763f84a2.png)