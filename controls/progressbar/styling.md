---
title: Styling
page_title: .NET MAUI ProgressBar Documentation - Styling
description: Check our &quot;Styling&quot; documentation article for Telerik ProgressBar for .NET MAUI control.
position: 10
slug: progressbar-styling
---

# .NET MAUI ProgressBar Styling

The ProgressBar control for .NET MAUI provides styling options for customizing its appearance.

The control supports the following styling properties:

* `TrackFill`(`Brush`)&mdash;Specifies the fill of the track.

<snippet id='progressbar-styling-trackfill'/>

![ProgressBar Track Fill](images/progressbar-styling-track-fill.png)

* `ProgressFill`(`Brush`)&mdash;Specifies the fill of the progress indicator.

<snippet id='progressbar-styling-progressfill'/>

![ProgressBar Progress Fill](images/progressbar-styling-progress-fill.png)

* `IndeterminateFill`(`Brush`)&mdash;Defines the fill of the indeterminate indicator.

<snippet id='progressbar-styling-indeterminatefill'/>

![ProgressBar Text Styling](images/styling-indeterminate-fill.png)

The following Style properties are related to the text displayed in the ProgressBar:

* `TextColor`(`Color`)&mdash;Defines the color of the Text which displays the progress value.
* `AlternateTextColor`(`Color`)&mdash;Defines the text color when the progress indicator overlaps the label which displays the current progress.
* `FontSize`(`double`)&mdash;Defines the font size of the Text which displays the progress value

<snippet id='progressbar-styling-text'/>

![ProgressBar Text Styling](images/progressbar-styling-text.png)

Style the ProgressBar segments using the following properties:

* `SegmentSeparatorFill`(`Brush`)&mdash;Specifies the fill of the segments separators.
* `SegmentSeparatorThickness`(`double`)&mdash;Sets the thickness of the segments separators.

<snippet id='progressbar-styling-separator-segments'/>

![ProgressBar Segments Separator Fill](images/progressbar-styling-segments-separator.png)

>important For the ProgressBar Styling example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}).

## See Also

- [Configuration]({%slug progressbar-configuration%})
- [Indeterminate Mode]({%slug progressbar-indeterminate-mode%})
- [Events]({%slug progressbar-events%})
