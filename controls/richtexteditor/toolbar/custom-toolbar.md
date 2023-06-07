---
title: Custom Toolbar
page_title: .NET MAUI RichTextEditor Documentation - Custom Toolbar
description: Check our &quot;RichTextEditor Custom Toolbar&quot; documentation article for Telerik RichTextEditor for .NET MAUI control.
position: 2
slug: richtexteditor-custom-toolbar
---

# RichTextEditor Custom Toolbar

You can easily customize the toolbar by setting the `AutoGenerateItems` to `False`. Then decide which toolbar items to include.

Here is an exmaple with custom toolbar items: 

**1.** RichTextEditor and Toolbar definitions in XAML:

<snippet id='richtexteditor-custom-toolbar-xaml' />

**2.** Add the `telerik` namespaces:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Load the html document in the RichTextEditor:

<snippet id='richtexteditor-toolbar-load-source' />

**4.** And the result:

![.NET MAUI RichTextEditor Custom Toolbar](../images/rte-custom-toolbar.png)

>important For the RichTextEditor Custom Toolbar example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) RichTextEditor -> Toolbar category.

## See Also

- [Commands]({%slug richtexteditor-commands%})
- [Configure the RichTextEditor]({%slug richtexteditor-configuration%})
- [Events]({%slug richtexteditor-events%})
- [Working with images]({%slug richtexteditor-images-overview%})
- [Hyperlinks]({%slug richtexteditor-hyperlink-support%})
