# 如何在 C# 中设置单选按钮的填充？

> 原文:[https://www . geesforgeks . org/如何设置 c-sharp 中 radiobutton 的填充符/](https://www.geeksforgeeks.org/how-to-set-the-padding-of-the-radiobutton-in-c-sharp/)

在 Windows 窗体中，单选按钮控件用于从选项组中选择一个选项。例如，从给定的列表中选择您的性别，因此您将在三个选项中仅选择一个选项，如男性或女性或变性者。在 Windows 窗体中，您可以使用单选按钮的**填充属性**来调整单选按钮的填充。这里，填充是内容和单选按钮边界之间的空间。您可以通过两种不同的方式设置此属性:

**1。设计时间:**调整单选按钮的填充是最简单的方法，如下所示:

*   **第一步:**创建如下图所示的窗口表单:
    **Visual Studio->File->New->Project->windows formpp**
    ![](img/f3cd3ae5c11eb68b3d10b5ab8eec9925.png)
*   **步骤 2:** 从工具箱中拖动 RadioButton 控件，并将其放到 windows 窗体上。您可以根据需要在 windows 窗体上的任何位置放置一个 RadioButton 控件。
    T3】
*   **Step 3:** After drag and drop you will go to the properties of the RadioButton control to adjust the padding of RadioButton.
    ![](img/1a898e6046bc1a5b56ddb75e579a3f97.png)

    **输出:**
    ![](img/972d06264d384a5c54d44733f58f440c.png)

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以借助给定的语法以编程方式调整 RadioButton 控件的填充:

```cs
public System.Windows.Forms.Padding Padding { get; set; }
```

这里，填充表示文本和单选按钮边界之间的空间。以下步骤显示了如何动态调整单选按钮的填充:

*   **步骤 1:** 使用 RadioButton 类提供的 radio button()构造函数创建单选按钮。

    ```cs
    // Creating radio button
    RadioButton r1 = new RadioButton();

    ```

*   **步骤 2:** 创建单选按钮后，设置单选按钮类提供的单选按钮的 Padding 属性。

    ```cs
    // Setting the padding of the radio button
    r1.Padding = new Padding(6, 6, 6, 6);

    ```

*   **Step 3:** And last add this RadioButton control to the form using Add() method.

    ```cs
    // Add this radio button to the form
    this.Controls.Add(r1);

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

    namespace WindowsFormsApp23 {

    public partial class Form1 : Form {

        public Form1()
        {
            InitializeComponent();
        }

        private void Form1_Load(object sender, EventArgs e)
        {
            // Creating and setting label
            Label l = new Label();
            l.AutoSize = true;
            l.Location = new Point(176, 40);
            l.Text = "Select Post";

            // Adding this label to the form
            this.Controls.Add(l);

            // Creating and setting the
            // properties of the RadioButton
            RadioButton r1 = new RadioButton();
            r1.AutoSize = true;
            r1.Text = "Intern";
            r1.Location = new Point(286, 40);
            r1.BackColor = Color.LightSteelBlue;
            r1.Padding = new Padding(6, 6, 6, 6);

            // Adding this label to the form
            this.Controls.Add(r1);

            // Creating and setting the 
            // properties of the RadioButton
            RadioButton r2 = new RadioButton();
            r2.Text = "Team Leader";
            r2.Location = new Point(400, 40);
            r2.AutoSize = true;
            r2.BackColor = Color.LightSteelBlue;
            r2.Padding = new Padding(6, 6, 6, 6);

            // Adding this label to the form
            this.Controls.Add(r2);
        }
    }
    }
    ```

    **输出:**

    设置填充前:
    ![](img/fa654cfc28bae61f0d2d00034270f6fd.png)

    设置填充后:
    ![](img/8b543ff77fa49b21df7fcf0a1bf7f8f7.png)