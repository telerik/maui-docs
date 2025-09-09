#nuget-security-links
The following Microsoft articles describe the best practices for securing your NuGet feed setup and supply chain:

* <a href="https://devblogs.microsoft.com/nuget/lock-down-your-dependencies-using-configurable-trust-policies/" target="_blank">Lock down your dependencies using configurable trust policies - Blog Post</a>

* <a href="https://devblogs.microsoft.com/nuget/how-to-scan-nuget-packages-for-security-vulnerabilities/" target="_blank">How to Scan NuGet Packages for Security Vulnerabilities - Blog Post</a>

* <a href="https://docs.microsoft.com/en-us/nuget/concepts/security-best-practices" target="_blank">Best practices for a secure software supply chain - MSDN docs</a>

Telerik provides signed NuGet packages that you can verify.
#end

#status-telerik-com
## Telerik NuGet Feed Status

Visit <a href="https://status.telerik.com" target="_blank">status.telerik.com</a> to check the status of the Telerik NuGet server. The top section shows manually logged incidents with possible updates or workaround suggestions. The <a href="https://status.telerik.com/#system-metrics" target="_blank">System Metrics section</a> provides real-time automated diagnostics.
#end

#generate-nuget-key
As the Telerik NuGet server requires authentication, the first step is to obtain an API key that you will use instead of a password. Using an API key instead of a password is a more secure approach, especially when working with [.NET CLI]({% slug nuget-dotnet-cli %}) or the [`NuGet.Config` file]({% slug nuget-config %}).

1. Go to the [NuGet Keys](https://www.telerik.com/account/downloads/nuget-keys) page in your Telerik account.
1. Click **Generate New Key +**.

   ![Manage NuGet Keys](/installation/images/account-generate-nuget-api-key.png)

1. In the **Key Note** field, add a note that describes the API key.
1. Click **Generate Key**.
1. Select **Copy and Close**. Once you close the window, you can no longer copy the generated key. For security reasons, the **NuGet Keys** page displays only a portion of the key.
1. Store the generated NuGet API key as you will need it in the next steps. Whenever you need to authenticate your system with the Telerik NuGet server, use `api-key` as the username and your generated API key as the password.

#end