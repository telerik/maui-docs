---
title: DateTimeContinuous Axis
page_title: Xamarin Chart Documentation | DateTimeContinuous Axis
slug: axes-date-time-continuous-axis
description: Check our &quot;DateTimeContinuous Axis&quot; documentation article for Telerik Chart for Xamarin control.
---

# DateTimeContinuousAxis

## Overview

The **DateTimeContinuousAxis** is a special axis that extends the base CartesianAxis class and may be considered as a hybrid between a categorical and a numerical axis. DateTimeContinuousAxis works with categorical data but instead of categories, the axis builds time slots depending on its Minimum, Maximum and MajorStep values.
DateTimeContinuousAxis also expects valid DateTime values so that the data could be plotted correctly. Think of DateTimeContinuousAxis as a timeline where each data point has a certain position, depending on its DateTime value. The timeline range properties are automatically calculated if not set explicitly by the user: the default value of the major step is the smallest difference between any two DateTime values. There might be empty time slots if no data falling into them is found, because the axis behaves like a numerical one.

The **CategoricalAxis** inherits from the base **Axis** class. You can see the inherited properties [here]({% slug axes-overview %}).

## Features

- **Minimum**: Defines the start value of the timeline. Specify DateTime.Minimum to clear the value and force the axis to determine it automatically, depending on the smallest DateTime value present.
- **Maximum**: Defines the end value of the timeline. Specify DateTime.Maximum to clear the value and force the axis to determine it automatically, depending on the biggest DateTime value present.
- **PlotMode**: Defines the strategy used to position data points along the axis time slots. Two different options are available: { BetweenTicks, OnTicks }.
- **MajorStep**: Defines the user-defined step between two adjacent time slots. Specify double.PositiveInfinity to clear the value and make the axis calculate an automatic step, depending on the smallest difference between any two dates.
- **MajorStepUnit**: Defines what DateTime component the MajorStep property refers to { Year, Quarter, Month, Week, Day, Hour, Minute, Second, Millisecond }.
- **GapLength**: Defines the distance (in logical units [0,1]) between two adjacent time slots. The default value is 0.3. As an example, if you have two BarSeries combined in Cluster mode, you can remove the space between the bars by setting the GapLength property to 0.

## Example

Here is an example how to format axis labes on DateTimeContinuous Axis:

Create the needed business objects:

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
        this.Data = GetDateTimeData(6);
    }

    private static ObservableCollection<TemporalData> GetDateTimeData(int itemsCount)
    {
        var startDate = new DateTime(2015, 03, 01);

        ObservableCollection<TemporalData> items = new ObservableCollection<TemporalData>();
        for (int i = 0; i < itemsCount; i++)
        {
            TemporalData data = new TemporalData();
            data.Date = startDate.AddDays(i);
            data.Value = Math.Sin(i);

            items.Add(data);
        }

        return items;
    }
}
```

Create a class, for example DateLabelFormatter that inherits from **LabelFormatterBase<DateTime>** for DateTimeContinuous Axis

```C#
public class DateLabelFormatter : LabelFormatterBase<DateTime>
{
    public override string FormatTypedValue(DateTime value)
    {
        if (value.Day == 1)
        {
            return value.Day + "st";
        }
        else if (value.Day == 2)
        {
            return value.Day + "nd";
        }
        else if (value.Day == 3)
        {
            return value.Day + "rd";
        }
        else
        {
            return value.Day + "th";
        }
    }
}
```

Finally, use the following snippet to declare the RadChart in XAML :

```XAML
<telerikChart:RadCartesianChart>
	<telerikChart:RadCartesianChart.BindingContext>
	    <local:ViewModel />
	</telerikChart:RadCartesianChart.BindingContext>
	<telerikChart:RadCartesianChart.HorizontalAxis>
	    <telerikChart:DateTimeContinuousAxis LabelFitMode="Rotate"
	                                         MajorStepUnit="Day">
	        <telerikChart:DateTimeContinuousAxis.LabelFormatter>
	            <local:DateLabelFormatter />
	        </telerikChart:DateTimeContinuousAxis.LabelFormatter>
	    </telerikChart:DateTimeContinuousAxis>
	</telerikChart:RadCartesianChart.HorizontalAxis>
	<telerikChart:RadCartesianChart.VerticalAxis>
	    <telerikChart:NumericalAxis LabelFormat="C"
	                                MajorStep="0.5"
	                                Minimum="-1"
	                                Maximum="1" />
	</telerikChart:RadCartesianChart.VerticalAxis>
	<telerikChart:RadCartesianChart.Series>
	    <telerikChart:LineSeries ValueBinding="Value"
	                             CategoryBinding="Date"
	                             ItemsSource="{Binding Data}" />
	</telerikChart:RadCartesianChart.Series>
</telerikChart:RadCartesianChart>
```

Here is how the DateTimeContinuous Axis Formatter looks:

![DateTimeContinuous Axis](images/chart-date-time-continuous-axis-example.png)

## See Also

- [Categorical Axis]({%slug axes-categorical-axis%})
- [Numerical Axis]({%slug axes-numerical-axis%})
- [Axis Overview]({%slug axes-overview%})
