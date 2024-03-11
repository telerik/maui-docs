---
title: Make it possible to interact through the BusyIndicator Content when IsBusy is False
description: Learn how to display .NET MAUI BusyIndicator above any content to mark long-running operation and allow interacting with the content behind when not busy
type: how-to
page_title: How to wrap any content with RadBusyIndicator to notify users for long-running process and enable user interaction with that content when not busy - BusyIndicator for .NET MAUI
slug: allow-interaction-with-busyindicator-content
tags: busy indicator, interaction, InputTransparent, .NET MAUI
res_type: kb
---

| Version | Product | Author | 
| --- | --- | ---- | 
| 6.8.0 | Telerik UI for .NET MAUI BusyIndicator | [Yana Kerpecheva](https://www.telerik.com/blogs/author/yana-kerpecheva) | 

## Description

Telerik .NET MAUI BusyIndicator allows you to display a notification indicator while a long-running operation is taking place. When you wrap any content within the BusyIndicator, the control may prevent the user interaction with that content even when `IsBusy` is `False`.

## Solution

To allow the interaction with the content behind the busy indicator when `IsBusy` is `False`, set `InputTransparent` to `True` and `CascadeInputTransparent` to `False` to both the `RadBusyIndicator` instance and the main layout control holding the content.

Check below a quick example showing how to wrap some sample content inside `RadBusyIndicator`'s `Content` property - `InputTransparent` and `CascadeInputTransparent` are defined for the parent VerticalStackLayout to allow interacting with the Entry and Button inside:

```XAML
<telerik:RadBusyIndicator x:Name="busyIndicator"
                          InputTransparent="True" 
                          CascadeInputTransparent="False">
    <telerik:RadBusyIndicator.Content>
        <VerticalStackLayout InputTransparent="True" 
                             CascadeInputTransparent="False">
            <Entry Text="This is the content of the RadBusyIndicator control displayed when the indicator is not busy." />
            <Button Text="Click in Content" 
                    Clicked="TestButtonClicked"/>
        </VerticalStackLayout>
    </telerik:RadBusyIndicator.Content>
</telerik:RadBusyIndicator>
```

## See Also

- [BusyIndicator Documentation]({%slug busyindicator-overview%})
