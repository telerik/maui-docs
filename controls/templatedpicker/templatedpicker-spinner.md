---
title: Spinner
page_title: .NET MAUI TemplatedPicker Documentation | Spinner
description: Check our &quot;Spinner&quot; documentation article for Telerik TemplatedPicker for .NET MAUI.
position: 8
slug: templatedpicker-spinner
---

# Spinner

**RadSpinner for .NET MAUI** is a control which allows you to display items in a list. It also provides an option to loop through its items. RadSpinner control is used for the [DatePicker]({%slug datepicker-overview%}), [ListPicker]({%slug listpicker-overview%}). Also is could be used inside the [TemplatedPicker SelectorTemplate]({%slug templatedpicker-templates%}). 

## Configuration

* `ItemLength`(*double*): Defines the length of the items in the spinner.

* `ItemSpacing`(*double*): Defines the spacing between the items.

* `IsLooping`(*bool*): Defines a value indicating whether the items should loop infinitely while scrolling. By default the looping is disabled. In order to enable it set *IsLooping="True"*.

## Data Binding

* `ItemsSource`(*IList*): Defines a collection used to generate the content of the spinner.

* `SelectedItem`(*object*): Defines the selected item.

* `SelectedIndex`(*int*): Specifies the selected index of the Spinner control.

* `DisplayStringFormat`(*string*): Defines the string format used to display the items of the spinner.

* `DisplayMemberPath`(*string*): Specifies a path to the property used to display the items of the spinner

## Templates

* `ItemTemplate`(*DataTemplate*): Defines the template for the spinner items

* `SelectedItemTemplate`(*DataTemplate*): Defines the template for spinner selected item

## Styling

* `ItemStyle`(*Style*): Defines the style for the spinner items.

* `SelectedItemStyle`(*Style*): Defines the style for the spinner selected item.

## Events

* `SelectionChanged`: Raised when the user confirms the selected item.


>important Sample example with RadSpinner control can be found in the TemplatedPicker/DataBinding folder of the [Telerik UI for .NET MAUI SDKBrowser Application]({%slug maui-demo-app%}).

## See Also

- [Templates]({%slug templatedpicker-templates%})