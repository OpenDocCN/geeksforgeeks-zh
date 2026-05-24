# 如何在 C# 中设置列表框边框的样式？

> 原文:[https://www . geeksforgeeks . org/如何设置 c-sharp 中列表框的边框样式/](https://www.geeksforgeeks.org/how-to-style-the-border-of-listbox-in-c-sharp/)

在 Windows 窗体中，ListBox 控件用于显示列表中的多个元素，用户可以从中选择一个或多个元素，这些元素通常显示在多个列中。在列表框中，您可以使用列表框的**边框样式属性**来设置列表框的边框样式，这将使您的列表框更具吸引力。您可以通过两种不同的方式设置此属性:

**1。设计时:**这是为列表框中的内容设置边框样式的最简单方法，如以下步骤所示:

*   **第一步:**创建如下图所示的窗口表单:
    **Visual Studio->File->New->Project->windows formpp**
    ![](img/52a0adebea6c33bdc662683df034f77e.png)
*   **步骤 2:** 从工具箱中拖动 ListBox 控件，并将其放到 windows 窗体上。根据您的需要，您可以将列表框控件放在窗口窗体的任何位置。
    T3】
*   **Step 3:** After drag and drop you will go to the properties of the ListBox control to style the border of the ListBox.
    ![](img/a31e21406b83a9e62a38c72ad0991ffb.png)

    **输出:**
    ![](img/2e9e93d695c7d0ced399ecef3606a9df.png)

**2。RunTime:** 比上面的方法稍微复杂一点。在此方法中，您可以在给定语法的帮助下，以编程方式设置 ListBox 控件的边框样式:

```cs
public System.Windows.Forms.BorderStyle BorderStyle { get; set; }
```

这里，边框样式指示边框样式的值，这些值是:

*   **固定 3D:** 用于三维边框。
*   **固定单线:**为单线边框。
*   **无:**为无边框。

如果该属性的值不属于 BorderStyle，它将引发*InvalidEnumArgumentException*。以下步骤显示了如何动态设置列表框边框的样式:

*   **步骤 1:** 使用 list box 类提供的 ListBox()构造函数创建列表框。

    ```cs
    // Creating ListBox using ListBox class constructor
    ListBox mylist = new ListBox();

    ```

*   **步骤 2:** 创建 ListBox 后，设置 ListBox 类提供的 ListBox 的 BorderStyle 属性。

    ```cs
    // Setting the BorderStyle of the ListBox
    mylist.BorderStyle = BorderStyle.Fixed3D;

    ```

*   **Step 3:** And last add this ListBox control to the form using Add() method.

    ```cs
    // Add this ListBox to the form
    this.Controls.Add(mylist);

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

    namespace WindowsFormsApp26 {

    public partial class Form1 : Form {

        public Form1()
        {
            InitializeComponent();
        }

        private void Form1_Load(object sender, EventArgs e)
        {
            // Creating and setting 
            // the properties of ListBox
            ListBox mylist = new ListBox();
            mylist.Location = new Point(287, 109);
            mylist.Size = new Size(120, 95);
            mylist.BorderStyle = BorderStyle.Fixed3D;
            mylist.Items.Add("Geeks");
            mylist.Items.Add("GFG");
            mylist.Items.Add("GeeksForGeeks");
            mylist.Items.Add("gfg");

            // Adding ListBox control to the form
            this.Controls.Add(mylist);
        }
    }
    }
    ```

    **输出:**

    ![](img/ab9c8963ef51411d67c9b2149c735cdd.png)