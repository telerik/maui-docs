---
title: Headers
page_title: .NET MAUI DataForm Documentation | Headers
description: "Check our &quot;Headers&quot; documentation article for Telerik .NET MAUI DataForm control."
position: 8
slug: dataform-headers
---

# .NET MAUI DataForm Headers

DataForm has a headers for the Editors and for the Groups. 

## Header in Editors

Each Editor has a header.

* `HeaderText`(`string`)&mdash;Specifies the text of the header.
* `HeaderLength`(`Microsoft.Maui.GridLength?`)&mdash;Specifies the image in the header.
* `HeaderImageSource`(`Microsoft.Maui.Controls.ImageSource`)&mdash;Specifies the image in the header.
* `HeaderPosition`(`Telerik.Maui.Control.DataFormHeaderPosition?`)&mdash;Specifies the postion of the header.
	* `Above`&mdash;The header label is placed above the input component in the Editor.
	* `Beside`&mdash;The header label is placed beside the input component in the Editor.

* `HeaderDisplayOptions`(`Telerik.Maui.Controls.DataFormHeaderDisplayOptions`)&mdash;Specifies the display options of the header. The available options are:
	* `None`&mdash;Header image and text are not visualzied.
	* `Text`&mdash;Visualizes the header text. For this option `HeaderText` has to be defined.
	* `Image`&mdash;Visualizes the image in the header. For this option `HeaderImageSource` has to be defined.

You can combine the `Text` and the `Image` in the ``HeaderDisplayOptions`:

```XAML
HeaderDisplayOptions="Image, Text"
```

* `HeaderTemplate`(`Microsoft.Maui.Controls.ControlTemplate`)&mdash;Specifies the template of the header view.

>note All Header properties for he Editors can be applied directly in the DataForm control and they will be common for all editors.

### Styling

For all styling options applied to the headers in the DataForm Editors review the DataForm [Header Styling]() artile.

## Header for Groups

Each group has a header. Here are the properties you can use to configure the group header:

* `HeaderText`(`string`)&mdash;Specifies the text of the header.
* `HeaderImageSource`(`Microsoft.Maui.Controls.ImageSource`)&mdash;Specifies the image in the header.
* `HeaderDisplayOptions`(`Telerik.Maui.Controls.DataFormHeaderDisplayOptions`)&mdash;Specifies the display options of the header. The available options are:
	* `None`&mdash;Header image and text are not visualzied.
	* `Text`&mdash;Visualizes the header text. For this option `HeaderText` has to be defined.
	* `Image`&mdash;Visualizes the image in the header. For this option `HeaderImageSource` has to be defined.

You can combine the `Text` and the `Image` in the ``HeaderDisplayOption`:

```XAML
HeaderDisplayOptions="Image, Text"
```

* `HeaderTemplate`(`Microsoft.Maui.Controls.ControlTemplate`)&mdash;Specifies the template of the header view.

### Styling

For all styling options applied to the headers in the DataForm Groups review the DataForm [Header Styling]() artile.

