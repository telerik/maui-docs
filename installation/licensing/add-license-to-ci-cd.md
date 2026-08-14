---
title: Adding License Key to CI Services
page_title: Adding Your License Key to CI Services
description: Learn how to activate the Telerik UI for .NET MAUI components by downloading and setting up your Telerik components license key for use in CI/CD environments.
slug: add-license-to-ci-cd
tags: maui,components,license,activate,download,ci,cd,environment
position: 2
---

# Adding the License Key to CI/CD Services

This article describes how to set up and activate your Telerik UI for .NET MAUI [license key]({%slug set-up-your-license%}) across a few popular CI/CD services by using deployment keys

Deployment keys are a dedicated type of license key for build pipelines. They’re tied to a specific application and the set of products that the application uses. Deployment keys cannot be used for application development.

To activate your license in a CI/CD environment:

1. Navigate to the [Deployment Keys](https://www.telerik.com/account/downloads/deployment-keys) page.

2. Click **Add Application**. In the form that opens:

    * Add the application name.

    * Select the type of application—public or private.

    * Select the set of products used in the application.

3. Copy the key value and store it securely.

4. [Create an environment variable](#creating-an-environment-variable) named TELERIK_LICENSE and set it to the obtained key value. Alternatively, the key can be stored in a telerik-license.txt file, for example when using the [Azure Secure files approach](#using-secure-files-on-azure-devops).

When working with CI/CD platforms, always add the `Telerik.Licensing` NuGet package as a project dependency. This package activates the Telerik UI for .NET MAUI components at build time by using the provided license key.

> If you cannot use NuGet packages in your project, see the workaround in the [Adding Your License Key to CI Platforms as a Code Snippet]({%slug add-license-as-snippet-ci-cd%}) KB article.

## Creating an Environment Variable

The recommended approach for providing your license key to the `Telerik.Licensing` NuGet package is to use environment variables. Each CI/CD platform has a different process for setting environment variables and this article lists only some of the most popular examples.

### GitHub Actions

1. Create a new [Repository Secret](https://docs.github.com/en/actions/reference/encrypted-secrets#creating-encrypted-secrets-for-a-repository) or an [Organization Secret](https://docs.github.com/en/actions/reference/encrypted-secrets#creating-encrypted-secrets-for-an-organization).

1. Set the name of the secret to `TELERIK_LICENSE` and paste the contents of the license file as a value.

1. After running npm install or yarn, add a build step to activate the license:

```YAML
env:
    TELERIK_LICENSE: ${{ secrets.TELERIK_LICENSE }}
```

### Azure Pipelines

1. Create a new [secret variable](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/set-secret-variables?view=azure-devops&tabs=yaml%2Cbash) named `TELERIK_LICENSE`.

1. Paste the contents of the license key file as a value.

> Always consider the Variable size limit—if you are using a [Variable Group](https://learn.microsoft.com/en-us/azure/devops/pipelines/library/variable-groups?view=azure-devops&tabs=azure-pipelines-ui%2Cyaml), the license key will typically exceed the character limit for the variable values.
>
> The only way to have a long value in the Variable Group is to link it from [Azure Key Vault](https://learn.microsoft.com/en-us/azure/devops/pipelines/library/link-variable-groups-to-key-vaults?view=azure-devops). If you cannot use a Key Vault, then use a normal pipeline variable instead (see above) or use the [Secure files approach instead](#using-secure-files-on-azure-devops).

## Using Secure Files on Azure DevOps

Secure files are an alternative approach for sharing the license key file in Azure Pipelines that does not have the size limitations of environment variables.

You have two options for the file-based approach. Set the `TELERIK_LICENSE_PATH` variable or add a file named `telerik-license.txt` to the project directory or a parent directory.

> Make sure you’re referencing `Telerik.Licensing` v1.4.10 or later.

### YAML Pipeline

With a YAML pipeline, you can use the [DownloadSecureFile@1](https://learn.microsoft.com/en-us/azure/devops/pipelines/tasks/reference/download-secure-file-v1?view=azure-pipelines&tabs=windows) task, then use `$(name.secureFilePath)` to reference it. For example:

```yaml
- task: DownloadSecureFile@1
name: DownloadTelerikLicenseFile # defining the 'name' is important
displayName: 'Download Telerik License Key File'
inputs:
    secureFile: 'telerik-license.txt'

- task: MSBuild@1
displayName: 'Build Project'
inputs:
    solution: 'myapp.csproj'
    platform: Any CPU
    configuration: Release
    msbuildArguments: '/p:RestorePackages=false'
env:
    # use the name.secureFilePath value to set TELERIK_LICENSE_PATH
    TELERIK_LICENSE_PATH: $(DownloadTelerikLicenseFile.secureFilePath)
```

### Classic Pipeline

With a classic pipeline, use the **Download secure file** task and a PowerShell script to set `TELERIK_LICENSE_PATH` to the secure file path.

1. Add a **Download secure file** task and set the output variable's name to `telerikLicense`.

![Azure DevOps Download Secure File Classic](images/classic-download.png)

2. Add a PowerShell task and set the `TELERIK_LICENSE_PATH` variable to the `secureFilePath` property of the output variable:

![Azure DevOps PowerShell Classic](images/classic-set.png)

The script to set the environment variable is quoted below:

```powershell
Write-Host "Setting TELERIK_LICENSE_PATH to $(telerikLicense.secureFilePath)"
Write-Host "##vso[task.setvariable variable=TELERIK_LICENSE_PATH;]$(telerikLicense.secureFilePath)"
```

Alternatively, copy the file into the repository directory:

```powershell
echo "Copying $(telerikLicense.secureFilePath) to $(Build.Repository.LocalPath)/telerik-license.txt"
Copy-Item -Path $(telerikLicense.secureFilePath) -Destination "$(Build.Repository.LocalPath)/telerik-license.txt" -Force
```

## See Also

* [License Activation Errors and Warnings]({%slug license-errors-warnings%})
* [Setting Up Your License Key]({%slug set-up-your-license%})
* [Frequently Asked Questions about Your Telerik UI for .NET MAUI License Key]({%slug licensing-faq%})
