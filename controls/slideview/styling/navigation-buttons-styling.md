---
title: Navigation Buttons Styling
page_title: .NET MAUI SlideView Documentation - Navigation Buttons Styling
description: Learn how to style and customize the .NET Maui SlideView navigation buttons.
position: 12
slug: slideview-navigation-buttons-styling
---

# .NET MAUI Navigation Buttons Styling

The SlideView control exposes styling properties that allow you to customize the Navigation Buttons:

* `NavigateToPreviousItemButtonStyle`(Style with target type `telerik:Radbutton`)&mdash;Defines the custom style that will be applied to the button leading to the previous item.

* `NavigateToNextItemButtonStyle`(Style with target type `telerik:Radbutton`)&mdash;Defines the custom style that will be applied to the button leading to the next item.

### Example

The following example demonstrates how to style the Navigation Buttons of the control.

<snippet id='slideview-navigation-styling-xaml' />

Add Style resources:

<snippet id='slideview-navigation-styling-resources' />

And the result below:

![.NET MAUI SlideView Navigation Buttons Styling](images/slideview-navigation-buutons-styling.gif)


## See Also

- [Binding SlideView to Data]({%slug slideview-data-binding%})
- [Using Navigation Buttons in SlideView]({%slug slideview-interaction%})
- [Executing Commands on Slide Action]({%slug slideview-commands%})
- [Handling the SlideView Events]({%slug slideview-events%})
- [Using an Item Template in SlideView]({%slug slideview-item-template%})
- [Changing the SlideView Appearance through a Control Template]({%slug slideview-control-template%})
- [Styling the SlideView Indicators]({%slug indicators-styling%})
