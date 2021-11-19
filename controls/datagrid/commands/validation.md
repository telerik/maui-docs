---
title: Validation Command
page_title: .NET MAUI DataGrid Documentation | Validation Command
description: Check our &quot;Validation Command&quot; documentation article for Telerik DataGrid for .NET MAUI control.
position: 3
slug: datagrid-commands-validation
---

# Validation Command

The DataGrid control provides a validation command that has an entry point for validating cells content. The execution parameter is of type `ValidateCellContext` and exposes the following properties:

* `CellInfo`&mdash;Gets the cell information associated with the operation.
* `Errors`&mdash;Gets or sets the errors (if any) that occurred during the validation.

## Example

Here is an example how the DataGrid `ValidateCell` command works:

First, create a `Data` class (the business object) that inherits from the `INotifyDataErrorInfo` and `INotifyPropertyChanged` interfaces. For demonstration purposes, the example will do the validation through the `INotifyDataErrorInfo` interface.

<snippet id='datagrid-commands-validation-businessobject'/>
```C#
public class Data : INotifyDataErrorInfo, INotifyPropertyChanged
{
    private Dictionary<string, HashSet<object>> errors = new Dictionary<string, HashSet<object>>();
    private string country;

    public string Country
    {
        get
        {
            return this.country;
        }

        set
        {
            this.country = value;

            if (this.country.Length > 15)
            {
                this.AddError("Country", string.Format("Country too long", new DateTime()));
            }
            else
            {
                this.RemoveErrors("Country");
            }

            this.OnPropertyChanged("Country");
        }
    }

    public string Capital { get; set; }

    public bool HasErrors
    {
        get
        {
            return this.errors.Count > 0;
        }
    }

    public IEnumerable GetErrors(string propertyName)
    {
        if (string.IsNullOrEmpty(propertyName))
        {
            return this.errors.SelectMany(c => c.Value);
        }

        HashSet<object> propertyErrors;

        this.errors.TryGetValue(propertyName, out propertyErrors);

        return propertyErrors ?? Enumerable.Empty<object>();
    }

    protected virtual void AddError(string propertyName, object errorMessage)
    {
        HashSet<object> propertyErrors;

        if (!this.errors.TryGetValue(propertyName, out propertyErrors))
        {
            propertyErrors = new HashSet<object>();
            this.errors.Add(propertyName, propertyErrors);

            propertyErrors.Add(errorMessage);

            this.OnErrorsChanged(propertyName);
        }
        else
        {
            if (!propertyErrors.Contains(errorMessage))
            {
                propertyErrors.Add(errorMessage);
                this.OnErrorsChanged(propertyName);
            }
        }
    }

    protected virtual void RemoveErrors(string propertyName = null)
    {
        if (string.IsNullOrEmpty(propertyName))
        {
            if (this.errors.Count > 0)
            {
                this.errors.Clear();
                this.OnErrorsChanged(propertyName);
            }
        }
        else
        {
            if (this.errors.Remove(propertyName))
            {
                this.OnErrorsChanged(propertyName);
            }
        }
    }

    public event EventHandler<DataErrorsChangedEventArgs> ErrorsChanged;

    protected virtual void OnErrorsChanged(string propertyName)
    {
        if (this.ErrorsChanged != null)
        {
            this.ErrorsChanged(this, new DataErrorsChangedEventArgs(propertyName));
        }
    }

    public event PropertyChangedEventHandler PropertyChanged;

    protected void OnPropertyChanged(string name)
    {
        PropertyChangedEventHandler handler = PropertyChanged;
        if (handler != null)
        {
            handler(this, new PropertyChangedEventArgs(name));
        }
    }
}
```

Then, create a `ViewModel` with a collection of `Data` objects:

<snippet id='datagrid-commands-validation-viewmodel'/>
```C#
public class ViewModel : INotifyPropertyChanged
{
    public ObservableCollection<Data> Items { get; set; }
    public ViewModel()
    {
        this.Items = new ObservableCollection<Data>()
        {
             new Data { Country = "India", Capital = "New Delhi"},
             new Data { Country = "South Africa", Capital = "Cape Town"},
             new Data { Country = "Nigeria", Capital = "Abuja" },
             new Data { Country = "Singapore", Capital = "Singapore" }
       };
    }

    public event PropertyChangedEventHandler PropertyChanged;

    protected void OnPropertyChanged(string name)
    {
        PropertyChangedEventHandler handler = PropertyChanged;
        if (handler != null)
        {
            handler(this, new PropertyChangedEventArgs(name));
        }
    }
}
```

Then, handle the `CellTap` action as a `Command`. First, create a class that inherits from the `DataGridCommand` and set its `Id` property accordingly. You will also need to override the `CanExecute` and `Execute` methods as demonstrated in the example below:

<snippet id='datagrid-commands-validation-validatecell'/>
```C#
public class ValidateCellCommand : DataGridCommand
{
    Grid grid;
    public ValidateCellCommand(Grid grid)
    {
        this.Id = DataGridCommandId.ValidateCell;
        this.grid = grid;
    }

    public override void Execute(object parameter)
    {
        var context = (ValidateCellContext)parameter;
        this.grid.IsVisible = context.Errors.Count > 0;
    }
}
```

Then, set the `BindingContext` to be the `ViewModel` and add this command to the `Commands` collection of the `RadDataGrid` instance:

<snippet id='datagrid-commands-validation-binding'/>
```C#
this.BindingContext = new ViewModel();
this.dataGrid.Commands.Add(new ValidateCellCommand(errorContainer));
```

Define the DataGrid in XAML:

<snippet id='datagrid-commands-validation'/>
```XAML
<Grid Margin="0,20,0,0">
    <Grid.RowDefinitions>
        <RowDefinition Height="Auto"/>
        <RowDefinition/>
    </Grid.RowDefinitions>
    <Grid x:Name="errorContainer"
          IsVisible="false">
        <BoxView BackgroundColor="DarkRed" />
        <Label Text="country name length must be less than 15 symbols"
               FontSize="15"
               HorizontalOptions="CenterAndExpand"
               VerticalOptions="CenterAndExpand"
               HorizontalTextAlignment="Center"
               TextColor="White"/>
    </Grid>

    <telerikDataGrid:RadDataGrid x:Name="dataGrid"
                                 Grid.Row="1"
                                 UserEditMode="Cell"
                                 AutoGenerateColumns="True"
                                 ItemsSource="{Binding Items}">
    </telerikDataGrid:RadDataGrid>
</Grid>
```

## See Also

- [CellTap Command]({%slug datagrid-commands-cell-tap%})
- [Editing Command]({%slug datagrid-commands-editing%})
- [Columns Styling]({%slug datagrid-columns-styling%})
