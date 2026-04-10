---
title: Control DataGrid Operations from External UI with AI Prompts
description: Learn how to manage filtering, sorting, grouping, and column manipulations in the Telerik UI for .NET MAUI DataGrid component from an external UI using AI prompts.
type: how-to
meta_title: DataGrid AI operations from external UI
slug: datagrid-data-operations-external-ui
tags: datagrid, ui-for-net-maui, filter, ai feature, ai prompts, sorting, grouping, column manipulations
res_type: kb
---

## Environment

| Version | Product | Author |
| --- | --- | ---- |
| 13.0.0 | Telerik UI for .NET MAUI DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

This article demonstrates how to use an external UI (such as a prompt entry and button) to control DataGrid operations-filtering, sorting, grouping, and column manipulations-using AI prompts. This approach enables users to interact with the DataGrid in a natural language-driven way, enhancing usability and flexibility.

Common questions answered:
- How to use AI prompts to manage DataGrid operations from an external UI?
- How to integrate AI features for controlling DataGrid operations from an external UI?
- How to set up an external UI for managing DataGrid operations using AI prompts?

## Solution

Add a prompt entry and a button to your page. These controls allow users to enter natural language commands for the DataGrid.

1. Create an external UI in your XAML page, including a `RadEntry` for the prompt and a `RadTemplatedButton` to trigger the AI command.

```xaml
<!-- Place this in your page's XAML -->
<Grid RowDefinitions="Auto, *" RowSpacing="10">
    <HorizontalStackLayout Spacing="10">
        <telerik:RadEntry x:Name="entry"
                          Placeholder="Enter prompt for DataGrid operations"
                          WidthRequest="250"
                          Text="{Binding Prompt, Mode=TwoWay}"
                          ReturnCommand="{Binding ProcessAICommand}"/>
        <telerik:RadTemplatedButton x:Name="btn"
                                    Content="Send"
                                    Command="{Binding ProcessAICommand}"/>
    </HorizontalStackLayout>
    <telerik:RadDataGrid ItemsSource="{Binding Flights}"
                         AIRequestFunc="{Binding RequestFunc}"
                         AIResponseAction="{Binding ResponseAction}"
                         Grid.Row="1"
                         AutoGenerateColumns="False"
                         UserEditMode="Cell"
                         UserGroupMode="Enabled">
        <telerik:RadDataGrid.AISettings>
            <telerik:DataGridAISettings SuggestedPrompts="{Binding SuggestedPrompts}" />
        </telerik:RadDataGrid.AISettings>
        <telerik:RadDataGrid.Columns>
            <telerik:DataGridNumericalColumn HeaderText="Flight Number" PropertyName="FlightNumber" />
            <telerik:DataGridTextColumn HeaderText="Destination" PropertyName="To" />
            <telerik:DataGridTimeColumn HeaderText="Departure Time" PropertyName="DepartureTime" />
            <telerik:DataGridTimeColumn HeaderText="Arrival Time" PropertyName="ArrivalTime" />
            <telerik:DataGridTextColumn HeaderText="Company" PropertyName="Company" />
        </telerik:RadDataGrid.Columns>
    </telerik:RadDataGrid>
</Grid>
```

2. Create a `ViewModel` to handle the AI prompts and responses. The example below uses a demo AI service endpoint. For production, configure your own AI service as described in the [Getting Started with the AI Smart Assistant]({%slug datagrid-ai-prompt-overview%}#getting-started-with-the-ai-smart-assistant) article.

```csharp
public class FlightsViewModel : NotifyPropertyChangedBase
{
    private string prompt;
    private Func<string, string> requestFunc;
    private Action<string> responseAction;
    private static readonly HttpClient HttpClient = new HttpClient();
    private CancellationTokenSource cancellationTokenSource;
    private ICommand processAICommand;
    private ICommand cancelAICommand;
    private ObservableCollection<string> suggestedPrompts;

    public FlightsViewModel()
    {
        this.suggestedPrompts = this.CreateDefaultSuggestedPrompts();

        this.Flights = new ObservableCollection<FlightInfo>();

        string[] companies = new[]
        {
            "Air Buzz",
            "North Airlines",
            "United Airlines",
            "Southwest Airlines",
            "East Airlines",
            "Air Cargo",
            "Pacific Airlines",
        };

        string[] cities = new[]
        {
            "Seattle",
            "New York",
            "London",
            "Paris",
            "Berlin",
            "Tokyo",
            "Sydney",
            "Toronto",
            "San Francisco",
            "Chicago"
        };

        for (int i = 0; i < 50; i++)
        {
            var company = companies[i % companies.Length];
            var fromIndex = i % cities.Length;
            var toIndex = (i + 3) % cities.Length;
            if (toIndex == fromIndex)
            {
                toIndex = (toIndex + 1) % cities.Length;
            }

            var departureTime = TimeSpan.FromHours(i % 24).Add(TimeSpan.FromMinutes((i * 5) % 60));
            var arrivalTime = departureTime.Add(TimeSpan.FromHours(1 + (i % 2)));

            int flightNumber = 1000 + i;

            this.Flights.Add(new FlightInfo
            {
                Company = company,
                FlightNumber = flightNumber,
                DepartureTime = departureTime,
                ArrivalTime = arrivalTime,
                From = cities[fromIndex],
                To = cities[toIndex]
            });
        }
    }

    public string Prompt
    {
        get => this.prompt;
        set => this.UpdateValue(ref this.prompt, value);
    }
    public Func<string, string> RequestFunc
    {
        get => this.requestFunc;
        set => this.UpdateValue(ref this.requestFunc, value);
    }

    public Action<string> ResponseAction
    {
        get => this.responseAction;
        set => this.UpdateValue(ref this.responseAction, value);
    }


    public ObservableCollection<FlightInfo> Flights { get; private set; }

    public ObservableCollection<string> SuggestedPrompts => this.suggestedPrompts;

    public ICommand ProcessAICommand
    {
        get => this.processAICommand ?? (this.processAICommand = new Command(this.ExecuteProcessAI));
    }

    public ICommand CancelAICommand
    {
        get => this.cancelAICommand ?? (this.cancelAICommand = new Command(this.ExecuteCancelAI));
    }

    // example prompts for the user.
    private ObservableCollection<string> CreateDefaultSuggestedPrompts()
    {
        return new ObservableCollection<string>
        {
            "Group flights by destination column",
            "Filter flights that arrival time is before 9 AM",
            "Show flights which destination is Tokyo and Sydney",
            "Lock flight number column",
            "Reset all filters, grouping and sorting",
        };
    }

    private async void ExecuteProcessAI()
    {
        if (this.cancellationTokenSource != null)
        {
            // An AI request is already being processed
            return;
        }

        this.cancellationTokenSource = new CancellationTokenSource();

        try
        {
            var request = this.RequestFunc(this.Prompt);
            string response;

            var requestResult = await HttpClient.PostAsJsonAsync("https://demos.telerik.com/service/v2/ai/grid/smart-state", JsonSerializer.Deserialize<object>(request));
            response = await requestResult.Content.ReadAsStringAsync();

            if (!requestResult.IsSuccessStatusCode)
            {
                var errorMessage = $"Error {(int)requestResult.StatusCode} ({requestResult.ReasonPhrase}): {response}";
                await this.ShowErrorAsync(errorMessage);
                return;
            }

            if (!string.IsNullOrEmpty(response))
            {
                this.ResponseAction?.Invoke(response);
            }
        }
        catch (Exception ex)
        {
            await this.ShowErrorAsync($"Failed to process request: {ex.Message}");
        }
        finally
        {
            this.Prompt = string.Empty;
        }
    }

    private void ExecuteCancelAI()
    {
        this.cancellationTokenSource?.Cancel();
    }

    private async Task ShowErrorAsync(string message)
    {
#if NET10_0_OR_GREATER
        await Microsoft.Maui.Controls.Application.Current?.Windows[0].Page?.DisplayAlertAsync("Error", message, "OK");
#else
        await Microsoft.Maui.Controls.Application.Current?.Windows[0].Page?.DisplayAlert("Error", message, "OK");
#endif
    }
}

public class FlightInfo
{
    public string Company { get; set; }

    public int FlightNumber { get; set; }

    public TimeSpan ArrivalTime { get; set; }

    public TimeSpan DepartureTime { get; set; }

    public string From { get; set; }

    public string To { get; set; }
}
```

> Replace the demo AI endpoint with your own service for production use. See [AI Smart Assistant Setup]({%slug datagrid-ai-prompt-overview%}#getting-started-with-the-ai-smart-assistant).

3. In your page's code-behind, set the `BindingContext` to an instance of the ViewModel:

```csharp
this.BindingContext = new FlightsViewModel();
```

## Example Prompts

- "Group flights by destination column"
- "Filter flights that arrival time is before 9 AM"
- "Show flights which destination is Tokyo and Sydney"
- "Reset all filters, grouping and sorting"
