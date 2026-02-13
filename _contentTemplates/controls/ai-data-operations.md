#ai-smart-assistant-operations
- **Sorting**&mdash;Users can sort the control by specifying the column and the sort direction (ascending or descending).
- **Filtering**&mdash;Users can filter the control based on specific criteria.
- **Column Manipulation**&mdash;Users can freeze, hide columns and more.
#end

#getting-started-with-the-ai-smart-assistant
### Prerequisites

1. `.NET9` or later.
1. An AI provider. For example **Azure OpenAI** or **OpenAI**, etc.
1. `Telerik.AI.SmartComponents.Extensions` package.

### 1. Getting Started with the Telerik.AI.SmartComponents.Extensions

The AI Smart Assistant functionality relies on the [`Telerik.AI.SmartComponents.Extensions`](https://www.nuget.org/packages/Telerik.AI.SmartComponents.Extensions) package. The package provides the necessary extensions to integrate AI capabilities into the control. 

1. Install the [`Telerik.AI.SmartComponents.Extensions`](https://www.nuget.org/packages/Telerik.AI.SmartComponents.Extensions) package in your .NET MAUI project.

```script
dotnet add package Telerik.AI.SmartComponents.Extensions
```
```xml
<PackageReference Include="Telerik.AI.SmartComponents.Extensions" Version="Select Latest" />
```

The `Telerik.AI.SmartComponents.Extensions` package has a dependency to the `Microsoft.Extensions.AI` package.

2. Configure the AI services in your application. This typically involves setting up an AI provider (such as **Azure OpenAI**, **OpenAI**, etc.) and providing the necessary API keys or credentials.

3. Register the AI service and AI chat client in your application.

    For the example, we will use the **Azure OpenAI**. For the demo, in order to register the AI service and chat client, the following code is needed in MauiProgram.cs:

    ```C#
    builder.Services.AddSingleton(sp =>
    {
        return new AzureOpenAIClient(new Uri("AZURE_OPENAI_ENDPOINT"), new AzureKeyCredential("AZURE_OPENAI_API_KEY"));
    });

    builder.Services.AddChatClient(services =>
        services.GetRequiredService<AzureOpenAIClient>().GetChatClient("gpt-4.1").AsIChatClient()
    );
    ```
#end

#process-requests
1. How to access the AI model in the ViewModel is a developer decision.

1. The `Telerik.AI.SmartComponents.Extensions` library provides two key methods:
    - `AddGridChatTools()`&mdash;Configures the AI model with DataGrid-specific capabilities.
    - `ExtractGridResponse()`&mdash;Extracts structured commands and messages from the AI response that the DataGrid can understand.

    For the demo we will use a command in the `ViewModel`. The command is bind to the DataGrid `UserCommand`. The command executes when a prompt is submitted from the AI Smart Assistant panel. 

    Here is a sample `ViewModel` definition:

    ```C#
    public class AIPromptViewModel : NotifyPropertyChangedBase
    {
        private CancellationTokenSource cancellationTokenSource;
        private ICommand processAICommand;
        private ICommand cancelAICommand;
        private readonly IChatClient chatClient;

        public AIPromptViewModel(IChatClient chatClient)
        {
            this.chatClient = chatClient;
        }

        public ICommand ProcessAICommand
        {
            get => this.processAICommand ?? (this.processAICommand = new Command<DataGridPromptRequestCommandContext>(this.ExecuteProcessAI));
        }

        public ICommand CancelAICommand
        {
            get => this.cancelAICommand ?? (this.cancelAICommand = new Command(this.ExecuteCancelAI));
        }

        private async void ExecuteProcessAI(DataGridPromptRequestCommandContext context)
        {
            if (this.cancellationTokenSource != null)
            {
                // An AI request is already being processed
                return;
            }

            this.cancellationTokenSource = new CancellationTokenSource();

            try
            {
                var request = JsonSerializer.Deserialize<GridAIRequest>(context.RequestJson);

                var options = new ChatOptions();
                options.AddGridChatTools(request.Columns);

                List<ChatMessage> messages = request.Contents.Select(m => new ChatMessage(ChatRole.User, m.Text)).ToList();

                ChatResponse completion = await this.chatClient.GetResponseAsync(messages, options); ;
                var response = JsonSerializer.Serialize(completion.ExtractGridResponse(), new JsonSerializerOptions() { PropertyNamingPolicy = JsonNamingPolicy.CamelCase });

                context.ResponseJson = response;
            }
            catch (OperationCanceledException)
            {
                // Cancellation was already handled by setting ProcessingState to Canceled
                // No need to set it again here
            }
            catch (Exception ex)
            {
                await this.ShowErrorAsync($"Failed to process request: {ex.Message}");
                context.HasError = true;
            }
            finally
            {
                this.cancellationTokenSource?.Dispose();
                this.cancellationTokenSource = null;
            }
        }

        private void ExecuteCancelAI()
        {
            this.cancellationTokenSource?.Cancel();
        }

        protected async Task ShowErrorAsync(string message)
        {
    #if NET10_0_OR_GREATER
            await Microsoft.Maui.Controls.Application.Current?.Windows[0].Page?.DisplayAlertAsync("Error", message, "OK");
    #else
            await Microsoft.Maui.Controls.Application.Current?.Windows[0].Page?.DisplayAlert("Error", message, "OK");
    #endif
        }
    }
    ```

    * Deserializes the incoming `JSON` `(context.RequestJson)` into a `GridAIRequest`. This contains grid columns and user prompt contents.

    * Creates `ChatOptions` and registers DataGrid-specific tools via `options.AddGridChatTools(request.Columns)` so the AI knows what columns/operations are available.

    * Maps each request content to a `ChatMessage` with `ChatRole.User`.

    * Calls the AI backend through `IChatClient.GetResponseAsync(messages, options)` to get a `ChatResponse`.

    * Extracts the grid-specific instruction from the AI result with `completion.ExtractGridResponse()`.

    * Serializes the response to a `JSON` and assign to `context.ResponseJson` for the DataGrid to consume.

1. Get the service registered in the `MauiProgram.cs` and pass it to the instance of the `ViewModel`. Then set the binding context of the page to be this `ViewModel`.

    ```C#
    var chatClient = Application.Current.Handler.MauiContext.Services.GetRequiredService<IChatClient>();
    this.viewModel = new AIPromptViewModel(chatClient);
    this.BindingContext = this.viewModel;
    ```
#end

#example-prompts
- "Sort the data by the Name column in ascending order."
- "Filter the data to show only items with a price greater than 100."
- To freeze a column use the `lock` keyword. For example: "Lock the Price column."
#end

#ai-smart-assistant-settings
You can configure the default settings for the AI Smart Assistant functionality using the `AISettings` (of type `Telerik.Maui.Controls.DataGrid.DataGridAISettings`) property of the DataGrid. 

Below you can find a list of the available configuration options applied through the `RadDataGrid.AISettings`:

* `InputText` (`string`)&mdash;Specifies the text of the input field.
* `SubmitPromptOnSelection` (`bool`)&mdash;Specifies whether selecting a prompt should automatically submit the request. The default value is `false`.
* `OpenOnFocus` (`bool`)&mdash;Specifies whether the prompt input should open the suggestions dropdown when the input field is focused. The default value is `true`.
* `IsSuggestedPromptsVisible` (`bool`)&mdash;Specifies whether the suggested prompts should be visible. The default value is `true`.
* `IsRecentPromptsVisible` (`bool`)&mdash;Specifies whether the recent prompts should be visible. The default value is `true`.
* `IsEmptyContentVisible` (`bool`)&mdash;Specifies whether the empty content message should be visible when no suggestions are available. The default value is `true`.
* `SuggestedPrompts` (`IEnumerable<string>`)&mdash;Specifies the collection of suggested prompts.
* `RecentPrompts` (`IEnumerable<string>`)&mdash;Specifies the collection of recent prompts.

This is how the default AI Smart Assistant view looks like when there are no suggestions and recent prompts available and the `IsEmptyContentVisible` property is set to `True`:
#end

#ai-prompt-events
* `PromptRequest`&mdash;Occurs when a prompt is submitted from the AI Smart Assistant panel.
	* The `sender` argument, which is of type `object`, but can be cast to the `RadDataGrid` type.
	* A `DataGridPromptRequestEventArgs` object, which provides the following properties:
		- `Prompt`&mdash;Gets the prompt text that was submitted from the user.
		- `RequestJson`&mdash;Specifies the JSON request sent to the AI model.
		- `ResponseJson`&mdash;Specifies the response text.
		- `HasError`&mdash;Specifies whether an error occurred during processing.

* `CancelPromptRequest`&mdash;Occurs when the user requests to cancel the current AI processing operation
	* The `sender` argument, which is of type `object`, but can be cast to the `RadDataGrid` type.
	* An `EventHandler` object.
#end

#ai-prompt-commands
* `PromptRequestCommand` (`ICommand`)&mdash;Gets the command that is executed when a prompt request is submitted. The command parameter is of type `Telerik.Maui.Controls.DataGrid.DataGridPromptRequestCommandContext`.
* `CancelPromptRequestCommand` (`ICommand`)&mdash;Gets the command that is executed when canceling a prompt request. The command parameter is of type `object`.
#end