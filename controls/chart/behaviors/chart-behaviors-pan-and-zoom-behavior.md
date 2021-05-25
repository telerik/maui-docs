---
title: Pan And Zoom Behavior
page_title: .NET MAUI Chart Documentation | Pan And Zoom Behavior
description: Check our &quot;Pan And Zoom Behavior&quot; documentation article for Telerik Chart for .NET MAUI.
tags: chart, .net maui, pan, zoom, ui for maui
position: 4
slug: chart-behaviors-pan-and-zoom
---

# ChartPanAndZoomBehavior

With **ChartPanAndZoomBehavior**, RadChart handles the gestures drag, pinch open and pinch close which respectively cause panning, zooming in and zooming out of the associated chart plot area.

## Features

- **ZoomMode**: Gets or sets value that specifies how the chart will respond to a zoom gesture. The available values are:
	- None
	- Horizontal
	- Vertical
	- Both
- **PanMode**: Gets or sets value that specifies how the chart will respond to a pan gesture. The available values are:
	- None
	- Horizontal
	- Vertical
	- Both
- **HandleDoubleTap**: Determines whether a double-tap gesture will be handled by the behavior to reset the values of the Zoom and ScrollOffset (Pan) properties of the chart.

## Example

Here is an example of how the Chart PanAndZoom Behavior works:

Create the needed business objects, for example:

```C#
public class TemporalData
{
    public DateTime Date { get; set; }

    public double Value { get; set; }
}
```

Create a ViewModel:

```C#
public class ViewModel
{
    public ObservableCollection<TemporalData> Data { get; set; }

    public ViewModel()
    {
        this.Data = new ObservableCollection<TemporalData>(GetDateTimeData(200));
    }

    private static List<TemporalData> GetDateTimeData(int itemsCount)
    {
        var startDate = new DateTime(2015, 03, 01);

        List<TemporalData> items = new List<TemporalData>();
        for (int i = 0; i < itemsCount; i++)
        {
            TemporalData data = new TemporalData();
            data.Date = startDate.AddDays(i);

            if (i % 2 == 0)
            {
                data.Value = i + 5;
            }
            else
            {
                if (i % 5 == 0)
                {
                    data.Value = i - 15;
                }
            }

            items.Add(data);
        }

        return items;
    }
}
```

Declare a RadCartesianChart in XAML:

```XAML
<telerikChart:RadCartesianChart PaletteName="Light"
                                Zoom="2, 1">
    <telerikChart:RadCartesianChart.BindingContext>
        <local:ViewModel/>
    </telerikChart:RadCartesianChart.BindingContext>
    <telerikChart:RadCartesianChart.HorizontalAxis>
        <telerikChart:DateTimeContinuousAxis LabelFitMode="Rotate"
                                             MajorStepUnit="Day"
                                             PlotMode="OnTicks"
                                             LabelFormat="dd MMM"
                                             MajorStep="20"
                                             ShowLabels="True"/>
    </telerikChart:RadCartesianChart.HorizontalAxis>
    <telerikChart:RadCartesianChart.VerticalAxis>
        <telerikChart:NumericalAxis />
    </telerikChart:RadCartesianChart.VerticalAxis>
    <telerikChart:RadCartesianChart.Series>
        <telerikChart:LineSeries ValueBinding="Value"
                                 CategoryBinding="Date"
                                 DisplayName="Sales"
                                 ItemsSource="{Binding Data}"/>
    </telerikChart:RadCartesianChart.Series>
    <telerikChart:RadCartesianChart.ChartBehaviors>
        <telerikChart:ChartPanAndZoomBehavior ZoomMode="Horizontal" 
                                              PanMode="Horizontal" 
                                              HandleDoubleTap="True"/>
    </telerikChart:RadCartesianChart.ChartBehaviors>
</telerikChart:RadCartesianChart>
```

Here is the result:

![Chart Pan And Zoom Behavior](images/chart-behaviors-panandzoom.png "Chart Pan And Zoom Behavior")

# See Also

- [Chart Selection Behavior]({%slug chart-behaviors-selection%})
- [Chart Track Ball Behavior]({%slug chart-behaviors-trackball%})
- [Chart Tool Tip Behavior]({%slug chart-behaviors-tooltip%})

	
