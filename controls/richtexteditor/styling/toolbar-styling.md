---
title: Toolbar Styling
page_title: .NET MAUI RichTextEditor Documentation - RichTextEditor Toolbar Styling
description: Check our &quot;RichTextEditor Toolbar Styling&quot; documentation article for Telerik RichTextEditor for .NET MAUI control.
position: 2
slug: richtexteditor-toolbar-styling
---

## RichTextEditor Toolbar Styling

RichTextEditor for .NET MAUI provudes a flexible styling API for its toolbar items. 

In general the RichTextEditorToolbar is based on the RadToolbar control. All toolbar items in the RichTextEditor inherit from `ButtonToolbarItem`.

All styling properties available for the `ButtonToolbarItem` are applicable for the richtext editor toolbar items. For more details review the ButtonToolbar Styling article. 

Here is an example:

**1.** RichTextEditor and Toolbar definitions in xaml:

<snippet id='richtexteditor-toolbar-styling-xaml' />

**2.** Add the `telerik` namespaces:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** And the Styles in the Resources of the page :

<snippet id='richtexteditor-toolbar-styling-resource' />

**4.** This is the result:

![RichTextEditor Toolbar Styling](../images/rte-toolbar-styling.png)

>important For the RichTextEditor Toolbar Styling example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) RichTextEditor -> styling category.


## See Also
