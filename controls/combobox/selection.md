---
title: Selection
page_title: .NET MAUI ComboBox Documentation - Selection
description: Check our &quot;Selection&quot; documentation article for Telerik ComboBox for .NET MAUI control.
position: 6
slug: combobox-selection
---

# Selection

ComboBox for .NET MAUI enables the app users to quickly and easily select item/items fro a dropdown list. This topic will go through the provided by the ComboBox API related to item/items selection.

ComboBox control has a support for single and multiple selection. You can easily specify the required selection using the `SelectionMode` property.

## Main Properties

* `SelectionMode` (enumeration of type `Telerik.Maui.Controls.ComboBoxSelectionMode`): Defines whether the selection is single or multiple.
* `SelectedIndex`(`int`): Specifies the index of the first item in the current selection or -1 if the selection is empty.
* `SelectedItem`(`object`): Defines the first item in the current selection, or null if the selection is empty.
* `SelectedItems`(`readonly ObservableCollection &lt;object &gt;`): Gets the collection of currently Selected Items. 

> `SelectedItems` collection can be changed only when `SelectionMode` is `Multiple`. For `Single` `SelectionMode` use `SelectedItem`.

## Single Selection

The default `SelectinMode`(enumeration of type `Telerik.Maui.Controls.ComboBoxSelectionMode`) of the ComboBox control is `Single`.

### Example with Single Selection and SelectedIndex set

Here is the ComboBox definition in XAML:

<snippet id='combobox-single-selection-selectedindex'/>

you need to add the following namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

the sample business model

<snippet id='combobox-city-businessmodel'/>

and the ViewModel used:

<snippet id='combobox-cities-viewmodel'/>

This is how single selection looks:

![ComboBox Single Selection](images/dropdown-single-selection.png)

### Example with Single Selection and SelectedItem set

Here is the ComboBox definition in XAML:

<snippet id='combobox-single-selection-selecteditem'/>


the sample business model

<snippet id='combobox-city-businessmodel'/>

and the ViewModel used:

<snippet id='combobox-cities-viewmodel'/>

## Multiple Selection

If you want to achieve multiple selection you will need to set the `SelectionMode` to `Multiple`. The multiple selected items are visualized inside tokens.

>important As the SelectedItems collection is read-only, in order to be notified when the collection is changed, you should listen to the  `CollectionChanged` event of the `SelectedItems`.

### Example with Multiple Selection and SelectedItems set

Here is the ComboBox definition in XAML:

<snippet id='combobox-multiple-selection'/>

the sample business model

<snippet id='combobox-city-businessmodel'/>

and the ViewModel used:

<snippet id='combobox-cities-viewmodel'/>

This is how multiple selection looks: 

![ComboBox Multiple Selection](images/combobox-multiple-selection-selecteditems.png)

>important The Selection example can be found in our [SDK Browser Application]({%slug sdkbrowser-app%}). You can find the applications in the **Examples** folder of your local **Telerik UI for .NET MAUI** installation or in the following [GitHub repo](https://github.com/telerik/maui-samples/tree/main/Samples/SdkBrowser).

## Events

ComboBox exposes a `SelectionChanged` event which is raised when item is selected.

The `SelectionChanged` event handler receives two parameters:

- The `sender` which is the RadComboBox control.
- ComboBoxSelectionChangedEventArgs provides the following properties:
	- `AddedItems`: the items added to the SelectedItemsCollection
	- `RemovedItems`: the items removed from the SelectedItmesCollection

## Commands

ComboBox has two commands related to the Selection feature:

- `SelectAllCommand`(`ICommand`): Selects all items from the source.
- `ClearSelectionCommand`(`ICommand`): Sets the selection to null. If Multiple SelectionMode is used, this command will clear all selected items.

## See Also

- [Configuration]({%slug combobox-configuration%})
- [Data Binding]({%slug combobox-databinding%})
- [Edit Mode & Search]({%slug combobox-editmode-and-search%}) 
- [Templates]({%slug combobox-templates%})
