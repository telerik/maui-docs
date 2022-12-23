---
title: Styling
page_title: .NET MAUI ProgressBar Documentation - Styling
description: "Style the Telerik ProgressBar for .NET MAUI control."
position: 10
slug: progressbar-styling
---

# .NET MAUI ProgressBar Styling

The ProgressBar control for .NET MAUI provides styling options for customizing its appearance.

* `TrackFill`(`Brush`)&mdash;Specifies the color of the background track.

<snippet id='progressbar-styling-trackfill'/>

![ProgressBar Track Fill](images/progressbar-styling-track-fill.png)

* `ProgressFill`(`Brush`)&mdash;Specifies the color of the progress indicator.

<snippet id='progressbar-styling-progressfill'/>

![ProgressBar Progress Fill](images/progressbar-styling-progress-fill.png)

## Styling the text

The following properties are related to the text displayed in the ProgressBar:

* `TextColor`(`Color`)&mdash;Defines the color of the Text which displays the progress value.
* `AlternateTextColor`(`Color`)&mdash;Defines the text color when the progress indicator overlaps the label which displays the current progress.
* `FontSize`(`double`)&mdash;Defines the font size of the Text which displays the progress value

<snippet id='progressbar-styling-text'/>

![ProgressBar Text Styling](images/progressbar-styling-text.png)

## Styling the segments

Style the ProgressBar segments using the following properties:

* `SegmentSeparatorFill`(`Brush`)&mdash;Specifies the fill of the segments separators.
* `SegmentSeparatorThickness`(`double`)&mdash;Sets the thickness of the segments separators.

<snippet id='progressbar-styling-separator-segments'/>

![ProgressBar Segments Separator Fill](images/progressbar-styling-segments-separator.png)

## Styling the indeterminate mode

For indeterminate mode you can style the ProgressBar using the `ProgressFill`(`Brush`) property.

<snippet id='progressbar-styling-separator-segments'/>

![ProgressBar Style the indeterminate mode fill](images/progressbar-styling-segments-separator.png)

>important For the ProgressBar Styling example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}).

## See Also

- [Configuration]({%slug progressbar-configuration%})
- [Indeterminate Mode]({%slug progressbar-indeterminate-mode%})
- [Events]({%slug progressbar-events%})
