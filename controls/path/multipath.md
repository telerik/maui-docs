---
title: MultiPath
page_title: .NET MAUI Path Documentation - MultiPath
description: Check our &quot;MultiPath&quot; documentation article for Telerik Path for .NET MAUI.
position: 4
previous_url: /controls/path/path-multipath
slug: path-multipath
---

# MultiPath

The MultiPath allows you to combine several PathGeometry objects into a single element. The MultiPath contains a collection of `RadPathDefinition` objects and each of them provides a `Geometry` property as well as the same styling properties as the Path.

The following example demonstrates how to define a `RadMultiPath`.

<snippet id='path-multipath-xaml' />

The following code demonstrates the logic behind changing the Grid size:

```C#
public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();
        this.root.SizeChanged += Root_SizeChanged;
    }

    private void Root_SizeChanged(object sender, EventArgs e)
    {
        double size = Math.Min(this.root.Width, this.root.Height / 2);
        this.multiPath.WidthRequest = size;
        this.multiPath.HeightRequest = size;
        this.path2.WidthRequest = size;
        this.path2.HeightRequest = size;
    }
}
```

The image below shows the result:

![RadMultiPath](images/path_multipath.png)

## See Also

- [PathGeometry]({% slug path-structure %})
- [Styling]({% slug path-styling %})
