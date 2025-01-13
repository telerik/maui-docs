---
title: Frequently Asked Questions
page_title: Frequently Asked Questions about Your Telerik UI for .NET MAUI License
description: Learn what can cause an invalid license for Telerik UI for .NET MAUI, learn what are the common warnings and errors, and learn how to solve them.
slug: licensing-faq
tags: maui,components,license,activate,download,error,warning,questions,faq
position: 3
---

# Frequently Asked Questions about Your Telerik UI for .NET MAUI License

This article lists the answers to the most frequently asked questions (FAQs) about working with the Telerik UI for .NET MAUI license key.

## I updated the version of the Telerik UI for .NET MAUI packages in my project and the invalid license errors have appeared. What is the cause of this behavior?

If this happens, the possible reason is that the end date of the license activated in your application is before the release date of the newly installed Telerik UI for .NET MAUI. To fix this issue:

1. [Download a new license key]({%slug set-up-your-license%}#downloading-the-license-key).

1. [Install  the new license key]({%slug set-up-your-license%}#installing-or-updating-your-license-key) in your project.

## Can I use the same license key in multiple builds?

You can use your personal license key in multiple pipelines, builds, and environments.

However, each individual developer must use a unique personal license key.

## Does the license key expire?

Yes, the license key expires at the end of your support subscription:

* For trial users, this is at the end of your 30-day trial.

* For commercial license holders, this is when your subscription term expires.

You will need to obtain and install a new license key after starting a trial, renewing a license, or upgrading a license.

> An expired perpetual license key is valid for all Telerik UI for .NET MAUI versions published before its expiration date.

## Do I need an Internet connection to activate the license?

No, the license activation and validation are performed entirely offline.

The license is not validated with our services at any point in the project lifecycle.

## Do I have to add the license key to source control?

No, you do not have to add the `telerik-license.txt` license key file or its contents to source control.

Build servers must use the `TELERIK_LICENSE` environment variable described in [Adding the License Key to CI Services]({%slug add-license-to-ci-cd%}).

Do not store the license key in plain text, for example, in a GitHub Actions Workflow definition.

## What happens if both the environment variable and the license key file are present?

If both the `TELERIK_LICENSE` environment variable and the `telerik-license.txt` file are present, then the environment variable will be used.

To enforce the use of the license key file, unset the environment variable.

## My team has more than one license holder. Which key do we have to use?

To activate Telerik UI for .NET MAUI, you can use any of the keys associated with your subscriptions.

## Are earlier versions of Telerik UI for .NET MAUI affected?

No, versions released prior to January 2025 do not require a license key.

## What happens if I make a change to non-Telerik parts of the code after the subscription expires?

This depends on your license:

* If you have a perpetual license, you can build the application with the Telerik components.

* If you have an expired subscription license, the build will fail.

## See Also

* [Setting Up Your License Key]({%slug set-up-your-license%})
* [License Activation Errors and Warnings]({%slug license-errors-warnings%})
* [Adding the License Key to CI Services]({%slug add-license-to-ci-cd%})
