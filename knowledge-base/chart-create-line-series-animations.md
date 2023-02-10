---
title: Creating Line Series with Animation
page_title: Adding Animations to the Chart Line Series - .NET MAUI Knowledge Base
description: Learn how to create animations and add them to the Telerik UI for .NET MAUI Line Chart component.
type: how-to
slug: chart-how-to-create-custom-renderer
tags: maui, chart, animation, line, series, create, add
res_type: kb
---

## Environment

<table>
	<tbody>
    <tr>
      <td>Product</td>
      <td>Telerik UI for .NET MAUI Chart</td>
    </tr>
  	<tr>
  		<td>Product Version</td>
  		<td>2.0.0</td>
  	</tr>
	</tbody>
</table>


## Description

How can I add animations to my Telerik UI for .NET MAUI Line Chart?

## Solution

For the purpose of this example, let's consider that you need to apply animation to LineSeries in iOS.

**1.** Create a class which inherits from `Telerik.XamarinForms.ChartRenderer.iOS.CartesianChartRenderer` and override the `UpdateNativeWidget` and `CreateChartDelegate` methods:

```C#
	public class LineWithAnimationRenderer : CartesianChartRenderer
	{
		public LineWithAnimationRenderer()
		{
		}

		protected override void UpdateNativeWidget()
		{
			base.UpdateNativeWidget();
			this.Control.AllowAnimations = true;
		}

		protected override TKChartDelegate CreateChartDelegate(RadCartesianChart chart)
        {
            return new ChartWithAnimationDelegate(chart);
        }
	}
```

**2.** The `UpdateNativeWidget` method takes care of allowing animations for the Chart. The `CreateChartDelegate` method supplies an instance of a class that inherits from `TKChartDelegate`, configured with animations as per the [iOS chart help](https://docs.telerik.com/devtools/xamarin/nativecontrols/ios/chart/animations/custom). The `ChartWithAnimationDelegate` method inherits from `Telerik.XamarinForms.ChartRenderer.iOS.CartesianChartDelegate`, which in turn inherits from `TKChartdelegate`. As a result, you only need to extend it with the desired features:

```C#
	public class ChartWithAnimationDelegate : CartesianChartDelegate
	{
		public ChartWithAnimationDelegate()
		{
		}

		public override CAAnimation AnimationForSeries(TKChart chart, TKChartSeries series, TKChartSeriesRenderState state, CGRect rect)
		{
			var duration = 0.0;
			var animations = new List<CAAnimation>();
			for (int i = 0; i < (int)state.Points.Count; i++)
			{
				var pointKeyPath = state.AnimationKeyPathForPointAtIndex((uint)i);
				var keyPath = pointKeyPath + ".y";
				var point = state.Points.ObjectAtIndex((uint)i) as TKChartVisualPoint;
				var oldY = rect.Size.Height;

				if (i > 0)
				{
					var animation = new CAKeyFrameAnimation();
					animation.KeyPath = keyPath;
					animation.Duration = (double)(0.1 * i );
					animation.Values = new NSNumber[] { new NSNumber(oldY), new NSNumber(oldY), new NSNumber(point.Y) };
					animation.KeyTimes = new NSNumber[] { new NSNumber(0), new NSNumber(i / (i + 1.0)), new NSNumber(1.0) };
					animations.Add(animation);
					duration = animation.Duration;
				}
				else
				{
					var animation = new CABasicAnimation();
					animation.KeyPath = keyPath;
					animation.From = new NSNumber(oldY);
					animation.To = new NSNumber(point.Y);
					animation.Duration = 0.1;
					animations.Add(animation);
				}
			}

			var group = new CAAnimationGroup();
			group.Duration = duration;
			group.Animations = animations.ToArray();
			return group;
		}
	}
	chart.Palette = CustomPalettes.CustomDark;
```

**3.** Now, register your custom renderer by using the `ExportRenderer` assembly level attribute:

```C#	 
	[assembly: Xamarin.Forms.ExportRenderer(typeof(Telerik.XamarinForms.Chart.RadCartesianChart), typeof(LineWithAnimationRenderer))]
```

## See Also

- [Categorical Series Combine Mode]({%slug chart-series-combine-mode%})
- [Chart Legend]({%slug chart-features-legend%})
- [How To Create Custom Renderer]({%slug chart-how-to-create-custom-renderer%})
