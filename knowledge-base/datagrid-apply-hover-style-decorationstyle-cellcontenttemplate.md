---
title: Applying Hover Style with DecorationStyle or CellContentTemplate in DataGrid for MAUI
description: Learn how to apply hover styles to cells in a DataGrid for MAUI when using DecorationStyle or CellContentTemplate.
type: how-to
page_title: Apply Hover Style with DecorationStyle or CellContentTemplate in DataGrid for MAUI
slug: datagrid-apply-hover-style-decorationstyle-cellcontenttemplate
tags: maui, datagrid, hover style, decoration style, cell content template, pointer over state, visualstatemanager
res_type: kb
category: knowledge-base
---

# Environment
| Product | Version |
|---------|---------|
| Progress® Telerik® UI for .NET MAUI DataGrid | 6.6.0 |

# Description

When assigning a style to `CellDecorationStyle` or a `DataTemplate` to `CellContentTemplate` in a `DataGridColumn` of a `RadDataGrid`, the hover functionality may be lost. The background color does not change on hover, and if the cell has a DataTemplate, the text color does not change either.

This article provides a solution for using these styles while maintaining the common hover style and suggests other possible solutions.

# Solution

To apply hover styles to cells in a DataGrid for MAUI when using `DecorationStyle` or `CellContentTemplate`, follow these steps:

1. Add a visual state manager to the element inside the template.
2. Use the `VisualStateManager.VisualStateGroups` property to define visual states for the hover effect via the `PointerOver` state.

Here is an example, in both XAML and C# variants, of how to use the `VisualStateManager` to define a `PointerOver` state in a custom `CellContentTemplate`:

## XAML Option

```
<telerik:RadDataGrid.Columns>
    <telerik:DataGridTextColumn PropertyName="Name" HeaderText="Name">
        <telerik:DataGridTextColumn.CellDecorationStyle>
            <telerik:DataGridBorderStyle BorderColor="DarkBlue" BorderThickness="3" BackgroundColor="LightBlue" />
        </telerik:DataGridTextColumn.CellDecorationStyle>
        <telerik:DataGridTextColumn.CellContentTemplate>
            <DataTemplate>
                <Label Text="{Binding Name}">
                    <VisualStateManager.VisualStateGroups>
                        <VisualStateGroupList>
                            <VisualStateGroup x:Name="CommonStates">
                                <VisualState x:Name="Normal">
                                    <VisualState.Setters>
                                        <Setter Property="BackgroundColor" Value="Lime" />
                                    </VisualState.Setters>
                                </VisualState>
                                <VisualState x:Name="Disabled">
                                    <VisualState.Setters>
                                        <Setter Property="BackgroundColor" Value="Pink" />
                                    </VisualState.Setters>
                                </VisualState>
				<!-- TAKEAWAY: This is the PointerOver state that is invoked during hover -->
                                <VisualState x:Name="PointerOver">
                                    <VisualState.Setters>
                                        <Setter Property="BackgroundColor" Value="LightBlue" />
                                        <Setter Property="TextColor" Value="Red" />
                                    </VisualState.Setters>
                                </VisualState>
                            </VisualStateGroup>
                        </VisualStateGroupList>
                    </VisualStateManager.VisualStateGroups>
                </Label>
            </DataTemplate>
        </telerik:DataGridTextColumn.CellContentTemplate>
    </telerik:DataGridTextColumn>
</telerik:RadDataGrid.Columns>
```

### C# Option

```csharp
var myLabel = REFERENCE_TO_YOUR_LABEL;

VisualStateManager.GetVisualStateGroups(myLabel).Add(new VisualStateGroup
{
	Name = "CommonStates",
	States =
	{
		new VisualState
		{
			Name = "Normal",
			Setters =
			{
				new Setter { Property = Label.BackgroundColorProperty, Value = Colors.Lime }
			}
		},
		new VisualState
		{
			Name = "Disabled",
			Setters =
			{
				new Setter { Property = Label.BackgroundColorProperty, Value = Colors.Pink }
			}
		},
		// TAKEAWAY: This is the PointerOver state that is invoked during hover
		new VisualState
		{
			Name = "PointerOver",
			Setters =
			{
				new Setter { Property = Label.BackgroundColorProperty, Value = Colors.LightBlue },
				new Setter { Property = Label.TextColorProperty, Value = Colors.Red }
			}
		}
	}
});
```

# Notes

- When using a custom `CellContentTemplate`, the `CellContentStyle` may not be respected as the template overrides the default behavior.
- For more information on defining visual states in a style, refer to the [.NET MAUI - Visual States | Microsoft Learn](https://learn.microsoft.com/en-us/dotnet/maui/user-interface/visual-states?view=net-maui-8.0) documentation.
- If you prefer to use styles, you can define visual states for the hover effect in a style and apply it to the label or the specific UI control. Refer to Microsoft documentation [.NET MAUI - Visual States in a Style | Microsoft Learn](https://learn.microsoft.com/en-us/dotnet/maui/user-interface/visual-states?view=net-maui-8.0#define-visual-states-in-a-style)

