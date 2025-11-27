---
title: Cancel Checkbox Change in .NET MAUI
description: Learn how to cancel a Checkbox change in .NET MAUI using the IsCheckedChanged event.
type: how-to
page_title: Prevent Checkbox State Change in .NET MAUI
meta_title: Prevent Checkbox State Change in .NET MAUI
slug: cancel-checkbox-change-net-maui
tags: checkbox, .net maui, ischeckedchanged, ischecked, binding
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 12.0.0 | Telerik UI for .NET MAUI CheckBox | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to cancel a state change in a Checkbox control in .NET MAUI based on a specific condition. This allows me to maintain control over the Checkbox's state and update it dynamically.

This knowledge base article also answers the following questions:
- How to prevent Checkbox state change in .NET MAUI?
- How to handle the `IsCheckedChanged` event to cancel state change?
- How to implement conditional logic for Checkbox state in .NET MAUI?

## Solution

To achieve this behavior, use the `IsCheckedChanged` event and set the `IsChecked` property conditionally.

**1.** Create a `ViewModel` class to store and bind the Checkbox state.

```csharp
public class ViewModel : NotifyPropertyChangedBase
{
    private bool myproperty = false;
    public bool MyProperty
    {
        get => this.myproperty;
        set
        {
            if (this.myproperty != value)
            {
                this.myproperty = value;
                OnPropertyChanged();
            }
        }
    }
}
```

**2.** Use the `IsCheckedChanged` event to monitor state changes.

**3.** Implement conditional logic to revert the state if a condition is not met.

```csharp
public partial class MainPage : ContentPage
{
    ViewModel vm;
    public bool OperationPassed = true;

    public MainPage()
    {
        InitializeComponent();
        this.vm = new ViewModel();
        this.BindingContext = this.vm;
    }

    private void RadCheckBox_IsCheckedChanged(object sender, IsCheckedChangedEventArgs e)
    {
        // Check condition and revert state
        if (this.OperationPassed is false)
        {
            this.vm.MyProperty = false;
        }
        else
        {
            this.vm.MyProperty = true;
        }
    }
}
```

**4.** The Checkbox definition in XAML:

```xml
<HorizontalStackLayout Spacing="5" VerticalOptions="Start">
    <telerik:RadCheckBox IsChecked="{Binding MyProperty, Mode=TwoWay}" 
                         IsCheckedChanged="RadCheckBox_IsCheckedChanged" 
                         IsThreeState="False"/>
</HorizontalStackLayout>
```

## See Also

- [CheckBox Overview](https://www.telerik.com/maui-ui/documentation/controls/checkbox/overview)
