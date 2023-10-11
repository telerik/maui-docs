---
title: NavigationItem Styling
page_title: .NET MAUI NavigationView Documentation - NavigationItem Styling
description: Learn how to style the navigation item inside the .NET MAUI NavigationView Pane.
position: 2
slug: navigationview-item-styling
---

# .NET MAUI NavigationItem Styling

Style the navigation item, by setting the `Style` property to the `NavigationViewItem` or use implicit style.

* Explicit style:

```XAML
<ContentView.Resources>
    <ResourceDictionary>
        <Style TargetType="telerik:NavigationViewItemView" x:Key="NavigationItemStyle">
            <Setter Property="Spacing" Value="10"/>
        </Style>
    </ResourceDictionary>
</ContentView.Resources>

<telerik:NavigationViewItem Text="Item 1" Style="{StaticResource NavigationItemStyle}" />
```

* Implicit style:

```XAML
<Style TargetType="telerik:NavigationViewItemView">
   <Setter Property="Spacing" Value="10"/>            
</Style>
```

The available properties are descrivbed in the table below:

| Property | Description |
| -------- | ----------- |
| `Command` (`ICommand`) | Executed when the navigation item is clicked. |
| `CommandParameter` (`object`) | Specifies a parameter to command which is executed when the navigation item is clicked. |
| `IsSelectable` (`bool`) | Specifies whether the navigation item is selectable. |
| `IsSelected` (`bool`) | Specifies whether the navigation item is selected. |
| `ImageSource` (`ImageSource`) | Specifies the source of the image that is displayed in the navigation item. |
| `ImageAspect` (`Microsoft.Maui.Aspect`) | Specifies the aspect ratio of the image that is displayed in the navigation item. |
| `ImageWidth` (`double`) | Specifies the width in pixels of the image that is displayed in the navigation item. |
| `ImageHeight` (`double`) | Specifies the height in pixels of the image that is displayed in the navigation item. |
| `Spacing` (`double`) | Specifies the spacing in pixels between the image area andthe content of the navigation item. |

## See Also

- [.NET MAUI NavigationView Forum Page](https://www.telerik.com/forums/maui?tagId=1978)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
