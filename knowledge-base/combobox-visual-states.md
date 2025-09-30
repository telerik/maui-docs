---
title: Setting the Visual States of the ComboBox
page_title: Configure the Visual States of the ComboBox Component - .NET MAUI Knowledge Base
description: Learn how to define the visual states of the Telerik UI for .NET MAUI ComboBox control.
type: how-to
slug: combobox-visual-states-kb
tags: maui, combobox, visual states, .net maui combobox, focused, normal, disabled, hover, mouse over
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 6.7.0 | ComboBox for .NET MAUI | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 


## Description

How can I set the visual states of the Telerik UI for .NET MAUI ComboBox control?

## Solution

To set the visual states of the ComboBox control, configure the `VisualStateManager`. The `VisualStateManager` defines a visual state group named `CommonStates` and supports the `Normal`, `Disabled`, `Focused`, and `MouseOver` values. As a general recommendation, always configure all available visual states.

```XAML
<telerik:RadComboBox x:Name="combo" Placeholder="telerik">
    <VisualStateManager.VisualStateGroups>
        <VisualStateGroupList>
            <VisualStateGroup x:Name="CommonStates">
                <VisualState x:Name="Normal">
                    <VisualState.Setters>
                        <Setter Property="FontSize" Value="35" />
                    </VisualState.Setters>
                </VisualState>
                <VisualState x:Name="Focused">
                    <VisualState.Setters>
                        <Setter Property="BackgroundColor" Value="Red" />
                    </VisualState.Setters>
                </VisualState>
                <VisualState x:Name="Disabled">
                    <VisualState.Setters>
                        <Setter Property="BackgroundColor" Value="Pink" />
                    </VisualState.Setters>
                </VisualState>
                <VisualState x:Name="Unfocused">
                    <VisualState.Setters>
                        <Setter Property="BackgroundColor"  Value="Yellow" />
                    </VisualState.Setters>
                </VisualState>
                <VisualState x:Name="MouseOver">
                    <VisualState.Setters>
                        <Setter Property="BackgroundColor"  Value="Green" />
                    </VisualState.Setters>
                </VisualState>
            </VisualStateGroup>
        </VisualStateGroupList>
    </VisualStateManager.VisualStateGroups>
</telerik:RadComboBox>
```

>note If you want to apply visual states to the elements inside the drop-down, set visual states inside the ComboBox `ItemTemplate` and `SelectedItemTemplate`.
