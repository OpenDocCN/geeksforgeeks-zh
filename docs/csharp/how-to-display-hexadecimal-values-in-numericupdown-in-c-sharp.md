# 如何在 C# 中用 NumericUpDown 显示十六进制值？

> 原文:[https://www . geeksforgeeks . org/如何显示十六进制数值-in-numeric pdown-in-c-sharp/](https://www.geeksforgeeks.org/how-to-display-hexadecimal-values-in-numericupdown-in-c-sharp/)

在 Windows 窗体中，NumericUpDown 控件用于提供显示数值的 Windows 旋转框或上下控件。或者换句话说，NumericUpDown 控件提供了一个使用上下箭头移动并保存一些预定义数值的界面。在 NumericUpDown 控件中，可以使用**十六进制属性**在上下控件中显示十六进制格式的值。
如果该属性的值设置为 true，则上下控件以十六进制格式显示值。如果此属性的值设置为 false，则上下控件不会以十六进制格式显示值。此属性的默认值为 false。您可以通过两种不同的方式设置此属性:

**1。设计时:**最简单的方法是在 NumericUpDown 中设置十六进制值，如以下步骤所示:

*   **Step 1:** Create a windows form as shown in the below image:
    **Visual Studio -> File -> New -> Project -> WindowsFormApp**

    ![](img/de9202f1f4646167e60ea580d67273d9.png)

*   **Step 2:** Next, drag and drop the NumericUpDown control from the toolbox on the form as shown in the below image:

    ![](img/e130871c36b969be4b9cf9ab8e45a276.png)

*   **Step 3:** After drag and drop you will go to the properties of the NumericUpDown and set the hexadecimal values in the NumericUpDown as shown in the below image:

    ![](img/f7b7d89e766bd2d4931741dcf3ae65a0.png)

    **输出:**

    ![](img/5c416a656f66fddcb4d92a71123aa5c8.png)

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以在给定语法的帮助下，以编程方式在 NumericUpDown 控件中设置十六进制格式:

```cs
public bool Hexadecimal { get; set; }
```

该属性的值为*系统。布尔*类型，非真即假。以下步骤显示了如何动态设置 NumericUpDown 中的十六进制值:

*   **步骤 1:** 使用 numericpdown()构造函数创建 numericpdown，该构造函数由 numericpdown 类提供。

    ```cs
    // Creating a NumericUpDown
    NumericUpDown n = new NumericUpDown();

    ```

*   **第 2 步:**创建 numericpdown 后，设置 numericpdown 类提供的 numericpdown 的十六进制属性。

    ```cs
    // Setting the Hexadecimal values
    n.Hexadecimal = true; 

    ```

*   **Step 3:** And last add this NumericUpDown control to the form using the following statement:

    ```cs
    // Adding NumericUpDown control on the form
    this.Controls.Add(n);

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

    namespace WindowsFormsApp44 {

    public partial class Form1 : Form {

        public Form1()
        {
            InitializeComponent();
        }

        private void Form1_Load(object sender, EventArgs e)
        {

            // Creating and setting the
            // properties of the labels
            Label l1 = new Label();
            l1.Location = new Point(348, 61);
            l1.Size = new Size(215, 25);
            l1.Text = "Example";
            l1.Font = new Font("Bodoni MT", 16);
            this.Controls.Add(l1);

            Label l2 = new Label();
            l2.Location = new Point(242, 136);
            l2.Size = new Size(103, 20);
            l2.Text = "Select value:";
            l2.Font = new Font("Bodoni MT", 12);
            this.Controls.Add(l2);

            // Creating and setting the
            // properties of NumericUpDown
            NumericUpDown n = new NumericUpDown();
            n.Location = new Point(386, 130);
            n.Size = new Size(126, 26);
            n.Font = new Font("Bodoni MT", 12);
            n.Value = 18;
            n.Minimum = 18;
            n.Maximum = 30;
            n.Increment = 1;
            n.Hexadecimal = true;

            // Adding this control
            // to the form
            this.Controls.Add(n);
        }
    }
    }
    ```

    **输出:**

    ![](img/70bf3dc9a658788e3b7f61d47aa2d68b.png)