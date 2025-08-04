---
title: Events
page_title: .NET MAUI BottomSheet Documentation - Events
description: Learn about the PositionChanged event in Telerik UI for .NET MAUI BottomSheet and how to handle position changes when the bottom sheet is dragged or programmatically moved.
position: 9
slug: bottomsheet-events
---

# .NET MAUI BottomSheet Events

The BottomSheet `StateChanging` event is useful for tracking user interactions and responding to sheet movements. Use this event to update UI elements based on the sheet's state, implement custom animations, or trigger actions when the sheet reaches specific state during drag gestures or programmatic state changes.
The `StateChanging` event handler receives two parameters: 
* The `sender` argument, which is of type `object`, but can be cast to the `RadBottomSheet` type.
* The `BottomSheetStateChangingEventArgs` object, which has a reference to the new position of the bottom sheet through its `Position` property (of type `double`).

## See Also

- [Configure the BottomSheet]({%slug bottomsheet-configuration%})
- [Animation when opening and closing the bottom sheet]({%slug bottomsheet-animation%})
- [Style the BottomSheet]({%slug bottomsheet-styling%})
- [Methods]({%slug bottomsheet-methods%})