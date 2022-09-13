---
title: Header Styling
page_title: .NET MAUI DataForm Documentation | Header Styling
description: "Review the available Styling options which DataForm for .NET MAUI control provides for its editors'."
position: 5
slug: dataform-header-styling
---

# .NET MAUI Header Styling

The DatePicker control for .NET MAUI provides styling options for customizing the apperance of the header label or image above each editor.

The style of the Header message can be set individually for each editor or directly to the DataForm control using the following styling properties:

* `HeaderImageSource`(`ImageSource`)&mdash;Specifies the `ImageSource` of the image displayed in the header.
* `HeaderImageStyle`(of type `Style` with target type `Image`)&mdash;Defines the header image style.
* `HeaderLabelStyle`(of type `Style` with target type `Label`)&mdash;Defines the header label style.

## Common Header Styling

**Define a common HeaderLabelStyle**

<snippet id='dataform-header-styling-common-style' />

**Apply the common HeaderLabelStyle to all editors in the DataForm**

<snippet id='dataform-header-styling-common' />

## Individual Header Styling

**Define two different HeaderLabelStyle**

<snippet id='dataform-header-styling-header-style' />

<snippet id='dataform-header-styling-header-style-alt' />

**Apply a style to each editor in the DataForm individually**

<snippet id='dataform-header-styling-individual' />

Add the following namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

The following image shows what the DataForm control looks like when the styles described above are applied:

![.NET MAUI DataForm Header Message Styling](../images/dataform_header_message_styling.png)