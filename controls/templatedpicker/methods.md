---
title: Methods
page_title: .NET MAUI TemplatedPicker Documentation - Methods
description: Check our &quot;Methods&quot; documentation article for Telerik TemplatedPicker for .NET MAUI.
position: 6
previous_url: /controls/templatedpicker/templatedpicker-methods
slug: templatedpicker-methods
---

# .NET MAUI TemplatedPicker Methods

The TemplatedPicker for .NET MAUI allows you to clear the selected value through its `ClearSelection` method.

1. Define the TemplatedPicker:

 ```XAML
<VerticalStackLayout>
    <Button Clicked="OnClearSelectionClicked" Text="clear selection"/>
    <telerik:RadTemplatedPicker x:Name="picker">
        <telerik:RadTemplatedPicker.SelectorTemplate>
            <ControlTemplate>
                <telerik:RadCalendar SelectedDate="{TemplateBinding SelectedValue, Mode=TwoWay}"/>
            </ControlTemplate>
        </telerik:RadTemplatedPicker.SelectorTemplate>
    </telerik:RadTemplatedPicker>
</VerticalStackLayout>
 ```

1. Clear the selection inside the button `click` event:

 ```C#
private void OnClearSelectionClicked(object sender, EventArgs e)
{
    this.picker.ClearSelection();
}
 ```

1. Add the following namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```



## See Also

- [Events]({%slug templatedpicker-events%})
- [Commands]({%slug templatedpicker-commands%})
