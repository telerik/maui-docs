---
title: Looping
page_title: .NET MAUI ListPicker Documentation - Looping
description: Learn more about the looping functionality that the Telerik UI for .NET MAUI ListPicker control provides.
position: 2
previous_url: /controls/listpicker/listpicker-looping
slug: listpicker-looping
---

# .NET MAUI ListPicker Looping

The ListPicker for .NET MAUI provides a looping functionality which allows you to loop the list of items after reaching the last item.

You can achieve this by setting the `IsLooping`(`bool`) property to `true`.

## Example

**1.** Define the ListPicker:

<snippet id='listpicker-features-looping' />

**2.** Define a sample business model:

<snippet id='listpicker-features-businessmodel' />

**3.** Set the `ViewModel`:

<snippet id='listpicker-features-viewmodel' />

The following image shows the end result.

![ListPicker Looping](images/looping_gif.gif)

>important For a sample looping example, refer to the **ListPicker/Looping** folder of the [Telerik UI for .NET MAUI SDKBrowser Application]({%slug sdkbrowser-app%}).

## See Also

- [Templates]({%slug listpicker-templates%})
- [Styling]({%slug listpicker-styling%})
- [Selection]({%slug listpicker-selection%})
- [Commands]({%slug listpicker-commands%})
