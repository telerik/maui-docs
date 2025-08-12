---
title: Screen Reader
page_title: .NET MAUI CollectionView Documentation - Screen Reader
description: The Telerik UI for .NET MAUI CollectionView provides screen reader support for Android and iOS.
position: 0
slug: collectionview-accessibility-screen-reader
tags: accessibility, collectionview, screen reader, accessibility support, dotnet maui
---

# .NET MAUI CollectionView Screen Reader Support

The Telerik UI for .NET MAUI CollectionView provides extensive accessibility support and enables users with disabilities to acquire complete control over its features.

The CollectionView allows users to use the Android (TalkBack), WinUI (Narrator), iOS and MacCatalyst (VoiceOver) screen readers for voice descriptions of the elements inside the CollectionView.

The Telerik MAUI CollectionView exposes an `AutomationManager` class which controls the automation behavior of the control. The `AutomationManager` class is responsible for managing the automation features of the CollectionView, such as enabling or disabling screen reader support.

## WinUI Automation Behavior

The `AutomationManager` class exposes the `EnableWindowsAutomation` (`bool`) property, which determines whether the automation-related logic is enabled for WinUI. The default value is `false`, which means that the automation logic is disabled by default. To enable the automation logic, set the `EnableWindowsAutomation` property to `true`.

Here's how to enable WinUI automation support:

```csharp
// Enable Windows automation
AutomationManager.EnableWindowsAutomation = true;
```

![.NET MAUI CollectionView Screen Reader Support](../images/collectionview-screen-reader.png)

## See Also

- [Keyboard navigation support on MacCatalyst]({%slug collectionview-keyboard-support-mac%})
- [Keyboard navigation support on WinUI]({%slug collectionview-keyboard-support-winui%})