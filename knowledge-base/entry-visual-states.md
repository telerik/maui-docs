---
title: Entry
page_title: Entry Visual States - .NET MAUI Knowledge Base
description: Learn how to set a Telerik UI for .NET MAUI Entry Visual States
type: how-to
slug: entry-visual-states
tags: maui, entry, visual, states 
res_type: kb
---

## Environment

<table>
	<tbody>
    <tr>
      <td>Product</td>
      <td>Progress® Telerik® UI for .NET MAUI Entry</td>
    </tr>
  	<tr>
  		<td>Product Version</td>
  		<td>5.1.0</td>
  	</tr>
	</tbody>
</table>


## Description

How can I set the Visual States in the Telerik UI for .NET MAUI Entry?

## Solution

The RadEntry control inherits the Visual States, which comes from the .NET MAUI Entry. The `Visual State Manager` introduces the concept of visual states. It defines a visual state group named `CommonStates` with the following visual states: `Normal`,`Disabled`, `Focused`, `Selected` and `PointerOver`. It is a good practice to set all visual states even if there is nothing to set in them. 

```XAML
  <telerik:RadEntry x:Name="tEntry" Placeholder="telerik">
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
                                <Setter Property="BackgroundColor"  Value="yellow" />
                            </VisualState.Setters>
                        </VisualState>
                        <VisualState x:Name="PointerOver"/>
                    </VisualStateGroup>
                </VisualStateGroupList>
            </VisualStateManager.VisualStateGroups>
        </telerik:RadEntry>
```