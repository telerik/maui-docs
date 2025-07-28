---
title: Configuration
page_title: .NET MAUI BottomSheet Documentation - Configuration
description: Learn more about how to configure the Telerik UI for .NET MAUI BottomSheet control.
position: 3
slug: bottomsheet-configuration
---

# .NET MAUI BottomSheet Configuration

The purpose of this help article is to show you how to configure the states and width of the Telerik .NET MAUI BottomSheet control.

## States (Built-in Transitions)

The Telerik UI for .NET MAUI BottomSheet control exposes predefined states (transitions). You can specify the state by using following options:

* `CurrentState`(of type `BottomSheetState`) property. The property specifies the current state of the bottom sheet. The available options for `CurrentState` are:

	* `Hidden`(the default one)&mdash;Represents a hidden bottom sheet.
	* `Minimal`&mdash;Represents a minimal bottom sheet state with height `25%`.
	* `Partial`&mdash;Represents a partial bottom sheet state with height `50%`.
	* `Full`&mdash;Represents a full bottom sheet state with height `90%`.

The `BottomSheetState` class represents the state of a bottom sheet.

The first instance of the class has as a parameters the name of the bottom sheet state and the height of the bottom sheet.

```C#
public BottomSheetState(string name, BottomSheetSize height)
```

The second instance of the class has as a parameters the name of the bottom sheet state and the height of the bottom sheet, and if the size parameter represents a percentage.

```C#
public BottomSheetState(string name, double size, bool isPercentage = false)
```

* Calling the [`GoToBottomSheetState(string name)` method]({%slug bottomsheet-methods%}). Where the `string name` is the name of the predefined sates.
	* `Hidden`&mdash;`HiddenStateName`.
	* `Minimal`&mdash;`StateName`.
	* `Partial`&mdash;`PartialStateName`.
	* `Full`&mdash;`FullStateName`.

Here is an example setting the predefined name of the state inside the `GoToBottomSheetState(string name)` method:

<snippet id='open-bottomsheet-view' />

The `UseDefaultStates`(`bool`) property allows you to specify whether the control will generate the default states. The default value is `true`.

The BottomSheet provides a read-only collection&mdash;`States` of type `ObservableCollection<BottomSheetState>`. The collection contains the available sheet states for the bottom sheet.

> For a runnable example with setting the BottomSheet States, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **BottomSheet > Features** category.

## Width

You can specify the width for the bottom sheet, by using the `BottomSheetWidth` (`struct` of type `BottomSheetSize`) property. You can set a percentage or an absolute value to the `BottomSheetWidth`.



> For a runnable example with setting the BottomSheet Width, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **BottomSheet > Features** category.

## Handle

The BottomSheet exposes a visual cue which indicates the control can be dragged. You can customize the handle by using the `HandleStyle` (`Style` with target type `BottomSheetHandle`) property.

For more details review the [BottomSheet Handle Styling]({%slug bottomsheet-styling%}#handle-styling) article.

## See Also

- [Animation when opening and closing the bottom sheet]({%slug bottomsheet-animation%})
- [Style the BottomSheet]({%slug bottomsheet-styling%})
- [Events]({%slug bottomsheet-events%})
- [Methods]({%slug bottomsheet-methods%})