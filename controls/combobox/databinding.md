---
title: Data Binding
page_title: .NET MAUI ComboBox Documentation - Data Binding
description: Learn more about the ways for data binding in the Telerik UI for .NET MAUI ComboBox control.
position: 3
slug: combobox-databinding
---

# Data Binding in .NET MAUI ComboBox

- `ItemsSource`(`IEnumerable`)&mdash;Defines the collection of the items that will populate the control with data.
- `DisplayMemberPath`(`string`)&mdash;Defines the name of the property which will be visualized inside the drop-down list.

> If DisplayMemberPath is not set the “ToString” implementation of the business object will be visualized. The DisplayMemberPath is a property that helps the developers to visualize an exact property from the business object they are bound to.

## Binding to a Complex Object

**1.** Define the ComboBox in XAML:

<snippet id='combobox-getting-started-complex-object-xaml'/>

**2.** Add the `telerik` namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

**3.** Define a sample business model:

<snippet id='combobox-city-businessmodel'/>

**4.** Add the ViewModel:

<snippet id='combobox-cities-viewmodel'/>

**5.** Set the binding context after `InitializeComponent()` in the page's code behind:

```C#
this.BindingContext = new ViewModel();
```

## See Also

- [Edit Mode & Search]({%slug combobox-editmode-and-search%}) 
- [Single and Multiple Selection]({%slug combobox-selection%})
