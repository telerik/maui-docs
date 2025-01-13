---
title: License Activation Errors and Warnings
page_title: License Activation Errors and Warnings
description: Learn what can cause an invalid license for Telerik UI for .NET MAUI, learn what are the common warnings and errors, and learn how to solve them.
slug: license-errors-warnings
tags: maui,components,license,activate,download,error,warning
position: 4
---

# License Activation Errors and Warnings

Starting with the 2025 Q1 release, using Telerik UI for .NET MAUI without a license or with an invalid license causes specific license warnings and errors. This article defines what an invalid license is, explains what is causing it, and describes the related license warnings and errors.

>The implementation of the 2025 Telerik UI for .NET MAUI licensing requirements will occur in two phases:
>
>- Phase 1&mdash;Starting with the 2025 Q1 release a missing or invalid license logs a warning in the build log.
>
>- Phase 2&mdash;Starting with the 2025 Q2 release a missing, expired, or invalid license will result in:
>   - A watermark appearing on application startup.
>   - A modal dialog appearing on application startup. Clicking the **OK** button closes the dialog and removes the banner until the next application startup.
>   - A warning message similar to the following appearing in the build log: `No license key is detected`.

## Invalid License

An invalid license can be caused by any of the following:

- Using an expired subscription license—subscription licenses expire at the end of the subscription term.
- Using a perpetual license for product versions released outside the validity period of your license.
- Using an expired trial license.
- A missing license for Telerik UI for .NET MAUI.
- Not installing a license key in your application.
- Not updating the license key after renewing your Telerik UI for .NET MAUI license.

## License Warnings and Errors

Using Telerik UI for .NET MAUI in a project with an expired or missing license, the `Telerik.Licensing` build task will indicate the following errors:

- `No license key is detected`—[Install a license key]({%slug set-up-your-license%}#installing-or-updating-your-license-key) to activate the UI components and remove the error message.
- `Invalid license key`—[Download a new license key]({%slug set-up-your-license%}#downloading-the-license-key) and install it to activate the UI components and remove the error message.

In addition, the following conditions will be logged:

| Condition                              | Solution                                                                                      |
|----------------------------------------|-----------------------------------------------------------------------------------------------|
| `Your subscription license has expired.` | Renew your subscription and [download a new license key]({%slug set-up-your-license%}#downloading-the-license-key). |
| `Your perpetual license is invalid.` | You are using a product version released outside the validity period of your perpetual license. To remove the error message, do either of the following: |
|                                        | - Purchase a license for the product version you are using, then download a new license key and install it. |
|                                        | - Downgrade to a product version included in your perpetual license as indicated in the message. |
| `Your trial license has expired.`        | Purchase a commercial license to continue using the product. |
| `Your license is not valid for the detected product(s).` | Review the purchase options for the listed products. Alternatively, remove the references to the listed packages from `package.json`. |

>Starting with the 2025 Q2 release of Telerik UI for .NET MAUI in May 2025, all conditions above will be treated as errors.

## See Also

* [Setting Up Your License Key]({%slug set-up-your-license%})
* [Adding the License Key to CI Services]({%slug add-license-to-ci-cd%})
* [Frequently Asked Questions about Your Telerik UI for .NET MAUI License Key]({%slug licensing-faq%})
