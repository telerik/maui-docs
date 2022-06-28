---
title: Events
page_title: .NET MAUI TemplatedPicker Documentation - Events
description: Check our &quot;Events&quot; documentation article for Telerik TemplatedPicker for .NET MAUI.
position: 5
previous_url: /controls/templatedpicker/templatedpicker-events
slug: templatedpicker-events
---

# Events

The TemplatedPicker for .NET MAUI exposes a `SelectionChanged` event which is raised when the user confirms the selected item.

Define the TemplatedPicker:

```XAML
<telerik:RadTemplatedPicker SelectionChanged="RadTemplatedPicker_SelectionChanged" x:Name="picker">
    <telerik:RadTemplatedPicker.SelectorTemplate>
        <ControlTemplate>
            <telerik:RadCalendar SelectedDate="{TemplateBinding SelectedValue, Mode=TwoWay}"/>
        </ControlTemplate>
    </telerik:RadTemplatedPicker.SelectorTemplate>
</telerik:RadTemplatedPicker>
```

Set the `SelectionChanged` event where the `sender` is the TemplatedPicker control.

```C#
private void RadTemplatedPicker_SelectionChanged(object sender, System.EventArgs e)
{
	// implement your logic here
}
```

## See Also

- [Commands]({%slug templatedpicker-commands%})
- [Methods]({%slug templatedpicker-methods%})
- [Templates]({% slug templatedpicker-templates%})
