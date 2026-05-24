# HTML 事件属性完整参考

> 原文:[https://www . geesforgeks . org/html-event-attributes-complete-reference/](https://www.geeksforgeeks.org/html-event-attributes-complete-reference/)

**事件**是当用户做某事时在浏览器中发生的动作，例如当用户点击鼠标或在键盘上键入某些内容时。

**事件属性:**在 HTML 中，我们可以在浏览器上使用事件动作，借助事件，用户响应系统。事件属性可以与 HTML 元素一起使用来执行各种操作。

**事件属性列表:**完整的事件属性列表如下:

**1。窗口事件属性**

*   [**onafterprint**](https://www.geeksforgeeks.org/html-onafterprint-event-attribute/)**:**当页面已经开始打印，或者打印对话框已经关闭时，on afterprint 属性工作。该属性与 onbeforeprint 属性一起使用。
*   [**onbeforeprint**](https://www.geeksforgeeks.org/html-onbeforeprint-event-attribute/)**:**onbeforeprint 属性在页面即将打印时有效。在打印对话框出现之前会显示警告消息。onbeforeprint 属性与 onafterprint 属性一起使用。
*   [**onbeforeunload**](https://www.geeksforgeeks.org/html-onbeforeunload-event-attribute/)**:**onbeforeunload 事件在文档即将卸载时运行。此事件用于允许在对话框中显示消息以通知用户，因此他/她想要停留或离开当前页面。
*   [**onerror**](https://www.geeksforgeeks.org/html-onerror-event-attribute/) **:当加载外部文件时出现错误时，此属性有效。外部文件可能包含文档文件或图像文件。**
*   [**onhashchange**](https://www.geeksforgeeks.org/html-onhashchange-event-attribute/)**:**当锚点部分发生变化时，此属性有效。锚点部分以当前网址的“#”符号开始。
*   [**onload**](https://www.geeksforgeeks.org/html-onload-event-attribute/) **:** 当一个对象被加载后，该属性生效。该属性主要用在<主体>元素中来执行脚本。它也可以与其他元素一起使用。此属性用于检查访问者的浏览器类型和浏览器版本，并根据信息加载网页的正确版本。
*   [**on message:**](https://www.geeksforgeeks.org/html-dom-onmessage-event/)**当对象通过事件源接收到一些消息时，使用此事件。**
*   **[**onoffline**](https://www.geeksforgeeks.org/html-onoffline-event-attribute/)**:**当浏览器在离线模式下工作时，on offline 事件属性起作用。仅由<车身>标签支撑。与*在线*事件属性相反。**
*   **[**ononline**](https://www.geeksforgeeks.org/html-ononline-event-attribute/)**:**当浏览器开始在线模式下工作时，on online 事件属性工作。它与 onoffline 事件属性相反。**
*   **[**【on pagehide:**](https://www.geeksforgeeks.org/html-dom-onpagehide-event/)**当用户从网页下车时会发生此事件。比如关闭浏览器窗口、点击链接、刷新页面等。****
*   ****[**onpageshow**](https://www.geeksforgeeks.org/html-onpageshow-event-attribute/)**:**当用户导航到某个网站时，会发生此事件。此事件与 onload 事件非常相似，但它发生在 onload 事件之后。每次加载页面时都会发生此事件，而从缓存加载页面时不会发生 onload 事件。****
*   ****[**onresize**](https://www.geeksforgeeks.org/html-onresize-event-attribute/)**:**onresize 事件属性在每次调整浏览器窗口大小时触发。****
*   ****[**【未加载】**](https://www.geeksforgeeks.org/html-onunload-event-attribute/) **:** 未加载事件属性在文档被卸载时工作，即在浏览器关闭时发生。它主要用于用户打开链接并提交表单以及关闭浏览器窗口时。****

******2。表单事件属性******

*   ****[**on bulr**](https://www.geeksforgeeks.org/html-onblur-attribute/)**:该属性在元素失去焦点的那一刻触发。该属性主要用于表单验证代码中。该属性与 *onfocus* 属性相反。******
*   ****[**onchange:**](https://www.geeksforgeeks.org/html-onchange-event-attribute/)**onchange 事件属性在元素的值发生变化时起作用，并从列表中选择新值。******
*   ******[**on context menu**](https://www.geeksforgeeks.org/html-oncontextmenu-event-attribute/)**:**当用户右键单击某个元素以打开上下文菜单时，该属性起作用。******
*   ****[**onfocus**](https://www.geeksforgeeks.org/html-onfocus-event-attribute/) **:这个 onfocus 属性在元素聚焦时生效。该事件属性多用于<输入>、<选择>、< a >元素。除了<基础>、< bdo >、< br >、<头部>、< html >、< iframe >、< meta >、< param >、<脚本>、<样式>和<标题>元素外，所有 HTML 元素都支持此事件属性******
*   ****[**oninput**](https://www.geeksforgeeks.org/html-oninput-event-attribute/) **:** 该属性在获取用户输入值时生效。该属性主要在用户更改<输入>和<文本区>元素的值时触发。****
*   ****[**on 无效**](https://www.geeksforgeeks.org/html-oninvalid-event-attribute/) **:** 当输入字段值无效或为空时，on 无效事件属性有效。当用户单击提交按钮时，脚本运行。提交前，必须填写必填输入字段。****
*   ****[**onreset:**](https://www.geeksforgeeks.org/html-onreset-event-attribute/) 重置表单时会触发 HTML 中的 onreset 事件属性。该属性与<表单>标签一起使用。****
*   ****[**onsearch**](https://www.geeksforgeeks.org/html-onsearch-event-attribute/)**:**当用户按下 *ENTER* 按钮或点击 *x* 按钮时，此 on search 属性生效。该事件与<输入>元素一起工作。****
*   ****[**【onsele】**](https://www.geeksforgeeks.org/html-onselect-event-attribute/)**:**onsele 事件属性在元素中选择了一些文本时起作用。它是事件属性的一部分。有<输入 type = "file" >、<输入 type = "password" >、<输入 type = "text" >、< textarea >等多种 HTML 元素支持。****
*   ****[**onsubmit**](https://www.geeksforgeeks.org/html-onsubmit-event-attribute/)**:HTML 中的 onsubmit 事件属性在表单提交时触发。******

******3。键盘事件属性******

*   ****[**onkeydown**](https://www.geeksforgeeks.org/html-onkeydown-event-attribute/)**:**这个 onkeydown 事件属性在用户按下键盘上任意一个键时起作用。****
*   ****[**onkeyup**](https://www.geeksforgeeks.org/html-onkeyup-event-attribute/) **:** 这个 onkeyup 事件属性在用户从键盘上释放按键时起作用。****
*   ****[**按下**](https://www.geeksforgeeks.org/html-onkeypress-attribute/) **:** 当用户按下键盘上的一个键时，该属性触发。此事件属性不能用于所有浏览器中的所有按键(如 ALT、CTRL、SHIFT、ESC)。****

******4。鼠标事件******

*   ****[**onclick**](https://www.geeksforgeeks.org/html-onclick-event-attribute/)**:**onclick 事件属性在用户点击按钮时生效。当鼠标点击元素时，脚本运行。****
*   ****[**onmouseout**](https://www.geeksforgeeks.org/html-onmouseout-event-attribute/)**:**当鼠标指针移出指定元素时，onmouseout 属性工作。****
*   ****[**点击**](https://www.geeksforgeeks.org/html-ondblclick-event-attribute/) **:** 当用户在元素上点击鼠标双击时，该属性事件发生。它是事件属性的一部分。****
*   ****[**onmouseover**](https://www.geeksforgeeks.org/html-onmouseover-event-attribute/)**:**当鼠标指针移动到指定元素上时，onmouseover 事件属性生效。****
*   ****[**【onmousedown】**](https://www.geeksforgeeks.org/html-onmousedown-attribute/)**:**当在元素上按下鼠标按钮并且与 onmousedown 事件相关的事件发生顺序(对于左/鼠标按钮)发生时，该 on mousedown 属性将触发****
*   ****[**onmouseup**](https://www.geeksforgeeks.org/html-onmouseup-event-attribute/)**:**当鼠标按钮在元素上释放时，该属性触发。事件发生的顺序与 onmouseup 事件相关。****
*   ****[**onmousemove**](https://www.geeksforgeeks.org/html-onmousemove-event-attribute/)**:**当指针在元素上移动时，onmousemove 属性起作用。****
*   ****[**onwheel**](https://www.geeksforgeeks.org/html-onwheel-event-attribute/) **:** 当指针设备的滚轮在元素上上下滚动时，此属性有效。当用户使用鼠标或触摸板滚动或缩放元素时，onwheel 属性也有效。****

******5。拖动事件属性******

*   ****[**【ondrag】**](https://www.geeksforgeeks.org/html-ondrag-event-attribute/)**:**当在 HTML 中拖动元素或文本选择时，ondrag 事件属性起作用。此事件与拖放事件非常相似。这个属性在 HTML 5 中是新的。****
*   ****[**【ondragstart】**](https://www.geeksforgeeks.org/html-ondragstart-event-attribute/)**:**用于用户想要拖动文本或元素时。简单来说就是我们按下想要的文本，将和拖放到不同的位置。****
*   ****[**【ondragend】**](https://www.geeksforgeeks.org/html-ondragend-event-attribute/)**:**ondragend 事件属性在用户完成元素拖动时工作。拖放功能在 HTML5 中很常见。任何元素都可以通过使用 HTML5 的可拖动属性来进行拖动。****
*   ****[**【on drop】**](https://www.geeksforgeeks.org/html-ondrop-event-attribute/)**:**on drop 事件属性用于将元素或文本拖放到有效的可拖放位置或目标。拖放是 HTML 5 的常见功能。****
*   ****[**【ondragenter】**](https://www.geeksforgeeks.org/html-ondragenter-event-attribute/)**:**当内容可拖动时，HTML 中的 ondragenter 事件属性起作用。通过将可拖动属性值设置为 true 来创建元素。可拖动属性只能取真值或假值。****
*   ****[**滚动**](https://www.geeksforgeeks.org/html-onscroll-attribute/) **:** 当元素滚动条滚动时，该滚动属性起作用。若要在元素中创建滚动条，请使用 CSS 溢出属性。****
*   ****[**【软骨上】**](https://www.geeksforgeeks.org/html-ondragleave-event-attribute/) **:** 当可拖动元素或文本选择离开有效放置目标时，软骨上属性起作用。它有助于拖动元素并进入或离开拖放目标。****
*   ****[](https://www.geeksforgeeks.org/html-dom-ondragover-event/)****:**当一个可拖动元素被拖动到一个有效的拖放区上时，会发生此事件。******

******6。剪贴板事件属性******

*   ****[**oncopy**](https://www.geeksforgeeks.org/html-oncopy-attribute/) **:** 当用户复制了元素中存在的内容时，该属性会触发。oncopy 属性用于< img >、<输入>、< p >等元素。****
*   ****[**【onpaste】**](https://www.geeksforgeeks.org/html-onpaste-event-attribute/)**:**onpaste 属性在某些内容粘贴到一个元素中时有效。所有 HTML 元素都支持此事件属性。多用于<输入>元素。****
*   ****[**oncut**](https://www.geeksforgeeks.org/html-oncut-attribute/) **:** 当用户剪切或删除元素中已经存在的内容时，该属性会触发。它是一个布尔类型属性。所有的 HTML 元素都支持这个属性，但是内容可编辑属性设置为“真”的元素是可能的。****

******7。媒体事件属性******

*   ****[**onabort**](https://www.geeksforgeeks.org/html-dom-onabort-event/) **:** 这发生在当媒体数据的下载没有任何错误地中止时音频/视频加载的中止中。****
*   ****[**oncanplay**](https://www.geeksforgeeks.org/html-dom-oncanplay-event/)**:**当指定的音频/视频被缓冲到足以开始时发生。****
*   ****[**oncanplaythrough**](https://www.geeksforgeeks.org/html-dom-oncanplaythrough-event/) :用于音频/视频等媒体不需要任何缓冲就能播放到最后的情况。****
*   ******one mpted:**事件为空时发生。****
*   ****[](https://www.geeksforgeeks.org/html-onended-event-attribute/)****:**当音频/视频完成时发生。******
*   ****[**on durationchange**](https://www.geeksforgeeks.org/html-dom-ondurationchange-event/)**:**当音频/视频时长发生变化时。****
*   ****[**onerror**](https://www.geeksforgeeks.org/html-dom-onerror-event/) **:** 加载外部文件发生中断时触发。****
*   ****[**加载数据**](https://www.geeksforgeeks.org/html-dom-onloadeddata-event/) **:** 当加载了当前帧数据，但下一帧的数据不足以播放音频/视频时，就会出现这种情况。****
*   ****[**onloaded metadata**](https://www.geeksforgeeks.org/html-dom-onloadedmetadata-event/)**:**为指定的音频/视频加载元数据时发生。****
*   ****[**onload start**](https://www.geeksforgeeks.org/html-dom-onloadstart-event/)**:**指定音频/视频的加载过程开始时发生。****
*   ****[**onpause**](https://www.geeksforgeeks.org/html-dom-onpause-event/) **:** 当音频/视频暂停时出现。音频/视频可以由用户暂停，也可以通过编程暂停。****
*   ****[**【on playevent】**](https://www.geeksforgeeks.org/html-dom-onplay-event/)**:播放音频/视频时出现。音频/视频可以由用户播放，也可以通过编程方式播放。******
*   ****[**【关于播放】**](https://www.geeksforgeeks.org/html-dom-onplaying-event/) **:** 当音频/视频暂停并在缓冲区后播放时出现。****
*   ****[**on progress**](https://www.geeksforgeeks.org/html-dom-onprogress-event/)**:**当浏览器正在下载指定的音频/视频时出现。****
*   ****[**on rate change**](https://www.geeksforgeeks.org/html-onratechange-attribute/)**:**如果音频/视频的播放速度发生变化，就会出现这种情况。playbackRate 属性用于设置或返回音频/视频的当前播放速度。****

******8。杂项事件属性******

*   ****[](https://www.geeksforgeeks.org/html-ontoggle-event-attribute/)****:**当用户打开或关闭<细节>元素时，触发本体事件。<细节>元素用于提供附加信息/细节，用户可以根据需要查看或隐藏细节。******