---
title: Spinner
page_title: .NET MAUI TemplatedPicker Documentation | Spinner
description: Check our &quot;Spinner&quot; documentation article for Telerik TemplatedPicker for .NET MAUI.
position: 8
previous_url: /controls/templatedpicker/templatedpicker-spinner
slug: templatedpicker-spinner
---

# Spinner

The Spinner for .NET MAUI is a control which allows you to display items in a list. It also provides an option to loop through its items.

The Spinner is used for the [DatePicker]({%slug datepicker-overview%}), [ListPicker]({%slug listpicker-overview%}). Also you can use it inside the [TemplatedPicker `SelectorTemplate`]({%slug templatedpicker-templates%}).

## Configuration

* `ItemLength`(`double`)&mdash;Defines the length of the items in the spinner.

* `ItemSpacing`(`double`)&mdash;Defines the spacing between the items.

* `IsLooping`(`bool`)&mdash;Defines a value indicating whether the items will loop infinitely while scrolling. By default, the looping is disabled. To enable it, set `IsLooping="True"`.

## Data Binding

* `ItemsSource`(`IList`)&mdash;Defines a collection used to generate the content of the spinner.

* `SelectedItem`(`object`)&mdash;Defines the selected item.

* `SelectedIndex`(`int`)&mdash;Specifies the selected index of the Spinner control.

* `DisplayStringFormat`(`string`)&mdash;Defines the string format that is used to display the items of the spinner.

* `DisplayMemberPath`(`string`)&mdash;Specifies a path to the property that is used to display the items of the spinner.

## Templates

* `ItemTemplate`(`DataTemplate`)&mdash;Defines the template for the spinner items.

* `SelectedItemTemplate`(`DataTemplate`)&mdash;Defines the template for the selected spinner item.

## Styling

* `ItemStyle`(`Style`)&mdash;Defines the style for the spinner items.

* `SelectedItemStyle`(`Style`)&mdash;Defines the style for the selected spinner item.

## Events

The Spinner exposes the `SelectionChanged` event that is raised when the user confirms the selected item.

>important For a sample example with the Spinner control, refer to the **TemplatedPicker/DataBinding** folder of the [Telerik UI for .NET MAUI SDKBrowser Application]({%slug maui-demo-app%}).

## See Also

- [Templates]({%slug templatedpicker-templates%})
