---
title: ToolTip Behavior
page_title: .NET MAUI Chart Documentation | ToolTip Behavior
description: Check our &quot;Tool Tip Behavior&quot; documentation article for Telerik Chart for .NET MAUI
position: 3
slug: chart-behaviors-tooltip
---

# ToolTip Behavior

The Tooltip behavior of the Chart is responsible for rendering concise information about a data point in a small popup which is displayed close to its relevant data point.

## Features

The ToolTip behavior of the Chart supports the `TriggerMode` property that determines the gestures on which the `ChartToolTipBehavior` will show a tool tip. The available values are:
	- `Tap`
	- `Hold`

## Example

The following example shows how the ToolTip behavior of the Chart works:

1. Create the business object:

 ```C#
public class TemporalData
{
    public DateTime Date { get; set; }

    public double Value { get; set; }
}
 ```

1. Create a `ViewModel`:

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

1. Declare a `RadCartesianChart` in XAML:

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

The following image shows how the ToolTip looks:

![Chart Tooltip Behavior](images/chart-behaviors-tooltip.png)

# See Also

- [Chart Selection Behavior]({%slug chart-behaviors-selection%})
- [Chart Track Ball Behavior]({%slug chart-behaviors-trackball%})
- [Chart Pan And Zoom Behavior]({%slug chart-behaviors-pan-and-zoom%})
