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
1. Go to the [**Manage NuGet Keys**](https://www.telerik.com/account/downloads/nuget-keys) page in your Telerik account.

1. Select the **DOWNLOADS** tab and then **Manage NuGet Keys**.

    ![Manage NuGet Keys](../images/manage-nuget-keys.png)

1. To create a new key, select the **Generate New Key** button.

1. Enter a name for the NuGet Key, and then select **Generate Key**.

1. To copy the key, select **Copy and Close**. Once you close the window, you can no longer copy the generated key. For security reasons, the **NuGet Keys** page displays only a portion of the key.

    ![Copy Generated NuGet Key](../images/copy-nuget-key.png)

1. Store the generated NuGet API key as you will need it in the next step.
#end