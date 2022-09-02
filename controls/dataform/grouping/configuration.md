---
title: Configuration
page_title: .NET MAUI DataForm Documentation | Configuration
description: Check our &quot;Configuration&quot; documentation article for Telerik DataForm for .NET MAUI control.
position: 0
slug: dataform-configuration
---

# Configuration

The DataForm control for .NET MAUI provides the following properties to configure and customize the groups appearance. 

* `GroupName`(`string`)Specified the unique name of the group.
* `Spacing`(`double`)&mdash;Specifies the spacing in pixels between the header view and the content view(where the editors are defined).

## Header

Each group has a header. Here are the properties you can use to configure the group header:

* `HeaderText`(`string`)&mdash;Specifies the text of the header.
* `HeaderImageSource`(`Microsoft.Maui.controls.ImageSource`)&mdash;Specifies the image in the header.
* `HeaderDisplayOptions`(`Telerik.Maui.Controls.DataFormHeaderDisplayOptions`)&mdash;Specifies the display options of the header. The available options are:
	* `None`&mdash;Header image and text are not visualzied.
	* `Text`&mdash;Visualizes the header text. For this option `HeaderText` has to be defined.
	* `Image`&mdash;Visualizes the image in the header. For this option `HeaderImageSource` has to be defined.

** Example for Header options**

<snippet id='dataform-grouping-configuration-header'/>

## Layouts

DataGormd supports different group layouts. You can easily apply a layout to a particular group by setting the `LayoutDefinition` property to the DataFormGroup. The available layouts are described in the [DataForm Layouts](%slug dataform-layouts%) article.

This is an example when the `DataFormGroup.LayoutDefinition` is set to `DataFormGridLayout`:

<snippet id='dataform-grouping-configuration-layout'/>

## Templates

* `HeaderTemplate`(`Microsoft.Maui.Controls.ControlTemplate`)&mdash;Specifies the template of the header view.
* `ContentTemplate`(`Microsoft.Maui.Controls.ControlTemplate`)&mdash;Specifies the template of the content view. The view where the editors are defined.

**Example for HeaderTemplate**

<snippet id='dataform-grouping-configuration-header-template'/>

## Styling

You can fully cusomize the groups using the flexible styling API. For more details review the [Groups Styling]() article.

## See Also