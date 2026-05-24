# 如何在 C# 中设置单选按钮的对齐复选框？

> 原文:[https://www . geeksforgeeks . org/如何设置 c-sharp 中 radiobutton 复选框的对齐方式/](https://www.geeksforgeeks.org/how-to-set-the-alignment-of-checkbox-of-the-radiobutton-in-c-sharp/)

在 Windows 窗体中，单选按钮控件用于从选项组中选择一个选项。例如，从给定的列表中选择您的性别，因此您将在三个选项中仅选择一个选项，如男性或女性或变性者。在 Windows 窗体中，您可以使用单选按钮的**检查对齐属性**来调整单选按钮复选框的对齐方式。
该属性的值由 ContentAlignment 枚举指定，它包含复选框对齐的 9 种不同类型的值，即底部中心、底部左侧、底部右侧、中间中心、中间左侧、中间右侧、顶部中心、顶部左侧和顶部右侧。该属性的默认值为*中左*。您可以通过两种不同的方式设置此属性:

**1。设计时:**最简单的方法是设置单选按钮复选框的对齐方式，如以下步骤所示:

*   **第一步:**创建如下图所示的窗口表单:
    **Visual Studio->File->New->Project->windows formpp**
    ![](img/f3cd3ae5c11eb68b3d10b5ab8eec9925.png)
*   **步骤 2:** 从工具箱中拖动 RadioButton 控件，并将其放到 windows 窗体上。您可以根据需要在 windows 窗体上的任何位置放置一个 RadioButton 控件。
    T3】
*   **Step 3:** After drag and drop you will go to the properties of the RadioButton control to set the alignment of the checkbox of the RadioButton.
    ![](img/d0d48948d2aab240a8ad58bf1c7c4edc.png)

    **输出:**
    ![](img/b4fd2aa0b663d30c33ced4bb640769d9.png)

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以借助给定的语法以编程方式设置单选按钮控件的复选框的对齐方式:

```cs
public System.Drawing.ContentAlignment CheckAlign { get; set; }
```

这里，内容对齐是内容对齐的值。如果该值不属于 ContentAlignment 的值，它将引发*InvalidEnumArgumentException*。以下步骤显示了如何动态设置单选按钮复选框的对齐方式:

*   **步骤 1:** 使用 RadioButton 类提供的 radio button()构造函数创建单选按钮。

    ```cs
    // Creating radio button
    RadioButton r1 = new RadioButton();

    ```

*   **步骤 2:** 创建单选按钮后，设置单选按钮类提供的单选按钮的 CheckAlign 属性。

    ```cs
    // Setting the alignment of the checkbox of the radio button
    r1.CheckAlign = ContentAlignment.BottomCenter;

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
            r1.CheckAlign = ContentAlignment.BottomCenter;

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
            r2.CheckAlign = ContentAlignment.BottomCenter;

            // Adding this label to the form
            this.Controls.Add(r2);
        }
    }
    }
    ```

    **输出:**

    ![](img/87c19940a9782df41321587f987b553b.png)