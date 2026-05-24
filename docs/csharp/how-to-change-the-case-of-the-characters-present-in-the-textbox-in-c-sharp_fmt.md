# 如何在 C# 中改变文本框中出现的字符的大小写？

> 原文：[https://www.geeksforgeeks.org/how-to-change-the-case-of-the-characters-present-in-the-textbox-in-c-sharp/](https://www.geeksforgeeks.org/how-to-change-the-case-of-the-characters-present-in-the-textbox-in-c-sharp/)

在 Windows 窗体中，文本框扮演着重要的角色。在文本框的帮助下，用户可以在应用程序中输入数据，可以是单行的，也可以是多行的。在文本框中，您可以借助`CharacterCasing`属性来更改文本框中显示的内容的大小写，这使得您的文本框更具吸引力。该属性的默认值为`CharacterCasing.Normal`。在 Windows 窗体中，可以通过两种不同的方式设置此属性：

## 设计时

最简单的方法是设置文本框的`CharacterCasing`属性，如下步骤所示：

*   **步骤 1:** 创建窗口表单。
    **Visual Studio -> 文件 -> 新建 -> 项目 -> Windows 窗体应用程序**
*   **步骤 2:** 从工具箱中拖动`TextBox`控件，并将其放到窗口窗体上。您可以根据需要将文本框控件放置在 Windows 窗体上的任何位置。
*   **步骤 3:** 拖放完成后，转到`TextBox`控件的属性窗口，设置其`CharacterCasing`属性。
    ![](img/926dd298b09d8a8ff55c5283a6007a78.png)

**输出:**
    ![](img/6053b77493a681a5a145939ee6aff07f.png)

## 运行时

比上面的方法稍微复杂一点。在此方法中，您可以借助给定的语法以编程方式设置文本框的`CharacterCasing`属性：

```cs
public System.Windows.Forms.CharacterCasing CharacterCasing { get; set; }
```

这里，`CharacterCasing`用于表示`CharacterCasing`枚举值，这些值指定文本框控件是否修改字符的大小写。如果分配给属性的值不在枚举的有效值范围内，它将引发`InvalidEnumArgumentException`。以下步骤用于设置文本框的`CharacterCasing`属性：

*   **步骤 1:** 使用`TextBox`类提供的`TextBox()`构造函数创建一个`TextBox`。

```cs
    // Creating textbox
    TextBox Mytextbox = new TextBox();
```

*   **步骤 2:** 创建文本框后，设置`TextBox`类提供的`CharacterCasing`属性。

```cs
    // Set CharacterCasing property
    Mytextbox.CharacterCasing = CharacterCasing.Upper;
```

*   **步骤 3:** 最后，使用`Add()`方法将此文本框控件添加到窗体。

```cs
    // Add this textbox to form
    this.Controls.Add(Mytextbox);
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

namespace my {

public partial class Form1 : Form {

public Form1()
        {
            InitializeComponent();
        }

private void Form1_Load(object sender, EventArgs e)
        {
            // Creating and setting the properties of Lable1
            Label Mylablel = new Label();
            Mylablel.Location = new Point(96, 54);
            Mylablel.Text = "Enter Name";
            Mylablel.AutoSize = true;
            Mylablel.BackColor = Color.LightGray;

// Add this label to form
            this.Controls.Add(Mylablel);

// Creating and setting the properties of TextBox1
            TextBox Mytextbox = new TextBox();
            Mytextbox.Location = new Point(187, 51);
            Mytextbox.BackColor = Color.LightGray;
            Mytextbox.AutoSize = true;
            Mytextbox.Name = "text_box1";
            Mytextbox.CharacterCasing = CharacterCasing.Upper;

// Add this textbox to form
            this.Controls.Add(Mytextbox);
        }
    }
    }
```

**输出:**

![](img/366dc547f78d1c82b9b43c9995189185.png)