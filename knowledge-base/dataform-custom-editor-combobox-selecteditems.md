---
title: DataForm with Custom ComboBox Editor and SelectedItems collection
description: How to bind the ComboBox SelectedItems in DataForm CustomEditor Scenario
type: how-to
page_title: DataForm with Custom ComboBox Editor and SelectedItems collection
slug: dataform-custom-editor-combobox-selecteditems
position: 
tags: 
ticketid: 1617072
res_type: kb
---

## Environment
<table>
    <tbody>
        <tr>
            <td>Product</td>
            <td>DataForm for .NET MAUI</td>
        </tr>
    </tbody>
</table>


## Description

This article shows how to bind the ComboBox SelectedItems collection in DataForm Custom Editor scenario. 

## Solution

**1.** When using the ComboBox `SelectedItems` collection you have to set the `SelectionMode` to `Multiple`. 

**2.** Here is the DataForm definition in XAML with ComboBox set as a custom editor: 

```XAML
<telerik:RadDataForm x:Name="dataForm" CommitMode="Explicit" AutoGenerateItems="False">
    <telerik:DataFormCustomEditor PropertyName="Accommodation">
        <telerik:DataFormCustomEditor.EditorTemplate>
            <ControlTemplate>
                <VerticalStackLayout>
                    <telerik:RadComboBox Text="{Binding Value, Mode=TwoWay, Source={RelativeSource Mode=TemplatedParent}}" 
                                            SelectionMode="Multiple"
                                            ItemsSource="{Binding AvailableAccommodations}"
                                            SelectedItems="{Binding Values}"/>
                </VerticalStackLayout>
            </ControlTemplate>
        </telerik:DataFormCustomEditor.EditorTemplate>
    </telerik:DataFormCustomEditor>
</telerik:RadDataForm>
```

**3.** DataForm needs a binding context. Here is a sample ViewModel implementation. Also the property bound to the SelectedItems - `Values` is a property defined in the ViewModel. For `Values`, you can subscribe to `CollectionChanged` event to listed for changes. For example, when item is added/removed to/from the collection.

```C#
public class CustomEditorViewModel : NotifyPropertyChangedBase
{
    private string accommodation;
    private ObservableCollection<object> selectedItems;

    public CustomEditorViewModel()
    {
        this.AvailableAccommodations = new[]
        {
            "Single Room",
            "Double Room",
            "Appartment",
            "House",
            "new House",
            "new apartment",
            "my apartment",
            "hallo",
        };
    }

    [Required]
    public string Accommodation
    {
        get => this.accommodation;
        set => this.UpdateValue(ref this.accommodation, value);
    }

    [NotMapped]
    public IList<string> AvailableAccommodations { get; }


    public ObservableCollection<object> Values
    {
        get
        {
            return this.selectedItems;
        }
        set
        {
            if (this.selectedItems != value)
            {

                if (this.selectedItems != null)
                {
                    this.selectedItems.CollectionChanged -= SelecteDItems_CollectionChanged;
                }

                this.selectedItems = value;

                this.selectedItems.Add(this.AvailableAccommodations[0]);
                this.selectedItems.Add(this.AvailableAccommodations[1]);


                if (this.selectedItems != null)
                {
                    this.selectedItems.CollectionChanged += SelecteDItems_CollectionChanged;
                }

                OnPropertyChanged();
            }
        }
    }
    private void SelecteDItems_CollectionChanged(object sender, System.Collections.Specialized.NotifyCollectionChangedEventArgs e)
    {
        if (e.Action == NotifyCollectionChangedAction.Add)
        {

        }
        else if (e.Action == NotifyCollectionChangedAction.Remove) 
        { 

        }
    }
}
```

**4.** Then set the `CustomEditorViewModel` as a `BindingContext` to the Page:

```
this.BindingContext = new CustomEditorViewModel();
```
