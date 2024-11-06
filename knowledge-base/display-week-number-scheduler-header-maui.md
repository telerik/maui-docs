---
title: Displaying Week Numbers in the Scheduler's HeaderTextFormat
description: Learn how to show week numbers in the RadScheduler for .NET MAUI by binding the HeaderTextFormat property.
type: how-to
page_title: How to Display Week Numbers in Scheduler Header in .NET MAUI
slug: display-week-number-scheduler-header-maui
tags: scheduler, .net maui, headertextformat, binding, week number
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 7.1.0 | Telerik UI for .NET MAUI Scheduler | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 


## Description

I need to display the week number in the `HeaderTextFormat` of the [Scheduler]({%slug header-settings%}) for .NET MAUI. How can I achieve this? Is it possible to use a bindable property for customization?

This KB article also answers the following questions:
- How to bind a property to the Scheduler's HeaderTextFormat in .NET MAUI?
- What is the method to customize the Scheduler's header format to include week numbers?
- Can I use data binding to modify the HeaderTextFormat of the Scheduler control?

## Solution

To display the week number in the `HeaderTextFormat` of the `RadScheduler`, you can utilize data binding for customization. The `HeaderTextFormat` property is bindable, allowing you to format the date in the header as required.

Below is an example demonstrating how to bind a property to the `HeaderTextFormat` property of the Scheduler control:

**1.** Define the Scheduler control in XAML:

```xml
<telerik:RadScheduler AutomationId="scheduler" CurrentDate="10/18/2023">
    <telerik:RadScheduler.ViewDefinitions>
        <telerik:MonthViewDefinition Title="MonthView scheduler" HeaderTextFormat="{Binding MyProperty}" />
    </telerik:RadScheduler.ViewDefinitions>
</telerik:RadScheduler>
```

**2.** Create a `ViewModel` for the property:
```csharp
public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();
        this.BindingContext = new ViewModel();
    }
}

public class ViewModel
{
    public ViewModel()
    {
        // Customize the HeaderTextFormat here
        this.MyProperty = "My property for header text format";
    }

    public string MyProperty { get; set; }
}
```

In this example, the `MyProperty` in the ViewModel is bound to the `HeaderTextFormat` property of the Scheduler. You can adjust the value of `MyProperty` to format the date in the header as needed, including displaying the week number.

## See Also

- [Scheduler Header Settings in .NET MAUI]({%slug header-settings%})
- [Scheduler Overview in .NET MAUI]({%slug scheduler-overview%})
- [Data Binding in .NET MAUI](https://docs.microsoft.com/en-us/dotnet/maui/fundamentals/data-binding)
