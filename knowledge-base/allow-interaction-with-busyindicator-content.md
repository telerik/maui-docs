---
title: Enabling Interaction with the Content behind the BusyIndicator
description: Learn how to display .NET MAUI BusyIndicator above any content to mark long-running operations and allow interacting with the content behind when not busy.
type: how-to
page_title: Enabling Interaction with the Content behind the BusyIndicator
slug: allow-interaction-with-busyindicator-content
tags: busy indicator, interaction, InputTransparent, .NET MAUI
res_type: kb
---

| Version | Product | Author | 
| --- | --- | ---- | 
| 6.8.0 | Telerik UI for .NET MAUI BusyIndicator | [Yana Kerpecheva](https://www.telerik.com/blogs/author/yana-kerpecheva) | 

## Description

I want to allow the user to interact with the content behind the BusyIndicator when the control's `IsBusy` property is set to `False`. How to achieve this?

## Solution

Telerik .NET MAUI BusyIndicator allows you to indicate that a long-running operation is taking place. When you display the BusyIndicator over other content, the control may prevent the user interaction with that content even when `IsBusy` is `False`.

To allow the interaction with the content behind the busy indicator when its `IsBusy` property is `False`, set `InputTransparent` to `True` and `CascadeInputTransparent` to `False` to the `RadBusyIndicator` instance. In case the BusyIndicator has its `Content` defined, set `InputTransparent` to `True` and `CascadeInputTransparent` to `False` to the main layout wrapped in the `Content` as well.

The example below shows how to utilize the approach with the BusyIndicator. An Entry control is placed below the BusyIndicator and the BusyIndicator's `Content` is defined. The `InputTransparent` and `CascadeInputTransparent` properties are set for both the `RadBusyIndicator` instance and the Grid to allow interaction with the Entry component behind:

```XAML
<Grid BackgroundColor="White">
    <Entry Text="This is an Entry placed behind the BusyIndicator"
           TextColor="Red"
           VerticalOptions="Start" />
    <telerik:RadBusyIndicator x:Name="BusyIndicator"
                              InputTransparent="True"
                              CascadeInputTransparent="False">
        <telerik:RadBusyIndicator.Content>
            <Grid InputTransparent="True"
                  CascadeInputTransparent="False">
                <Entry Text="This is the Content of the RadBusyIndicator control displayed when the indicator is not busy." 
                       VerticalOptions="Center"
                       TextColor="Black" />
            </Grid>
        </telerik:RadBusyIndicator.Content>
    </telerik:RadBusyIndicator>
</Grid>
```

## See Also

- [BusyIndicator Documentation]({%slug busyindicator-overview%})
- [Adding an Image Inside the BusyIndicator for .NET MAUI]({%slug add-image-inside-busyindicator-dotnet-maui%})