---
title: Cell Swipe
page_title: .NET MAUI ListView Documentation - Cell Swipe
description: Learn what are the swiping options for Telerik ListView for .NET MAUI and how to define custom swipe template.
position: 
previous_url: /controls/listview/gestures/listview-gestures-cell-swipe
slug: listview-features-cell-swipe
---

# .NET MAUI ListView Cell Swipe

Cell swipe allows end-users to use swipe gestures on cells. When users swipe, they reveal a designated custom view with buttons, images etc.

The image below shows how swiping right can reveal a Delete button on the left:

![ListView Cell Swipe Gesture](images/listview-cellswipe.png)

You can reveal another custom view if the user swipes left. In this case, Cell Swipe displays the custom view on the right. As soon as the user taps the swiped item or anywhere on the ListView, the item returns to its original position.

## Properties

You can use the following `RadListView` properties to configure the Cell Swipe feature:

- `IsItemSwipeEnabled`(`bool`)&mdash;Enables or disables the Cell Swipe feature. The default value is False.
- `SwipeThreshold`(`double`)&mdash;Defines the length (in pixels) of the swipe gesture that is required to trigger the feature. Shorter swipe gestures are not respected. The default value is 0.
- `SwipeOffset`(`Thickness`)&mdash;Specifies how to move the swiped cell to the side and stick it there. The default value is 100.
- `ItemSwipeContentTemplate` (`DataTemplate`)&mdash;Defines the content that will be visualized when users swipe a cell.

>tip The `SwipeThreshold` value must be lower than the `SwipeOffset` value. This is required because the `SwipeThreshold` defines the minimum swipe gesture length that triggers the Cell Swipe feature and reveals a custom view.

## Methods

The following `RadListView` methods are related to the cell swiping feature:

- void `EndItemSwipe`(`bool` `isAnimated`)&mdash;Moves the swiped item to its default position.

## Events

The following `RadListView` events are related to the cell swiping feature:

- `ItemSwipeStarting`&mdash;Occurs when the user initiates the swipe gesture. The event arguments are of the `ItemSwipeStartingEventArgs` type that provides the following properties:
  - `Item`(`object`)&mdash;The item that will be swiped.
  - `Cancel`(`bool`)&mdash;If you set this value to `false`, the swiping will be canceled.
- `ItemSwiping`&mdash;Occurs while the user is swiping the item. The event arguments are of the `ItemSwipingEventArgs` type that provides the following properties:
  - `Item`(`object`)&mdash;The item that is being swiped.
  - `Offset`(`double`)&mdash;The current swipe offset.
- `ItemSwipeCompleted`&mdash;Occurs when the user finishes the swipe gesture. The event arguments are of the `ItemSwipeCompletedEventArgs` type that provides the following properties:
  - `Item`(`object`)&mdash;The item that has been swiped.
  - `Offset`(`double`)&mdash;The swipe offset at which the item has been dropped.

## Commands

In addition to the swipe events, `RadListView` provides the following commands related to swipe actions:

- `ItemSwipeStarting`
- `ItemSwiping`
- `ItemSwipeCompleted`

For more details on how to use the ListView commands, see [Commands]({% slug listview-features-commands %}).
  
## Examples

The `RadListView` swipe events allow you to configure custom actions that depend on the swipe direction, the swipe gesture length or the data item.

Alternatively, you can add interactive elements to the swipe content and use the swipe gesture only to reveal this content. The user can then choose how to interact with the revealed content.

### Example with Swipe Events

The following example demonstrates how to use the `ItemSwipeCompleted` event. Depending on the swipe gesture length, we will modify the data item or remove it from the source.

![ListView Cell Swipe](images/listview-gestures-swipe-swipe-event.png)

**1.** Add the ViewModel for the ListView:

<snippet id='listview-gestures-cellswipe-swipeevents-viewmodel'/>

**2.** **Set up ListView. Swiping left or right will reveal content with a hint for what will happen if the user completes the swipe action.

<snippet id='listview-gestures-cellswipe-swipeevents-listview'/>

**3.** **Define the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"                 
```

**4.** **Configure what happens when the user completes the swipe gesture:

<snippet id='listview-gestures-cellswipe-swipeevents-swipecompleted'/>

We call the `EndItemSwipe()` method to force the item to go to its default position since the scenario does not require any interaction with the swipe content itself.

### Example with Interactive Content

The following example demonstrates how to add a delete button to the swipe content. We use the button's `Clicked` event handler to delete an item from the ListView source.

![ListView Cell Swipe Interactive Content](images/listview-gestures-swipe-interactive-content.png)

**1.** Add the view model for the ListView:

<snippet id='listview-gestures-cellswipe-interactivecontent-viewmodel'/>

**2.** Set up ListView. Note that the `SwipeOffset` is equal to the width of the button in the swipe content. Thus, when the swipe is complete, the revealed content will be the whole button.

<snippet id='listview-gestures-cellswipe-interactivecontent-listview'/>

**3.** Define the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"                 
```
 
**4.** Configure what happens when the user completes the swipe gesture. The `BindingContext` of the swipe content is the data item. This can be used to perform operations on the data. In this case, we will delete the item from the source.

<snippet id='listview-gestures-cellswipe-interactivecontent-deleteitem'/>

> For sample Cell Swipe examples, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to ListView -> Cell Swipe category.

## See Also

- [ListView Text Cell]({% slug listview-textcell %})
- [ListView Template Cell]({% slug listview-templatecell %})
- [Layouts]({% slug listview-features-layouts %})
- [Commands]({% slug listview-features-commands %})
- [Pull to Refresh]({% slug listview-features-pull-to-refresh %})
- [Reorder Items]({% slug listview-features-reorder-items %})
