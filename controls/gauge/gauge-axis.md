---
title: Axis
page_title: .NET MAUI Gauge Documentation | Axis
description: Check our &quot;Axis&quot; documentation article for Telerik Gauge for .NET MAUI control.
position: 4
slug: gauge-axis
---

# Gauge Axis

The axis is a gauge element that is used to control everything related to the display of the axis. This includes ticks, labels, appearance and axis range. 

## Examples

### Axis Range

Presently, the axis does not have an auto-range mechanism so it is mandatory that you set **Minimum**, **Maximum** and **Step**.

```XAML
<telerikGauges:GaugeLinearAxis Maximum="4"
                               Minimum="0"
                               Step="0.5" />
```

![Gauge Axis Range](images/gauge-axis-range.png)

## Appearance

You can control the stroke of the axis line and ticks via the **Stroke** property. If you need to have a different color for the ticks you need to set the **TickStroke** property. Similarly, setting the **StrokeThickness** affects both the axis line and ticks. If you need ticks with a different stroke thickness you need to set the **TickThickness** property.

```XAML
<telerikGauges:GaugeLinearAxis Maximum="4"
                               Minimum="0"
                               Step="0.5"
                               Stroke="#FFDD789B"
                               StrokeThickness="1"
                               TextColor="#FF4062AD"
                               TickStroke="#FFAAC271"
                               TickThickness="2" />
```

![Gauge Appearance](images/gauge-axis-appearance.png)

## Font Style

You can control the appearance of the labels via the **FontSize**, **FontFamily** and **FontAttributes** properties.

```XAML
<telerikGauges:GaugeLinearAxis FontAttributes="Bold"
                               FontSize="30"
                               Maximum="4"
                               Minimum="0"
                               Step="0.5" />
```

![Gauge Font Style](images/gauge-axis-fontstyle.png)

## FontFamily

Note that the **FontFamily** property is of type string and you need to pass the name of the font family. Remember that the different platforms work with different fonts so you may need to use the **OnPlatform** method.

<snippet id='gauge-axis-font-family'/>

![Gauge Font Familly](images/gauge-axis-fontfamily.png)

## Label Format

You can control the numeric format of the content of the labels. The default label format is "G7".

```XAML
<telerikGauges:GaugeLinearAxis LabelFormat="N2"
                               Maximum="4"
                               Minimum="0"
                               Step="0.5" />
```							   

![Gauge example](images/gauge-axis-label-format.png)

## Label And Tick Position

In the radial gauge, the gauge elements can be positioned on the inside or on the outside of the axis line. Some of the elements, such as the ticks, can also be centered on the axis line. This is controlled by the Position property of the concrete element.

```XAML
<telerikGauges:GaugeLinearAxis LabelPosition="Start"
                               Maximum="4"
                               Minimum="0"
                               Step="0.5"
                               TickPosition="Start" />
```
							   
![Gauge example](images/gauge-axis-label-and-tick-position.png)

## Offset And Length

The distance between the concrete element and the axis line is defined by an offset property (**Offset**, **TickOffset**, **LabelOffset**). You can also specify the length of the ticks.

```XAML
<telerikGauges:GaugeLinearAxis LabelOffset="8"
                               Maximum="4"
                               Minimum="0"
                               Step="0.5"
                               TickLength="3"
                               TickOffset="3" />
```							   

![Gauge Offset and Length](images/gauge-axis-offset-and-length.png)

## See Also

- [Indicators]({%slug gauge-indicators%})
- [Positioning]({%slug gauge-positioning%})
- [Ranges]({%slug gauge-ranges%})
