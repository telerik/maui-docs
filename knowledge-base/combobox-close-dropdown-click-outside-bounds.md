---
title: Closing the DropDown of the ComboBox on Click Outside Its Bounds
description: Learn how to configure the ComboBox to close its DropDown when the user clicks outside the component's bounds.
type: how-to
page_title: How to Close DropDown of ComboBox on Click Outside Bounds
slug: combobox-close-dropdown-click-outside-bounds
tags: [.NET MAUI, ComboBox, DropDown, Close, Click]
res_type: kb
---

## Environment
| Product | Version |
|---------|---------|
| ComboBox for .NET MAUI | 6.6.0 |

## Description
To close the DropDown of the ComboBox when the user clicks outside of the component's bounds, you can use a workaround that involves attaching a gesture recognizer to the parent layout or main layout in the page and setting the `IsDropDownOpen` property of the ComboBox to `false`.

## Solution
Follow these steps to implement the workaround:

1. In your XAML code, locate the parent layout or main layout that contains the ComboBox.
2. Add a `GestureRecognizer` to the parent layout and subscribe to its `Tapped` event. For example:

```
<VerticalStackLayout>
    <VerticalStackLayout.GestureRecognizers>
        <TapGestureRecognizer Tapped="TapGestureRecognizer_Tapped"/>
    </VerticalStackLayout.GestureRecognizers>
    <!-- Other controls and elements -->
</VerticalStackLayout>
```

3. In the event handler method, set the `IsDropDownOpen` property of the ComboBox to `false`. This will close the DropDown when someone clicks outside its boundaries. For example:

```
private void TapGestureRecognizer_Tapped(object sender, TappedEventArgs e)
{
    this.comboBox.IsDropDownOpen = false;
}
```


## Notes
- This workaround is applicable to both Android and iOS platforms.
- Make sure to replace `comboBox` with the actual name of your ComboBox control in the event handler method.

## See Also
- [ComboBox for .NET MAUI Documentation](https://docs.telerik.com/devtools/maui/controls/combo-box/overview)
