---
title: Selection
page_title: .NET MAUI SegmentedControl Documentation - Selection
description: Check our &quot;Selection&quot; documentation article for Telerik SegmentedControl for NET MAUI control.
slug: segmentedcontrol-selection
tags: selection
position: 2
---

# Selection

The SegmentedControl exposes properties, which can help you work with the items selection.

## Main Properties

* `SelectedIndex`(`int`): Specifies the index of the first item in the current selection or -1 if the selection is empty.
* `SelectedItem`(`object`): Defines the first item in the current selection, or null if the selection is empty.

## Setting the Selection Colors

You can define custom colors for the text and the background of the selected segment by using the `SelectedSegmentBackgroundColor` and `SelectedSegmentTextColor` properties of the SegmentedControl.

## Updating the Selected Item

The SegmentedControl exposes a `SelectionChanged` event, which is fired when the selected item is programmatically changed or updated due to user interaction.

The `SelectionChanged` event handler receives two parameters:
* The sender argument, which is of type `object`, but can be cast to the `RadSegmentedControl` type.
* A `ValueChangedEventArgs&lt;int&gt;` object, which provides the old and new value of the `SelectedIndex`.

## Example

The following example demonstrates how to utilize the selection feature of SegmentedControl.

1. First, create a `ViewModel` class containing the SegmentedControl items and the `int` property for defining the `SelectedIndex`:

<snippet id='segmentcontrol-selection-viewmodel' />


1. Then, add the SegmentedControl definition and apply the `ItemsSource`, `SelectedItem`, and the selection colors properties:

<snippet id='segmentcontrol-selection-xaml' />


1. Lastly, define the `ViewModel` as the `BindingContext` of the control:

 ```C#
this.segmentControl.BindingContext = new ViewModel();
 ```

The image below shows the end result on different platforms:

![SegmentedControl selection](images/segmentcontrol-features-selection-0.png)

## See Also

- [Customizing the Segment Colors]({%slug segmentedcontrol-styling%})
