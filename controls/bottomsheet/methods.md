---
title: Methods
page_title: .NET MAUI BottomSheet Documentation - Methods
description: Learn about the methods that the Telerik UI for .NET MAUI BottomSheet control exposes and find out how to use them to configure the UI component.
position: 11
slug: bottomsheet-methods
---

# .NET MAUI BottomSheet Methods

The Telerik UI for .NET MAUI BottomSheet component exposes the `GoToBottomSheetState(string name)` method. Use the method to transition the bottom sheet to a specified [state]({%slug bottomsheet-configuration%}).

The example shows how to use the `GoToBottomSheetState(string name)` method:

**1** Define the BottomSheet in XAML:

<snippet id='bottomsheet-getting-started-xaml' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Call the `GoToBottomSheetState()` method with corresponding state name:

<snippet id='open-bottomsheet-view' />

This is the result on Android:

![.NET MAUI BottomSheet Methods](images/bottomsheet-methods.gif)

## See Also

- [Configure the BottomSheet]({%slug bottomsheet-configuration%})
- [Animation when opening and closing the bottom sheet]({%slug bottomsheet-animation%})
- [Style the BottomSheet]({%slug bottomsheet-styling%})
- [Events]({%slug bottomsheet-events%})

