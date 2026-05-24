# 如何在 C# 中设置按钮的边距？

> 原文:[https://www . geeksforgeeks . org/如何设置 c-sharp 中按钮的边距/](https://www.geeksforgeeks.org/how-to-set-the-margin-of-the-buttons-in-c-sharp/)

按钮是应用程序、软件或网页的重要组成部分。它允许用户与应用程序或软件交互。在按钮中，您可以使用**边距属性**设置两个或多个按钮控件之间的间距。您可以在两种不同的方法中使用此属性:

**1。设计时:**设置两个按钮控件之间的边距是最简单的方法。使用以下步骤:

*   **第一步:**创建如下图所示的窗口表单:
    **Visual Studio->File->New->Project->windows formpp**
    ![](img/9889dfd1d09174ca813cf58170ab9cc8.png)
*   **步骤 2:** 从工具箱中拖动按钮控件，并将其放到窗口窗体上。您可以根据需要将按钮控件放置在窗口窗体的任何位置。
    T3】
*   **Step 3:** After drag and drop you will go to the properties of the Button control to set the Margin property of the Button.
    ![](img/03bf29b5f3605c2e708b6f035fb56716.png)

    **输出:**
    ![](img/ff3240db4c200ca4dbcf871b163a5d5e.png)

**运行时间:**比上面的方法稍微复杂一点。在此方法中，您可以在给定语法的帮助下以编程方式设置按钮的 Margin 属性:

```cs
public System.Windows.Forms.Padding Margin { get; set; }
```

这里，填充用于表示控件之间的空间。以下步骤用于设置按钮的边距属性:

*   **步骤 1:** 使用 button 类提供的 Button()构造函数创建按钮。

    ```cs
    // Creating Button using Button class
    Button MyButton = new Button();

    ```

*   **步骤 2:** 创建按钮后，设置按钮类提供的按钮的边距属性。

    ```cs
    // Set the margin of the button
    Mybutton.Margin = new Padding(5, 5, 5, 5);

    ```

*   **Step 3:** And last add this button control to form using Add() method.

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
            l.Font = new Font("French Script MT", 18);
            // Adding this label to form
            this.Controls.Add(l);

            // Creating and setting the properties of Button
            Button Mybutton = new Button();
            Mybutton.Location = new Point(225, 198);
            Mybutton.Text = "Submit";
            Mybutton.AutoSize = true;
            Mybutton.BackColor = Color.LightBlue;
            Mybutton.Padding = new Padding(6);
            Mybutton.Font = new Font("French Script MT", 18);
            Mybutton.Margin = new Padding(5, 5, 5, 5);
            // Adding this button to form
            this.Controls.Add(Mybutton);

            // Creating and setting the properties of Button
            Button Mybutton1 = new Button();
            Mybutton1.Location = new Point(360, 198);
            Mybutton1.Text = "Cancel";
            Mybutton1.AutoSize = true;
            Mybutton1.BackColor = Color.LightPink;
            Mybutton1.Padding = new Padding(6);
            Mybutton1.Font = new Font("French Script MT", 18);
            Mybutton1.Margin = new Padding(5, 5, 5, 5);
            // Adding this button to form
            this.Controls.Add(Mybutton1);
        }
    }
    }
    ```

    **输出:**
    ![](img/5d1422fe35bfdc7327f02d2638bce7d9.png)