---
title: Covering the Flyout Menu with BusyIndicator in .NET MAUI
description: Learn how to extend the coverage of BusyIndicator to include the Flyout menu in .NET MAUI applications.
type: how-to
page_title: How to Extend BusyIndicator Coverage to the Flyout Menu in .NET MAUI
slug: extend-busyindicator-coverage-flyout-net-maui
tags: busyindicator, .net maui, shell, flyout, overlay
res_type: kb
ticketid: 1674906
---

## Description

When implementing the [BusyIndicator for .NET MAUI](https://docs.telerik.com/devtools/maui/controls/busyindicator), it's observed that the indicator covers only the view area and not the Flyout menu. This knowledge base article also answers the following questions:
- How to cover the Flyout menu with BusyIndicator in .NET MAUI Shell?
- How to ensure BusyIndicator visibility over the entire application including the Flyout in .NET MAUI?
- How to implement an overlay for the Flyout menu in .NET MAUI?

## Environment

<table>
<tbody>
<tr>
<td>Product</td>
<td>BusyIndicator for .NET MAUI</td>
</tr>
<tr>
<td>Version</td>
<td>6.7.0</td>
</tr>
</tbody>
</table>

## Solution

To cover the Flyout area of the Microsoft Shell along with the application's content page using BusyIndicator, you need to define a separate BusyIndicator or an overlay specifically for the Flyout. The Flyout area is not part of the application's main visual tree but is a separate page, requiring its own BusyIndicator implementation.

To achieve this, access your Shell definition and override the `FlyoutContent` to include a BusyIndicator. This allows you to show the BusyIndicator or an overlay specifically for the Flyout menu.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<Shell xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
       xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
       xmlns:local="clr-namespace:FullShellCoverage"
       xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
       x:Class="FullShellCoverage.AppShell"
       Title="AppShell"
       FlyoutBehavior="Locked"
       FlyoutIsPresented="True"
       x:Name="shell">

    <ShellContent Title="Home"
                  ContentTemplate="{DataTemplate local:MainPage}"
                  Route="MainPage">
        <ShellContent.Icon>
            <FontImageSource
                Glyph="🏠"
                Color="DodgerBlue"
                Size="18"/>
        </ShellContent.Icon>
    </ShellContent>

    <Shell.FlyoutContent>
        <Grid>
            <CollectionView BindingContext="{x:Reference shell}"
                            IsGrouped="True"
                            ItemsSource="{Binding FlyoutItems}">
                <CollectionView.ItemTemplate>
                    <DataTemplate>
                        <Grid ColumnDefinitions="0.2*,0.8*">
                            <Image Source="{Binding Icon}"
                                   Margin="5"
                                   HeightRequest="45" />
                            <Label Grid.Column="1"
                                   Text="{Binding Title}"
                                   VerticalTextAlignment="Center" />
                        </Grid>
                    </DataTemplate>
                </CollectionView.ItemTemplate>
            </CollectionView>

            <telerik:RadBusyIndicator x:Name="GlobalBusyIndicator"
                                      IsVisible="False"
                                      AnimationContentHeightRequest="100"
                                      AnimationContentWidthRequest="100"
                                      AnimationContentColor="{DynamicResource PrimaryColor}"
                                      BackgroundColor="#CCDCDCDC"/>
        </Grid>
    </Shell.FlyoutContent>
</Shell>
```

### Additional Information

- Understanding the architecture of the .NET MAUI Shell, including the Flyout menu, is crucial for implementing this solution. For more details, refer to the [.NET MAUI Shell flyout documentation](https://learn.microsoft.com/en-us/dotnet/maui/fundamentals/shell/flyout?view=net-maui-9.0).
- This solution is applicable to any BusyIndicator, including the Telerik RadBusyIndicator, and is not limited to the default ActivityIndicator provided by .NET MAUI.


## See Also

- [BusyIndicator for .NET MAUI Documentation](https://docs.telerik.com/devtools/maui/controls/busyindicator)
- [.NET MAUI Shell flyout - .NET MAUI | Microsoft Learn](https://learn.microsoft.com/en-us/dotnet/maui/fundamentals/shell/flyout?view=net-maui-9.0)
