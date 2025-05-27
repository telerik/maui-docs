---
title: Using ItemTemplateSelector with CollectionView for .NET MAUI
description: Learn how to implement an ItemTemplateSelector in the CollectionView for .NET MAUI to customize item appearance at runtime.
type: how-to
page_title: Implementing ItemTemplateSelector in CollectionView for .NET MAUI
slug: item-template-selector-collectionview-dotnet-maui
tags: collectionview, datatemplate, itemtemplate, selector, .net-maui
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.0.0 | Telerik UI for .NET MAUI CollectionView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I am migrating from `RadListView` to [CollectionView](https://docs.telerik.com/devtools/maui/controls/collectionview/overview) for .NET MAUI. In `RadListView`, I used the `RadListView.ItemTemplateSelector` to dynamically select item templates at runtime. However, I could not find an equivalent feature for the CollectionView. How can I achieve dynamic item template selection in the CollectionView?

This knowledge base article also answers the following questions:
- How to use `ItemTemplateSelector` in CollectionView for .NET MAUI?
- How to dynamically select templates in CollectionView?
- Implementing custom `DataTemplateSelector` for CollectionView?

## Solution

To achieve dynamic item template selection in the CollectionView, you can use the `DataTemplateSelector` provided by .NET MAUI. The `DataTemplateSelector` enables you to define logic for choosing different templates based on item properties.

**1.** Create a custom template selector class that inherits from `DataTemplateSelector`. Override the `OnSelectTemplate` method to provide logic for selecting the appropriate template.

```csharp
   using Microsoft.Maui.Controls;

   public class CustomTemplateSelector : DataTemplateSelector
   {
       public DataTemplate TemplateOne { get; set; }
       public DataTemplate TemplateTwo { get; set; }

       protected override DataTemplate OnSelectTemplate(object item, BindableObject container)
       {
           var myItem = item as MyItemType;
           if (myItem != null && myItem.Condition)
           {
               return TemplateOne;
           }
           return TemplateTwo;
       }
   }
```

**2.** Declare the templates and the custom selector in your XAML file.

```xml
   <ResourceDictionary>
       <DataTemplate x:Key="TemplateOne">
           <Label Text="{Binding PropertyOne}" />
       </DataTemplate>
       <DataTemplate x:Key="TemplateTwo">
           <Label Text="{Binding PropertyTwo}" />
       </DataTemplate>

       <local:CustomTemplateSelector x:Key="CustomSelector" 
                                     TemplateOne="{StaticResource TemplateOne}" 
                                     TemplateTwo="{StaticResource TemplateTwo}" />
   </ResourceDictionary>
```

**3.** Set the `ItemTemplate` property of the CollectionView to the custom template selector.

```xml
<telerik:RadCollectionView ItemsSource="{Binding Items}" 
                                                 ItemTemplate="{StaticResource CustomSelector}" />
```

## See Also

- [CollectionView Overview](https://docs.telerik.com/devtools/maui/controls/collectionview/overview)
- [Data Binding in CollectionView](https://docs.telerik.com/devtools/maui/controls/collectionview/data-binding#item-appearance-at-runtime)
- [Microsoft Documentation: DataTemplateSelector](https://learn.microsoft.com/en-us/dotnet/maui/fundamentals/datatemplate?view=net-maui-9.0#create-a-datatemplateselector)
