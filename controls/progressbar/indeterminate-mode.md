---
title: Indeterminate Mode
page_title: .NET MAUI ProgressBar Documentation - Indeterminate Mode
description: Check our &quot;Indeterminate Mode&quot; documentation article for Telerik ProgressBar for .NET MAUI control.
position: 4
slug: progressbar-indeterminate-mode
---

# .NET MAUI ProgressBar Indeterminate Mode

Telerik ProgressBar for MAUI supports two modes of operation:

* **Determinate**&mdash;aimed at scenarios in which the progress of an operation can be precisely measured.

* **Indeterminate**&mdash;aimed at scenarios in which there is no way of determining the current progress of an operation.

Using the `IsIndeterminate` property(of type `bool`) you can specify whether the control is in Indeterminate mode or not. The default value is `false`.

![.NET MAUI ProgressBar Indeterminate support](images/progressbar-indeterminate-mode.gif)

**Example with Indeterminate mode**

The snippet below shows a simple `RadLinearProgressBar` definition with `IsIndeterminate` property set to `True`.

<snippet id='progressbar-indeterminate-mode'/>

Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

>important For the ProgressBar Indeterminate example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}).

## See Also

- [Configuration]({%slug progressbar-configuration%})
- [Animations]({%slug progressbar-animations%})
- [Events]({%slug progressbar-events%})
- [Styling]({%slug progressbar-styling%})
