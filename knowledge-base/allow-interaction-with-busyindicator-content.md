---
title: Enabling Interaction with the Content of the BusyIndicator
description: Learn how to display .NET MAUI BusyIndicator above any content to mark long-running operations and allow interacting with the content behind when not busy.
type: how-to
page_title: Enabling Interaction with the Content of the BusyIndicator
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

Telerik .NET MAUI BusyIndicator allows you to indicate that a long-running operation is taking place. When you wrap any content within the BusyIndicator, the control may prevent the user interaction with that content even when `IsBusy` is `False`.

To allow the interaction with the content behind the busy indicator when its `IsBusy` property is `False`, set `InputTransparent` to `True` and `CascadeInputTransparent` to `False` to both the `RadBusyIndicator` instance and the main layout control holding the content.

The example below shows how to wrap some sample content inside the  `Content` property of the BusyIndicator. The `InputTransparent` and `CascadeInputTransparent` properties are defined for the parent [VerticalStackLayout]({%slug dataform-layouts%}) to allow interaction with the Entry and Button components inside:

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
