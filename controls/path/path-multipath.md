---
title: MultiPath
page_title: .NET MAUI Path Documentation | MultiPath
description: Check our &quot;MultiPath&quot; documentation article for Telerik Path for .NET MAUI.
position: 3
slug: path-multipath
---

# MultiPath

RadMultiPath allows you to combine several PathGeometry objects into a single element. The MultiPath contains a collection of **RadPathDefinition** objects and each of them provides a **Geometry** property as well as the same styling properties as the RadPath.

Here is a an example of RadMultiPath definition:

```XAML
    <Grid x:Name="root">
        <Grid.RowDefinitions>
          <RowDefinition />
          <RowDefinition />
        </Grid.RowDefinitions>
        <telerikPrimitives:RadMultiPath x:Name="multiPath"
                                  Grid.Row="0"
                                  HorizontalOptions="Center"
                                  VerticalOptions="Center">
            <telerikPrimitives:RadPathDefinition Fill="#FF4285F4">
                <telerikCommon:RadPathGeometry>
                    <telerikCommon:RadPathFigure>
                        <telerikCommon:RadArcSegment Center="0.5, 0.5" SweepAngle="360" Size="0.9, 0.9" />
                    </telerikCommon:RadPathFigure>
                </telerikCommon:RadPathGeometry>
            </telerikPrimitives:RadPathDefinition>
            <telerikPrimitives:RadPathDefinition Fill="#FFEA4335">
                <telerikCommon:RadPathGeometry>
                    <telerikCommon:RadPathFigure>
                        <telerikCommon:RadArcSegment Center="0.5, 0.5" SweepAngle="360" Size="0.6, 0.6" />
                    </telerikCommon:RadPathFigure>
                </telerikCommon:RadPathGeometry>
            </telerikPrimitives:RadPathDefinition>
            <telerikPrimitives:RadPathDefinition Fill="#FFFBBC05">
                <telerikCommon:RadPathGeometry>
                    <telerikCommon:RadPathFigure>
                        <telerikCommon:RadArcSegment Center="0.5, 0.5" SweepAngle="360" Size="0.3, 0.3" />
                    </telerikCommon:RadPathFigure>
                </telerikCommon:RadPathGeometry>
            </telerikPrimitives:RadPathDefinition>
        </telerikPrimitives:RadMultiPath>
        <telerikPrimitives:RadMultiPath x:Name="path2"
                                  Grid.Row="1"
                                  HorizontalOptions="Center"
                                  VerticalOptions="Center">
    <telerikPrimitives:RadPathDefinition Stroke="#FF364781" StrokeThickness="{StaticResource strokeThickness}">
      <telerikCommon:RadPathGeometry>
        <telerikCommon:RadPathFigure StartPoint="0.95, 0.95">
          <telerikCommon:RadLineSegment Point="0.75, 0.75" />
        </telerikCommon:RadPathFigure>
      </telerikCommon:RadPathGeometry>
    </telerikPrimitives:RadPathDefinition>
    <telerikPrimitives:RadPathDefinition Fill="#FF64B5FF" Stroke="#FF616161" StrokeThickness="{StaticResource strokeThickness}">
      <telerikCommon:RadPathGeometry>
        <telerikCommon:RadPathFigure StartPoint="0.75, 0.75">
          <telerikCommon:RadArcSegment Center="0.4, 0.4" StartAngle="-45" SweepAngle="360" Size="0.7, 0.7" />
        </telerikCommon:RadPathFigure>
      </telerikCommon:RadPathGeometry>
    </telerikPrimitives:RadPathDefinition>
    <telerikPrimitives:RadPathDefinition Fill="#FFBDE0FF">
      <telerikCommon:RadPathGeometry>
        <telerikCommon:RadPathFigure StartPoint="0.241, 0.241">
          <telerikCommon:RadArcSegment Center="0.4, 0.4" StartAngle="135" SweepAngle="-90" Size="0.45, 0.45" />
          <telerikCommon:RadArcSegment Center="0.541, 0.259" StartAngle="45" SweepAngle="-180" Size="0.05, 0.05" />
          <telerikCommon:RadArcSegment Center="0.4, 0.4" StartAngle="45" SweepAngle="90" Size="0.35, 0.35" />
          <telerikCommon:RadArcSegment Center="0.259, 0.259" StartAngle="-45" SweepAngle="-180" Size="0.05, 0.05" />
        </telerikCommon:RadPathFigure>
      </telerikCommon:RadPathGeometry>
    </telerikPrimitives:RadPathDefinition>
  </telerikPrimitives:RadMultiPath>
</Grid>
```

The image below shows the result:

![RadMultiPath](images/path_multipath.png)

## See Also

- [PathGeometry]({% slug path-structure %})
- [Styling]({% slug path-styling %})