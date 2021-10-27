---
title: Methods
page_title: .NET MAUI TemplatedPicker Documentation | Methods
description: Check our &quot;Methods&quot; documentation article for Telerik TemplatedPicker for .NET MAUI.
position: 6
slug: templatedpicker-methods
---

# Methods

TemplatedPicker for .NET MAUI allows you to clear the selected value through its `ClearSelection` method.

### Example

```XAML
<StackLayout>
    <Button Clicked="OnClearSelectionClicked" Text="clear selection"/>
    <telerikInput:RadTemplatedPicker x:Name="picker">
        <telerikInput:RadTemplatedPicker.SelectorTemplate>
            <ControlTemplate>
                <telerikInput:RadCalendar SelectedDate="{TemplateBinding SelectedValue, Mode=TwoWay}"/>
            </ControlTemplate>
        </telerikInput:RadTemplatedPicker.SelectorTemplate>
    </telerikInput:RadTemplatedPicker>
</StackLayout>
```

and you can clear the selection inside the button click event:

```C#
private void OnClearSelectionClicked(object sender, EventArgs e)
{
    this.picker.ClearSelection();
}
```

also you will need to add the following namespace:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;Telerik.Maui.Controls.Compatibility"
```

## See Also

- [Events]({%slug templatedpicker-events%})
- [Commands]({%slug templatedpicker-commands%})