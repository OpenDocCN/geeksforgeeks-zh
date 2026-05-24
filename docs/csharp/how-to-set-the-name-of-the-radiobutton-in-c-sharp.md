# 如何在 C# 中设置单选按钮的名称？

> 原文:[https://www . geeksforgeeks . org/如何设置 c-sharp 中 radiobutton 的名称/](https://www.geeksforgeeks.org/how-to-set-the-name-of-the-radiobutton-in-c-sharp/)

在 Windows 窗体中，单选按钮控件用于从选项组中选择一个选项。例如，从给定的列表中选择您的性别，因此您将在三个选项中仅选择一个选项，如男性或女性或变性者。在 Windows 窗体中，您可以使用单选按钮控件的**名称属性**为您的单选按钮命名。您可以通过两种不同的方式设置此属性:

**1。设计时:**最简单的方法是将名称设置为 RadioButton，如下图截图所示:

*   **第一步:**创建如下图所示的窗口表单:
    **Visual Studio->File->New->Project->windows formpp**
    ![](img/f3cd3ae5c11eb68b3d10b5ab8eec9925.png)
*   **步骤 2:** 从工具箱中拖动 RadioButton 控件，并将其放到 windows 窗体上。您可以根据需要在 windows 窗体上的任何位置放置一个 RadioButton 控件。
    T3】
*   **Step 3:** After drag and drop you will go to the properties of the RadioButton control to set a name to RadioButton.
    ![](img/2fee17d9d8756f5a72bf7d6f90ee227b.png)

    **输出:**
    ![](img/fb0af8616434fe6cdaf2bb84eb98c3a9.png)

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以借助给定的语法以编程方式将名称设置为单选按钮:

```cs
public string Name { get; set; }
```

该属性的值为**系统。字符串**类型，该字符串代表单选按钮的名称。以下步骤显示了如何动态设置单选按钮的名称:

*   **步骤 1:** 使用 RadioButton 类提供的 radio button()构造函数创建单选按钮。

    ```cs
    // Creating radio button
    RadioButton r1 = new RadioButton();

    ```

*   **步骤 2:** 创建单选按钮后，设置单选按钮类提供的单选按钮的 Name 属性。

    ```cs
    // Setting the name of the radio button
    r1.Name = "My_Radio_1";

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

    namespace WindowsFormsApp24 {

    public partial class Form1 : Form {

        public Form1()
        {
            InitializeComponent();
        }

        private void RadioButton2_CheckedChanged(object sender,
                                                  EventArgs e)
        {
        }

        private void Form1_Load(object sender, EventArgs e)
        {
            // Creating and setting label
            Label l = new Label();
            l.AutoSize = true;
            l.Location = new Point(176, 40);
            l.Text = "Select Post:";
            l.Font = new Font("Berlin Sans FB", 12);

            // Adding this label to the form
            this.Controls.Add(l);

            // Creating and setting the 
            // properties of the RadioButton
            RadioButton r1 = new RadioButton();
            r1.AutoSize = true;
            r1.Text = "Intern";
            r1.Name = "My_Radio_1";
            r1.Location = new Point(286, 40);
            r1.Font = new Font("Berlin Sans FB", 12);

            // Adding this label to the form
            this.Controls.Add(r1);

            // Creating and setting the
            // properties of the RadioButton
            RadioButton r2 = new RadioButton();
            r2.AutoSize = true;
            r2.Name = "My_Radio_2";
            r2.Text = "Team Leader";
            r2.Location = new Point(356, 40);
            r2.Font = new Font("Berlin Sans FB", 12);
            // Adding this label to the form
            this.Controls.Add(r2);

            // Creating and setting the
            // properties of the RadioButton
            RadioButton r3 = new RadioButton();
            r3.AutoSize = true;
            r3.Name = "My_Radio_3";
            r3.Text = "Software Engineer";
            r3.Location = new Point(480, 40);
            r3.Font = new Font("Berlin Sans FB", 12);

            // Adding this label to the form
            this.Controls.Add(r3);
        }
    }
    }
    ```

    **输出:**

    ![](img/ead0454b5c3e63a9d416fe34e84857d6.png)