---
title: CustomLayout
page_title: .NET MAUI DataForm Documentation - CustomLayout
description: Learn how to apply custom layout in the .NET MAUI DataForm.
position: 4
slug: dataform-layouts-custom
---

# .NET MAUI DataForm Custom Layout Definition

The `DataFormCustomLayout` definition allows you to arrange the items using a custom layout.

To build the custom layout you have to use the `LayoutTemplate` (`DataTemplate`) property.

XAML definition of `RadDataForm` with `CustomLayout` applied using a `RadWrapLayout`:

```XAML
<Grid>
    <telerik:RadDataForm x:Name="dataForm">
        <telerik:RadDataForm.LayoutDefinition>
            <telerik:DataFormCustomLayout>
                <telerik:DataFormCustomLayout.LayoutTemplate>
                    <DataTemplate>
                        <telerik:RadWrapLayout/>
                    </DataTemplate>
                </telerik:DataFormCustomLayout.LayoutTemplate>
            </telerik:DataFormCustomLayout>
        </telerik:RadDataForm.LayoutDefinition>
        <telerik:RadDataForm.BindingContext>
            <local:EditorsViewModel/>
        </telerik:RadDataForm.BindingContext>
    </telerik:RadDataForm>
</Grid>
```

Define the  `ViewModel` for the DataForm `BindingContext`:

<snippet id='dataform-editors-model'/>

where the `local` points to the namespace where the `EditorsViewModel` is defined.

## See Also

- [DataForm with VerticalStack Layout]({%slug dataform-layouts-verticalstack%})
- [DataForm with Grid Layout]({%slug dataform-layouts-grid%})
